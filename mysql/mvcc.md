# MVCC

## 资料

> [https://www.jianshu.com/p/8845ddca3b23](https://www.jianshu.com/p/8845ddca3b23)

## 简述

> 多版本并发控制。解决并发下的读写冲突问题，提高并发性能

## 实现

> 事务开启的时候会在undo\_log里面记录多个版本的数据。快照读读的是历史版本的数据



