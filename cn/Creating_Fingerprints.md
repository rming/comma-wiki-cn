## 采集车辆指纹信息


OpenPilot 通过对比 CAN 信号读取到的车辆指纹信息 与 已知的指纹列表 识别当前连接的什么车型（`/data/openpilot/selfdrive/car/{汽车厂商}/values.py` 文件中的指纹信息列表）。

现在，同一型号的不同配置车型有时候会有不同的指纹信息，如果 openpilot 还没有包含你车辆的指纹信息，那么你需要自己创建一个指纹信息。

如果你的 EON 开机并联网，你可以使用 [Workbench](https://github.com/jfrux/workbench) 在局域网里搜索到你的 EON，SSH 连接进去，抓取车辆指纹（EON 需要连接到车上）。

**操作步骤：**
1. 车辆熄火后，通过 Giraffe 把 PANDA 连接到车上，EON 连接到 PANDA 上。
2. 把 Giraffe 设置成 **原车模式（stock mode）**（你需要采集原车发送的 CAN信号数据 ，而不是 openpilot 的）
3. SSH 连接到 EON，在两个会话窗口中分别运行下面 2 个命令
```bash
/data/openpilot/selfdrive/boardd/boardd
```
```bash
cd /data/openpilot/selfdrive && PYTHONPATH=/data/openpilot PREPAREONLY=1 /data/openpilot/selfdrive/debug/get_fingerprint.py
```
4. 启动汽车，等大约 20 秒钟，确保可以得到如下的全部DBC消息：
<pre style="white-space: pre-wrap;word-wrap: break-word;">
number of messages: 107
fingerprint 36L: 8, 37L: 8, 166L: 8, 170L: 8, 180L: 8, 295L: 8, 296L: 8, 426L: 6, 452L: 8, 466L: 8, 467L: 8, 550L: 8, 552L: 4, 560L: 7, 562L: 6, 581L: 5, 608L: 8, 610L: 8, 614L: 8, 643L: 7, 658L: 8, 713L: 8, 740L: 5, 742L: 8, 743L: 8, 800L: 8, 810L: 2, 814L: 8, 824L: 2, 829L: 2, 830L: 7, 835L: 8, 836L: 8, 863L: 8, 869L: 7, 870L: 7, 871L: 2, 898L: 8, 900L: 6, 902L: 6, 905L: 8, 913L: 8, 918L: 8, 921L: 8, 933L: 8, 944L: 8, 945L: 8, 950L: 8, 951L: 8, 953L: 8, 955L: 8, 956L: 8, 971L: 7, 974L: 8, 975L: 5, 993L: 8, 998L: 5, 999L: 7, 1000L: 8, 1001L: 8, 1014L: 8, 1017L: 8, 1020L: 8, 1041L: 8, 1042L: 8, 1044L: 8, 1056L: 8, 1057L: 8, 1059L: 1, 1071L: 8, 1076L: 8, 1077L: 8, 1082L: 8, 1083L: 8, 1084L: 8, 1085L: 8, 1086L: 8, 1114L: 8, 1132L: 8, 1161L: 8, 1162L: 8, 1163L: 8, 1164L: 8, 1165L: 8, 1166L: 8, 1167L: 8, 1175L: 8, 1227L: 8, 1228L: 8, 1235L: 8, 1237L: 8, 1279L: 8, 1552L: 8, 1553L: 8, 1556L: 8, 1557L: 8, 1568L: 8, 1570L: 8, 1571L: 8, 1572L: 8, 1595L: 8, 1777L: 8, 1779L: 8, 1904L: 8, 1912L: 8, 1990L: 8, 1998L: 8
</pre>
5. 熄火并重新启动几次，确保接收到了全部消息（某些消息仅在启动时发送）。
6. `<CTRL> + C` 关闭程序.
7. 将从第3步中获得的 DBC消息 复制到  `/data/openpilot/selfdrive/car/{汽车厂商}/values.py` 文件的 "FINGERPRINTS" 部分（创建新的车型，或者暂时覆盖之前已经存在的车型）。 
8. 汽车熄火，重启 EON。
