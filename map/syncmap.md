# sync.Map

> [https://studygolang.com/articles/30515](https://studygolang.com/articles/30515)
>
> 坑 [https://zhuanlan.zhihu.com/p/198984827?utm\_source=wechat\_session&utm\_medium=social&utm\_oi=597821804883218432&utm\_campaign=shareopn](https://zhuanlan.zhihu.com/p/198984827?utm_source=wechat_session&utm_medium=social&utm_oi=597821804883218432&utm_campaign=shareopn)

## 结构

> ```
> type Map struct {
>     mu Mutex
>     read atomic.Value // readOnly
>     dirty map[interface{}]*entry
>     misses int
> }
> ```

## 简述

> \*entry有三种状态，nil，expunged，正常状态
>
> nil表示被删除，dirty为nil或者dirty指向entry
>
> expunged 表示帧的被删除了
>
> 正常状态

## 坑

> 如果删除的key再 read map里面，不会真的删除key，而是把val改为nil，容易导致OOM

## 为什么安全

> 1. 有一只读map，atomic.Value类型和一个线程不安全的map
> 2. 如果元素不存在。并发读写的时候，会加锁，然后对线程不安全的map进行操作
> 3. 如果元素存在的时候，读操作利用atomic.Value的原子操作load，写操作利用自旋的CAS进行原子更新，原子操作不会被打断



