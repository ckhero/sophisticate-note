# go-micro

## 资料

> [https://blog.csdn.net/mi\_duo/article/details/82701732](https://blog.csdn.net/mi_duo/article/details/82701732)、
>
> 容错 [https://www.kancloud.cn/linimbus/go-micro/529028](https://www.kancloud.cn/linimbus/go-micro/529028)

## 简述

> 插件式RPC框架，提供服务发现，客户端负载均衡，编码，同步和异步通信

## 高度定制化

> go-micro由8个关键的interface组成，每一个interface都可以根据自己的需求重新实现，这8个主要的inteface也构成了go-micro的框架结构。
>
> ![](/assets/import.png)



## 容错

> 心跳
>
> * 服务注册成功后会定期向注册中心发送心跳
>
> 负载均衡
> * micro通过选择器进行客户端的负载均衡
>
> 重试
> * 客户端有请求失败重试机制，失败后通过负载均衡获得下一个节点去重试，默认一次
>
> 缓存发现
> * 发现缓存是服务发现的客户端缓存



