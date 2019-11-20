## Windows 下 切换 openpilot 分支版本（openpilot fork）

### 获取 EON 的 IP 地址

#### \- 如果 电脑 和 EON 同时接入网络

1. EON 和 电脑 接入同一局域网（比如连接同一个路由器的 WIFI 信号）。
2. 在 EON 上，通过菜单 "设置 - 网络 - 无线网络设置 - 更多选项（右上角）- 右上角三个点 - 高级"，打开 WiFi 连接信息界面，即可查看 EON IP 地址。


#### \- 如果 电脑 通过 WiFi 连接到了 EON 提供的 WiFi 热点

1. 电脑通过 WIFI 连接到 EON 提供的 WiFi 热点。
2. 电脑的 IP 是 `192.168.43.x`，EON 的IP 固定为 `192.168.43.1`。

附：[EON 如何设置共享 WIFI 热点](how_to_connect_openpilot_via_iphone.md)


### 下载 Putty 和 ppk（私钥）

1. 下载软件 putty （ 下载地址：http://d.sdut.me/putty ）
2. 下载私钥 ppk （ 下载地址：http://d.sdut.me/eonkeys/eon.ppk ）

### 填写信息，SSH 连接到 EON

1. 打开 Putty 填写 IP 和 Port
2. 点击左侧菜单 "Connection - SSH - Auth"，点击右侧最下面 Browse 选择 ppk 私钥
3. 点击右下角 Open 按钮，弹出窗口点击确认
4. Putty 的 "login as :" 界面输入 `root`，然后回车
5. 进入 EON 的 shell 环境了

选项|填写|备注
-|-|-
Host Name<br>(or IP address)| `192.168.43.1` 或者 EON 的 IP| 第一步查询到的 EON 的 IP
Port| `8022`|SSH 端口号，这里默认是 `8022`
Private Key| 点击 Browse，选择之前下载的 ppk 文件 |ppk 格式为客户端 putty 专用

### 切换 openpilot 分支版本

依次执行下列命令切换分支版本：
```bash
# 打开 data 目录
cd /data

# 备份原有的 openpilot
mv openpilot openpilot.bak

# 下载新的版本分支
git clone https://gitee.com/afaaa/kegman openpilot

# 打开 openpilot 目录
cd openpilot

# 查看全部分支 和 当前分支
git branch -a

# 切换到目标分支
git checkout 

# 重新查看确认当前分支
git branch

# 编译重启
make && reboot
```
