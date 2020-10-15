# 分布式事务

## 资料

> [https://developer.51cto.com/art/201808/581174.htm](https://developer.51cto.com/art/201808/581174.htm)
>
> rocketmq [https://www.jianshu.com/p/286cac4625b6](https://www.jianshu.com/p/286cac4625b6)
>
> 2pc [https://www.cnblogs.com/wudimanong/p/10340948.html](https://www.cnblogs.com/wudimanong/p/10340948.html)
>
> 消息中间间分布式 [https://www.cnblogs.com/wudimanong/p/10558710.html](https://www.cnblogs.com/wudimanong/p/10558710.html)
>
> [https://zhuanlan.zhihu.com/p/93008976](https://zhuanlan.zhihu.com/p/93008976)
>
> 详细 https://xiaomi-info.github.io/2020/01/02/distributed-transaction/

## 简述

> 本质上是多个数据库的事务的统一控制，按照粒度可以分为不控制，部分控制，完全控制。不控制就是不引入分布式事务，部分控制就是各种变种的两段提交，（消息事务 + 最终一致性， TCC模式）
>
> 部分控制好处是并发量和性能变好了，缺点是一致性变弱了。w安全控制是牺牲性能，保证一致性

## XA

> [https://www.cnblogs.com/zengkefu/p/5742617.html](https://www.cnblogs.com/zengkefu/p/5742617.html)

## TCC

> try confirm cancel
>
> 2PC是数据库层面的两段提交，TCC是业务逻辑层面的两段提交

## 消息中间件

> 保证最终的一致性



