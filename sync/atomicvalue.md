# Atomic.Value

> [https://studygolang.com/articles/23242?fr=sidebar](https://studygolang.com/articles/23242?fr=sidebar)

## 原子操作

> 一个或者多个操作不会被打断

## 思想

> 为了完成多个字段的原子性写入，我们可以抓住一个字段的状态

## 简述

> store的时候会把value利用unsafe.Pointer转成ifaceWords ，因为value是interface所以和 ifaceWords结果本质是一致的 。
>
> 然后里判断ifaceWords的type是否为nil，如果未nil，继续往下走，利用硬件层面的swap把type设置为中间状态。第二请求进来的时候因为ifaceWords为中间状态所以无法完成写入，达到原子性

## 扩展

> mutex由操作系统提供，atomic由底层硬件直接提供支持



