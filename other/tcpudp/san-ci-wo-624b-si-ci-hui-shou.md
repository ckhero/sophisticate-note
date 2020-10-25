# 三次握手/四次挥手

> [https://blog.csdn.net/weixin\_32208747/article/details/87842240](https://blog.csdn.net/weixin_32208747/article/details/87842240)
>
> [https://blog.csdn.net/qzcsu/article/details/72861891](https://blog.csdn.net/qzcsu/article/details/72861891)
>
> time-out [https://draveness.me/whys-the-design-tcp-time-wait/](https://draveness.me/whys-the-design-tcp-time-wait/)

## 简述

> 第一次握手，发送客户端序列号
>
> 第二次  发送确认码和服务端序列号
>
> 第三次发送确认码

## 为什么要三次

> tcp要提供可靠高效的传输。三次握手主要目的是互相交换原始序列号，两次的话，只交换了客户端的序列号，四次的话没必要

## 异常

> 第一次握手异常，客户端在75秒内会重传
>
> 第二次异常，客户端没收到，服务端会重传ack，syn，超过指定次数后，服务端关闭
>
> ```
>              如果客户端收到了，客户端开始发送数据，服务端不接受这数据，继续发送ack，syn
> ```
>
> 第三次异常，客户端会继续发送ack

## 四次挥手客户端2MSL

> * 保证TCP被正确的关闭，等待被动关闭的一方收到FIN的ACK，被动关闭一方的FIN没收到ACK的情况下会重传
> * 阻止延迟数据段，被相同的源地址，源端口号，目标地址，目标端口号的TCP接收到
>   * 如果不等2MSL的话，服务端重发的FIN可能会被新打开的同一个端口号的TCP链接接收到

## 意外断开

> 保活机制，两小时，如果两小时后还没接收到请求，开始嗅探，嗅探失败断开连接



