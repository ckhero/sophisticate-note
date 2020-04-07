ETCD

## 资料

> [https://zhuanlan.zhihu.com/p/96428375?from\_voters\_page=true](https://zhuanlan.zhihu.com/p/96428375?from_voters_page=true)
>
> [https://segmentfault.com/a/1190000020742981](https://segmentfault.com/a/1190000020742981)

## 简述

> 分布式，靠key-value存储的分布式系统，不仅提供存储系统，还提供配置共享和服务发现
>
> 通过 raft算法报纸一致性，3各节点1故障，5个节点2个故障，一个主节点多个从节点

## 主节点

> Raft利用Timer来初始化选举流程，率先完成初始化的会给其他节点发送成为主节点的请求。其他节点收到后给他投一票

## 写入成功

> 写请求被主节点处理并且发送给多数节点，就是一个成功的写入。多数节点指 Quorum=N/2+1
>
> 因此推荐的节点节点



