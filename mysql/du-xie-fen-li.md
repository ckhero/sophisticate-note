# 读写分离

## 资料

> [https://blog.csdn.net/liyuxing6639801/article/details/90582565](https://blog.csdn.net/liyuxing6639801/article/details/90582565)

## 主从同步

> * master把变化写入bin\_log
>
> * slave连接到master的时候,master创建bin_log dump线程，bin_\_log发生变化的时候，master通知salve，并推送给slave
>
> * slave接收到后写入relay\_log
>
> * slave另外一个线程会从relay\_log中读取进行同步操作

## 如何防止数据丢失？

> 开启半同步复制，至少数据写入一个slave的relay\_log 才算成功，等待的时候有超时时间。超过超时时间后同步转异步

## 如何防止数据延迟？

> 开启并行复制。
>
> 5.6数据库是库级别的并行复制
>
> 5.7之后master怎么写入的，slave就怎么写入



