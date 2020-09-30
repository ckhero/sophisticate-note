# go-micro

## 资料

> [https://blog.csdn.net/mi\_duo/article/details/82701732](https://blog.csdn.net/mi_duo/article/details/82701732)、
>
> 容错 [https://www.kancloud.cn/linimbus/go-micro/529028](https://www.kancloud.cn/linimbus/go-micro/529028)
>
> [https://www.cnblogs.com/li-peng/p/9689786.html](https://www.cnblogs.com/li-peng/p/9689786.html)
>
> 深度学习 [https://www.cnblogs.com/li-peng/p/10522084.html](https://www.cnblogs.com/li-peng/p/10522084.html)

## 简述

> 插件式RPC框架，提供服务发现，客户端负载均衡，编码，同步和异步通信

## 高度定制化

> go-micro由8个关键的interface组成，每一个interface都可以根据自己的需求重新实现，这8个主要的inteface也构成了go-micro的框架结构。
>
> ![](/assets/import.png)

## 容错

> 心跳
>
> * 设置注册服务的过期时间，定期去刷新
>
> 负载均衡
>
> * client通过selector获取next可用节点去重试
>
> 缓存发现
>
> * client缓存发现服务。另起一个协程去watch注册中心的服务变更，如果新增发现把发现加入本地缓存。发现失效则删除本发现

## 注册服务

> * 设置服务的过期时间，避免服务提供者突然宕机。超时后会自动删除
> * 设置服务的刷新间隔

## 发现服务

> 1 . 去注册中心取，go-micro默认设置的cache。 DefaultSelectors里的cache对应的就是初始化cacheSelector方法\(cmd.go\)。设置缓存时间，过期重新获取。还会跑一个携程去watch服务的注册。如果有新的节点则添加到缓存当中。如果有故障节点则删除。client获取主机信息还需要通过Strategy去获取，目前只支持随机和轮询\(目前就是简单的轮询，一个个试过去\)。
>
> 调用失败的时候通过next的Strategy获取新的服务重试

## Selector类别

> ```
> DefaultSelectors = map[string]func(...selector.Option) selector.Selector{
>         "default": selector.NewSelector,
>         "dns":     dns.NewSelector,
>         "cache":   selector.NewSelector,
>         "router":  router.NewSelector,
>         "static":  static.NewSelector,
>     }
> ```

## Call 过程

> 通过selector获取服务器的信息，然后去client的pool里面找对应的client，没有则创建。再进行数据传输



