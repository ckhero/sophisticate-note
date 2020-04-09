# go-micro

## 资料

> [https://blog.csdn.net/mi\_duo/article/details/82701732](https://blog.csdn.net/mi_duo/article/details/82701732)、
>
> 容错 [https://www.kancloud.cn/linimbus/go-micro/529028](https://www.kancloud.cn/linimbus/go-micro/529028)
>
> [https://www.cnblogs.com/li-peng/p/9689786.html](https://www.cnblogs.com/li-peng/p/9689786.html)

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
>
> * micro通过选择器进行客户端的负载均衡
>
> 重试
>
> * 客户端有请求失败重试机制，失败后通过负载均衡获得下一个节点去重试，默认一次
>
> 缓存发现
>
> * 发现缓存是服务发现的客户端缓存

## 注册服务

> * 设置服务的过期时间，避免服务提供者突然宕机。超时后会自动删除
> * 设置服务的刷新间隔

## 发现服务

> 去注册中心取，go-micro默认设置的cache。 DefaultSelectors里的cache对应的就是初始化cacheSelector方法



