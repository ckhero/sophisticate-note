# 服务治理

## 资料

> [https://blog.csdn.net/haponchang/article/details/93488503](https://blog.csdn.net/haponchang/article/details/93488503)

## 微服务的问题

> 注册中心宕机
>
> 服务提供者宕机
>
> 服务消费者和注册中心网络不连通
>
> 服务提供者和注册中心网络不连通
>
> 服务消费者和服务提供者网络不连通
>
> 服务提供者性能变慢
>
> 服务提供者短时不可用

### 节点管理

> 服务调用失败原因两种
>
> * 服务提供者宕机
> * 服务提供者 注册中心 服务消费者 三者任意两者网络不连通

#### 》方案

注册中心自动摘除机制

> 要求服务提供者定时向注册中心发送心跳，注册中心根据最近一次心跳汇报和上一次的心跳汇报时间对比，如果超出一定时间就认为服务不可用，然后把节点从可用列表摘除，并且同步给服务消费者

##### 服务消费者摘除机制

> 如果因为服务提供者和注册中心网络不连通导致的可用节点被摘除，会导致服务消费者没有可用服务。所以存活探测机制放在消费者端更合理。如果消费者调用失败则从内存中保存的可用列表删除

### 负载均衡

> 服务提供者一般以集群的方式存在。不同的机器性能不同，所以通过负载均衡让性能更好的机器处理更多的请求

#### 》方案

##### 随机算法

> 随机选取节点，无论机器好坏，得到的调用量差不多

##### 轮询算法

> 按照权重去轮询节点，可以做到让性能好的机器处理更多的调用

##### 最少活跃调用算法

> 消费者端维护节点的连接数。优先调用连接数少的节点，性能理论上也是最优的

##### 一致性hash算法

> 相同的请求参数总会发送到同一个节点。若节点出现故障，基于虚拟节点机制，平摊到其他节点

### 服务路由

> 对于消费而言使用哪个节点不仅有负载均衡决定，还由服务路由规则决定
>
> 所谓的服务路由就是通过一定的规则限定服务节点的选择范围

#### 》原因

##### 业务存在灰度发布的需求

##### 多机房就近访问的需求

#### 》方案

##### 静态配置

> 消费者本地存放，修改需要重新上线

##### 动态配置

> 通过配置中心去做

## 服务容错 {#%E6%9C%8D%E5%8A%A1%E5%AE%B9%E9%94%99}

* ##### FailOver

> 失败自动切换
>
> 失败后重新选取可用的节点。适合读多的场景。要求操作是幂等的

* ##### FailBack

> ##### 失败通知
>
> 失败后不在重试，根据失败的详细信息决定后续的执行策略。对于非幂等的场景，不能简单的重试，因为我们不知道上次调用是否真的失败了。应查询服务提供者端的状态

* ##### FailCache

> ##### 失败缓存
>
> 失败后不立即重新发起请求，而是隔一段时间重新发起请求。 比如服务端短时有问题的话，立即重试不利于服务端的回复

* ##### FailFast

> ##### 快速失败机制
>
> 非核心的业务开启快速失败



