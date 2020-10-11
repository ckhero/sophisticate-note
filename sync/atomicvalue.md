# Atomic.Value

> https://studygolang.com/articles/23242?fr=sidebar



## 原子操作

> 一个或者多个操作不会被打断

## 思想

> 为了完成多个字段的原子性写入，我们可以抓住一个字段的状态

## 简述

> store的时候会把value利用unsafe.Pointer转成iface



