# RedoLog

> [https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html](https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html)
>
> [https://database.51cto.com/art/202008/624307.htm](https://database.51cto.com/art/202008/624307.htm)

## 简述

> mysql持久性的保证，mysql事务写入缓冲之前写入redo  buffer，然后再提交

## 两部分

> 1. 内存中的日志缓冲，容易失控
> 2. 磁盘上的重做文件

## 流程

> * 角色
>   * redo buffer   用户缓冲区
>   * os buffer 内核缓冲区
>   * redo log 日志文件
> * redos buffer  -&gt; os buffer -&gt; redo log

## 策略

> innodb\_flush\_log\_at\_trx\_commit
>
> 1. 1  事务提交会把 log buffer 中的数据写入 os buffer
> 2. 0 事务提交不会把log buffer 写入 os buffer，而是每秒写入 os buffer
> 3. 2 每次提交都仅仅写入到 os buffer，然后 每秒写入 log file

## RedoLog与binLog的区别

> 1. 作用不同
>    1. binlog用于基于时间点的回复，和主从复制
>    2. redolog适用于崩溃恢复，保证数据持久性
> 2. 层次不同
>    1. binlog由引擎层的上层mysql服务器
>    2. redolog是innodb存储引擎实现的
> 3. 写入时机不同
>    1. binglog在提交的时候一次性写入缓存
>    2. redolog在准备数据的时候就开始写入缓存，在binglog提交前提交
> 4. 内容不同
>    1. redo log 是物理日志，记录的是个每个物理页的变化
>    2. binlog是逻辑性的语句

## 有binlog为什么还要redolog

> 1. inndodb是以页单位进行磁盘交互，而一个事务很可能只修改了一个数据页里的几个字节，这时候将完整的数据页刷到磁盘的话。浪费资源
> 2. 一个事务可能修改多个数据页，这些数据页在磁盘上不连续，随机IO写入性能太差
> 3. redolog只记录事务对数据页做了哪些修改，相对而言文件较小也是顺序IO



