# HTTP3

## 资料

> [https://blog.csdn.net/howgod/article/details/102597450](https://blog.csdn.net/howgod/article/details/102597450)
>
> [http://xiaorui.cc/archives/6117](http://xiaorui.cc/archives/6117)
>
> 详细 [https://zhuanlan.zhihu.com/p/32553477](https://zhuanlan.zhihu.com/p/32553477)
>
> 0RTT [https://cloud.tencent.com/developer/article/1594468](https://cloud.tencent.com/developer/article/1594468)

## Quic

> 1. 解决队首阻塞，面向数据报文，宝举报之间没有阻塞，丢包只会影响对应的stream，前向纠错，减少重传
> 2. 可靠性，前向纠错，失败重传，单调递增seq
> 3. 0RTT 规避三次握手，一次server config的缓存，后面只要缓存不失效，重连无序TLS交互
>    1. 利用第一次握手得到的服务端公钥 + 本地的私钥 通过DH 算法得到加密对
> 4. 拥塞窗口，网络质量检测，避免流量浪费

## 前向纠错

> 发送数据包AB的时候会增发，AB的异或C，发生丢包的时候利用其中任意两个包，来得到第三个包，减少重传

## 几个点

> 1. 有序性，可靠性，单调递增的seq + offset
> 2. 重传的sack范围更大，减少不必要的重传，向前容错等

## 链接迁移

> * tcp
>   * ip和端口四元组（目标地址，目标端口，源地址，源端口）组成
> * quic
>   * 以64位的唯一标识符 表示，不需要重连



