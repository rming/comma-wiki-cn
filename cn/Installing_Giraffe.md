# 安装 Giraffe


## 安装位置

如果你的车兼容 openpilot，那么在车内后视镜后面会有一个用于车道保持的摄像头模块，就固定在前挡风玻璃顶部。 giraffe 需要插在摄像头模块插头上，与汽车数据线串联在一起。

** 摄像头模块插头被盖板挡住了，需要拆下盖板，才能看到插头和数据线。**

下面是一些车型的拆装视频：

* [丰田摄像头盖板拆卸视频](https://www.bilibili.com/video/av66404543?t=298)
* [本田摄像头盖板拆卸视频](https://www.bilibili.com/video/av66405025?t=23)

以上是本田和丰田车型视频，其他车型基本相似。


## 指拨开关

Giraffe 上面的指拨开关（DIP switch）配置，需要参考响应的 Giraffe 文档：

- [菲亚特 Giraffe](https://github.com/commaai/neo/tree/master/giraffe/fca)
- [本田 Giraffe](https://github.com/commaai/neo/tree/master/giraffe/honda)
- [现代 Giraffe](https://github.com/commaai/neo/tree/master/giraffe/hyundai)
- [丰田 Giraffe](https://github.com/commaai/neo/tree/master/giraffe/toyota)



先拔掉原车摄像头模块的数据线，然后把 Giraffe 插到摄像头模块插座上，Panda 插到 Giraffe 的 OBD 接口上，原车数据线也插到 Giraffe 的插座上，这样就把原车摄像头、Giraffe、Panda、原车数据线串联在了一起。


Panda 还有一个 USB 数据线，把 USB 插头接到你的 EON (手机) 上，你的 EON 就是通过这条线从 Panda 接收、发送指令。


接下来我们再看怎样 [安装 EON](Installing_EON.md).

------

相关资料：
- [硬件设备简介](hardwares.md)
