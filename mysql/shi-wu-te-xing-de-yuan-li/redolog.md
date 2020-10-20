# RedoLog

> [https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html](https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html)

## 简述

> mysql持久性的保证，mysql事务写入缓冲之前写入redo  buffer，然后再提交

## 两部分

> 1. 内存中的日志缓冲，容易失控
> 2. 磁盘上的重做文件

## 角色

> * redo buffer   用户缓冲区
> * os buffer 内核缓冲区



