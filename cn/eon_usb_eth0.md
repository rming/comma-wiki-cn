## EON USB网卡设置

### DHCP 客户端模式

EON 可以开启 USB 网卡的 DHCP 客户端模式，操作步骤如下：

1. USB 网卡通过 Type-C (Micro USB) 连接到 EON，USB 网口中插入网线，保证网络连接正常
2. EON 通过无线接入到局域网，电脑端通过 SSH 进入 EON
3. 在 EON 的 SSH 里执行 `dhcptool eth0` 启动 eth0 的 DHCP 客户端功能，命令会阻塞直至 DHCP 开启成功
4. 在 EON 的 SSH 里执行  `ip addr show eth0` 查看当前有线网卡的连接情况
```bash
root@localhost:/$ ip addr show eth0
6: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP qlen 1000
    link/ether 00:6f:00:00:07:5f brd ff:ff:ff:ff:ff:ff
    inet 192.168.2.201/23 brd 192.168.3.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::26f:ff:fe00:75f/64 scope link
       valid_lft forever preferred_lft forever

```
<center><small>192.168.2.201 即我们的有线网卡IP</small></center>
4. 重启 EON，只连接有线网卡（关闭无线网卡，有线、无线同时工作会有网络延迟异常的情况）

