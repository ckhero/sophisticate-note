# Cluster 模式

> 资料 [https://blog.csdn.net/hguisu/article/details/82979320](https://blog.csdn.net/hguisu/article/details/82979320)
>
> [https://zhuanlan.zhihu.com/p/142843518](https://zhuanlan.zhihu.com/p/142843518)

## 简述

> 哨兵模式的缺点是每个slave都存了全部的数据，比较浪费空间
>
> cluster引入哈希槽的概念。 0 ~ 1616383，每个master负责一部分的槽
>
> 对key 用crc16进行hash 得到结果再用 1616384 取模确定存放的位置
>
> **Gossip 协议有 meet，pong，ping组成 三次握手**

## 请求重定向

> MOVED错误
>
> ```
> 1  请求d额key不在该节点，节点检查映射关系，回复MOVED错误
>
>  2 客户端拿到MOVED错误去向新的节点请求 ，我的理解这时候应该会刷新客户端里面的id和节点映射关系
> ```
>
> ASK错误
>
> 1 请求的槽属于MIGRATING状态，key不存在，节点返回ASK让去客户端去对应的IMPORTING节点试试
>
> ```
> 2 客户端向IMPORTING节点发起ASKING的命令请求
>
>  3 不必更新客户端记录的槽至节点的映射，一次性的
> ```

## 数据迁移

> node1 -&gt; node2 node1标记为migrating 。node2标记为importing
>
> 请求node1
>
> 1 存在 直接返回
>
> 2 不存在返回ask，再向node2发起asking
>
> 3 多个命令
>
> ```
>  都存在，直接返回
>
>  都不存在返回ask
>
> 部分存在返回trying ，然后等服务端迁移完毕之后会得到ask，然后进行重定向
> ```
>
> 不刷新客户的key和node映射
>
> 请求node2
>
> 以下部分自己的理解，感觉文章写的有问题，欢迎纠正
>
> 1 存在则返回
>
> 2 不存在则创建
>
> 3 asking直接执行

## 故障检测

> 如果一个节点认为另一个节点宕机，则x先主观下线。如果多个节点都认为主观下线了。则正式下线。然后开始重新选举

## 多个从节点选主

> 选新主的过程基于简易版的Raft协议选举方式来实现的
>
> 1 从节点检测到主节点下线后，会广播给其他 主节点 。收到消息的主节点如果未给其他从节点投票。则给这个 从节点投票。当从节点收到半数以上的票的时候则成为新的maser



