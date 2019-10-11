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




