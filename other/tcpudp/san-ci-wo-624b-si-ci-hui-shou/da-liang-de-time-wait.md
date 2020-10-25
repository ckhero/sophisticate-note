# 大量的time\_wait

> https://www.cnblogs.com/dadonggg/p/8778318.html

## 原因

> * TCP关闭的时候为保证正确关闭，关闭发起者再接收到被关闭者的FIN指令后进入time\_wait状态。默认60s
> * 端口范围是0-65535
> * 高并发场景下，http链接使用后，丢弃。然后进入time\_wait状态。导致端口得不到释放

## 解决

> 修改/etc/sysctl.conf
>
> 1. net.ipv4.tcp\_tw\_reuse  // 开启重用
> 2. net.ipv4.tcp\_tw\_recycle // 开启快速回收
> 3. net.ipv4.tcp\_fin\_timeout   // 修改超时时间



