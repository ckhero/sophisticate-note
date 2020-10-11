# sync.Map

> [https://studygolang.com/articles/30515](https://studygolang.com/articles/30515)

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


