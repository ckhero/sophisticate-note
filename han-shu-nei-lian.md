# 函数内联

## 资料

> [https://zhuanlan.zhihu.com/p/137850288](https://zhuanlan.zhihu.com/p/137850288)

## 是什么

> 把简短函数放到调用它的地方展开

## 为什么

> 1. 消除函数本身调用的开销
> 2. 使编译器高效的执行他的优化策略

## 命令

> * ```
>   go build -gcflags=-m=2 inline.go
>   //go:noinline
>   ```



