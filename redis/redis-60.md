# Redis 6.0

## 资料

> [https://segmentfault.com/a/1190000020031841?utm\_source=tag-newest](https://segmentfault.com/a/1190000020031841?utm_source=tag-newest)
>
> 多线程 [https://cloud.tencent.com/developer/article/1483779](https://cloud.tencent.com/developer/article/1483779)

## 多线程

> * 多线程只是用来处理网络数据和协议解析，执行命令还是单线程
> * 流程
>   1. 主线程负责建立连接，读事件到来则放入一个全局等待读队列
>   2.



