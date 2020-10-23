# RedoLog

> [https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html](https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html)

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

> 1. binlog由引擎层的上层产生，RedoLog由innnodb产生
> 2. binlog是在commit的一次性写入缓冲，redolog在数据准备修改前开始写入缓存，再binlog的commit前进行提交



