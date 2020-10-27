# 恐慌恢复

> [https://gfw.go101.org/article/panic-and-recover-more.html](https://gfw.go101.org/article/panic-and-recover-more.html)
>
> 好文 [https://xiaomi-info.github.io/2020/01/20/go-trample-panic-recover/](https://xiaomi-info.github.io/2020/01/20/go-trample-panic-recover/)

## Recover Nil

> 1. panic实参为 nil
> 2. 没有 恐慌
> 3. recover 位置错误

## Recover的有效调用

> * recover调用的父级调用是一个延迟调用，并且延迟调用的父级调用和协程内未恢复的最新恐慌关联起来才起作用
> * 同一个协程内有效

## 异常

> map并发读写
>
> 数组越界
>
> 空指针
>
> 关闭已经关闭的channel，向已经关闭的channel发送数据



