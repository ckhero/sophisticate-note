# HTTP3

## 资料

> [https://blog.csdn.net/howgod/article/details/102597450](https://blog.csdn.net/howgod/article/details/102597450)
>
> [http://xiaorui.cc/archives/6117](http://xiaorui.cc/archives/6117)



## Quic

> 1. 解决队首阻塞，面向数据报文，宝举报之间没有阻塞，丢包只会影响对应的stream，前向纠错，减少重传
> 2. 可靠性，前向纠错，失败重传，单调递增seq
> 3. 0RTT 规避三次握手，一次server config的缓存，后面只要缓存不失效，重连无序TLS交互
> 4. 拥塞窗口，网络质量检测，避免流量浪费

## 前向纠错

> 发送数据包AB的时候会增发，AB的异或C，发生丢包的时候利用其中任意两个包，来得到第三个包，减少重传



