## Openpilot 一键安装脚本

小白用户初次接触 shell，因为对 shell 不熟悉，如果需要切换 openpilot 的 fork 和 分支，可能碰到各种问题，这个一键安装脚本可以输入安装选项，简单安装更新不同的 openpilot 版本分支。

* [Openpilot 一键安装脚本](https://github.com/Rming/openpilot_install) 使用了 [Openpilot 国内镜像](/mirror.md)，文件下载也会相比较 github 快一点。


### 使用教程

1. 手机正常开机并联网
2. 电脑通过局域网连接到手机 SSH

**单次使用**，不用下载存储脚本：
```bash
# 下载并运行脚本
bash <(curl -s -L  https://gitee.com/afaaa/openpilot_install/raw/master/op_install.sh) 
```


**重复使用**，下载脚本放到 /sdcard 目录：
```bash
# 下载脚本到 /sdcard/op_install.sh
curl -o /sdcard/op_install.sh -L  https://gitee.com/afaaa/openpilot_install/raw/master/op_install.sh

# 运行脚本
bash /sdcard/op_install.sh
```

### 演示视频

<center>
{% bilibili %}av69034797{% endbilibili %}
</center>
