# context

> [https://zhuanlan.zhihu.com/p/110085652](https://zhuanlan.zhihu.com/p/110085652)

## 简述

> 主要用于父子协程之间的取消信号。是一种协程的调度方式。上有任务及仅仅是通知下游任务不再需要。而不会干涉下游任务的执行。

## 知识点

> 1. context.Background\(\) 和context.TODO\(\)
>    1. 本质上没有区别，都是实例化emptyCtx
>    2. Back..适用于主函数
>    3. TODO适用于不知道用什么ctx的时候

## WithValue

> 不是在原来的ctx上直接添加。而是以原来的作为父节点。添加一个valueCtx

## WithCancel

> 1. cancelCtx
>
>    1. done channel，用来传递关闭信号
>
>    2. children  map  存储当前节点的子节点
>
> 2. withCancel
>
>    1. 基于父节点创建 cancelCtx
>
>    2. 然后把当前节点加入到最近的cancelCtx的祖先节点的child当中
>
>    3. 节点取消的时候会遍历 children map  进行取消操作



