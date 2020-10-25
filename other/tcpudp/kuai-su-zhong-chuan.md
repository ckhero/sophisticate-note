# 重传

> [https://www.jianshu.com/p/62940de97ca5](https://www.jianshu.com/p/62940de97ca5)
>
> [https://www.cnblogs.com/xiaolincoding/p/12732052.html](https://www.cnblogs.com/xiaolincoding/p/12732052.html)

## 简述

> 1. 超时重传
>    1. 重传定时器
>    2. 以时间为驱动
> 2. 快速重传
>    1. 冗余ACK
>    2. 以数据为驱动

## 超时重传时间

> RTO，略大于一个RTT

## 为什么要用快速重传

> 在等待重传定时器的时候，后面发送的报文段可能会因为得不到ACK，也触发不必要的重传

## 冗余ACK

> 服务端如果接受的消息序列号大于最后一次ACK的值，则会把重新发送ACK，客户端接收到四次同一个ACK的时候，会触发重传。

## 快速重传SACK

> 快速重传触发的时候客户端不知道哪个数据丢失了，SACK会缓存这些信息

## 快速重传D-SACK

> 1. 告诉发送端哪些数据被重复发送了，这样子客户端可以知道是发送的包丢了，还是ACK丢了

## SACK和D-SACK 区分

> 如果缓存数据的序列号大于ACK就是SACK，小于就是D-SACK



