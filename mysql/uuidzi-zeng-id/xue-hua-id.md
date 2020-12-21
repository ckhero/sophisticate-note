# 雪花ID

> [https://xie.infoq.cn/article/cf27b51c9e3cde1b2c585f0ec](https://xie.infoq.cn/article/cf27b51c9e3cde1b2c585f0ec)

## 优点

> 1. 全局唯一，全局有序
> 2. 占用空间少8字节

## 构成

> 64位，第一位不用，41是时间戳，10位机器标号，12位自增序列

## 问题

> 1. 时间回拨
>    1. 利用历史ID，当自增序列用完后，历史事件+1
> 2. workid的分配
>    1. zookeeper和DB，客户端维持心跳，数据设置过期时间



