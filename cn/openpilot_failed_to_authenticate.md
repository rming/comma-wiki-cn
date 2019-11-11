## failed to authenticate 和 无法绑定账户问题

一些手机设备因为刷机问题、分区信息丢失等问题，即使重新安装好 NEOS 系统后，也无法正常通过 `IMEI` 和 `SN` 在 Openpilot 官方通过授权验证，在系统安装过程中，通常会出现 `openpilot failed to authenticate` 的报错，这时候可以通过变更 `IMEI` 的方式解决。

```bash
getting pilotauth
failed to authenticate
Traceback (most recent call last):
  File "/data/openpilot/selfdrive/registration.py", line 94, in register
    dongle_id, access_token = dongleauth["dongle_id"].encode('ascii'), dongleauth["access_token"].encode('ascii')
KeyError: 'dongle_id'
Traceback (most recent call last):
  File "./manager.py", line 622, in <module>
    main()
  File "./manager.py", line 598, in main
    manager_init()
  File "./manager.py", line 313, in manager_init
    raise Exception("server registration failed")
Exception: server registration failed
```

<center><small>通过 ssh 进入 eon，<code>tmux at</code> 后看到的报错信息</small></center>

### IMEI 生成工具

IMEI 相当于设备的身份证号，有一定的格式规则，包含品牌、型号、产地等信息，但是这里 openpilot 官方对 IMEI 的验证并不严格，只要满足校验位正确就可以，如果你需要一个新的 IMEI，并且对品牌、型号没有要求，则可以通过下面这个工具生成。

<script src="/files/imei-generator.js" type="text/javascript" charset="utf-8" async defer></script>
<input type="button" onclick="imei_gen()" value="生成 IMEI -&gt;" /><input type="text" value="" size="17" id="imei_num" readonly="readonly" width="600" />


### 更改 IMEI

设备的 IMEI 是保存在芯片中的，直接修改芯片内容比较麻烦，我们可以通过软件方法在每次软件启动之前，修改这个系统属性的值，来欺骗 Openpilot 软件。 

#### 方法1（分步操作）

```bash
# 通过 ssh 登陆到 EON
ssh eon

# 编辑 openpilot 初始化脚本
vi /data/data/com.termux/files/continue.sh

# 在 exec 语句之前加入下面这行
# 517923590773528 是新设置的 IMEI，需要通过上面工具生成替换
setprop oem.device.imeicache 517923590773528

```


#### 方法2（一条命令）

```bash
# 通过 ssh 登陆到 EON
ssh eon
# 在 continue.sh 文件 第 2 行，添加一个更新 IMEI 属性值的语句 
# 517923590773528 是新设置的 IMEI，需要通过上面工具生成替换
sed '2i\setprop oem.device.imeicache 517923590773528' -i /data/data/com.termux/files/continue.sh
```

EON 的 IMEI 更改完成后，重启一下，即可正常通过官方的验证，也可以通过二维码完成绑定。

-----------


### 重新请求 DongleId 和 授权

如果你的情况是可以正常运行 Openpilot ，但是无法完成扫码绑定，那么除了需要变更 IMEI 外，你还需要下面进行这些操作。


```bash
# 通过 ssh 登陆到 EON
ssh eon

# 移除已经授权提供的 DongleId 和 授权码
rm /data/params/d/DongleId
rm /data/params/d/AccessToken
```

移除已经授权提供的 DongleId 和 授权码后，再次通过新的 IMEI 去请求官方接口，则会重新为你分配一个 DongleId，此时即可通过扫描 EON 上的二维码，完成账户绑定。


### 问题原因探究

EON 每次启动都会请求comma 服务器验证设备的绑定信息，请求的参数包含下列数据：

```bash
cat /persist/comma/id_rsa.pub
cat /persist/comma/id_rsa
getprop oem.device.imeicache
getprop ro.serialno
```

openpilot 请求服务器时：

```bash
PUBLIC_KEY + IMEI + SN + JWT_TOKEN --> | Comma Server|
[DONGLE_ID, JWT_TOKEN]             <-- | Comma Server|
```


其中 
```bash
JWT_TOKEN = RS256(PRIVATE_KEY + EXPIRE_TIME)
```

每次开机，openpilot 会用自己根据 私钥 生成的 JWT_TOKEN、公钥、IMEI、SN 去请求 comma 服务器验证 JWT_TOKEN 合法性，服务器返回设备绑定信息（Dongle ID、JWT_TOKEN）


以下是对服务器端验证策略的猜测：

设备第一次请求接口时，服务器端判断，如果 IMEI/SN 没有绑定的 公钥，则进行绑定，这样服务器端就存储了 EON公钥、IMEI、SN 的关联信息。

设备再次请求接口时，服务器端使用 IMEI 作为主索引查询当前 EON 的公钥 去验证 JWT_TOKEN 请求参数 的合法性（JWT_TOKEN 本质是私钥 + 有效期），决定是否返回设备信息（Dongle ID、JWT_TOKEN）
如果在 IMEI 注册完成后，EON 的公钥、私钥信息发生了变更（/persist/comma/id_rsa.pub、/persist/comma/id_rsa 丢失或被修改），那么服务器端就会返回 failed to authenticate 的错误信息。

服务器上可能是存在这样的关联关系：
```bash
USER_ID <---> Devices {DONGLE_ID、PUBLIC_KEY、IMEI}
```

comma api 的数据结构也可以佐证：
- [device info](https://api.comma.ai/#device-info)
- [openpilot auth](https://api.comma.ai/#openpilot-auth)

