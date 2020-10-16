## 重复消费

> [https://zhuanlan.zhihu.com/p/112745985](https://zhuanlan.zhihu.com/p/112745985)
>
> [https://blog.csdn.net/qq\_29493353/article/details/88535092](https://blog.csdn.net/qq_29493353/article/details/88535092)
>
> https://segmentfault.com/a/1190000023282843

## 消息提交

> * 手动提交
>   * 消息消费后手动提交
> * 自动提交
>
>   * enable.auto.commit 默认值true，表示会周期性的自动提交
>
>   * 默认自动提交间隔5s，提交上次poll的最大偏移量
>
>   * poll的时候会提交上一次poll的offset

## 什么情况会导致重复消费?

> 1. 自动提交场景下，服务器宕机，有可能部分offset没提交
> 2. 手动提交场景下，客户端宕机，offset没提交
> 3. 客户端处理时间过长，进行rebalance，到时offset没提交

## 解决

> 1. 客户端做幂等，比如根据订单状态判断是否被处理了
> 2. 本地记录对应分区的offset
> 3. 设置手动提交

## 数据丢失

> 1. 上次poll了之后数据还没处理完，就被自动提交了 
> 2. 发送过大的数据
> 3. 数据还没同步到从节点就宕机了



