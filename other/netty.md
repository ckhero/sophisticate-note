# Netty

## 资料

> https://www.jianshu.com/p/b9f3f6a16911

# 简述

> java编写的一个NIO的网络通信框架。支持多种协议http2

## 高并发

> 基于NIO的网络通信

## 传输快

> 零拷贝。传统的拷贝模式是从磁盘-&gt;页缓存-&gt;堆内存-&gt;socket缓存，neety会在堆内存之外开辟一部分空间。直接从磁盘读到该空间，然后通过ByteBuf堆其内部的数据进行操作

## 封装好

> 无法描述







