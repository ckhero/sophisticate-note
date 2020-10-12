# context

> [https://zhuanlan.zhihu.com/p/110085652](https://zhuanlan.zhihu.com/p/110085652)

## 简述

> 主要用于父子协程之间的取消信号。是一种协程的调度方式。上有任务及仅仅是通知下游任务不再需要。而不会干涉下游任务的执行。

## WithValue

> 不是在原来的ctx上直接添加。而是以原来的作为父节点。添加一个valueCtx



