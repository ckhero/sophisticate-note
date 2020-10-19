# 恐慌恢复

> https://gfw.go101.org/article/panic-and-recover-more.html

## Recover Nil

> 1. panic实参为 nil
> 2. 没有 恐慌
> 3. recover 位置错误

## Recover的有效调用 

> recover调用的父级调用是一个延迟调用，并且延迟调用的父级调用和协程内未恢复的最新恐慌关联起来才起作用





