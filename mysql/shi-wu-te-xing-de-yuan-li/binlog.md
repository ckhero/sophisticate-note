# Binlog

> https://database.51cto.com/art/202008/624307.htm

## 刷盘

> * 提交的时候写入缓冲，sync\_binlog线程控制刷盘时机。
>
> * 刷盘策略
>   * 0  系统自行判断刷盘时机
>   * 1 每次commit都刷盘
>   * N 每N次提交事务刷盘



