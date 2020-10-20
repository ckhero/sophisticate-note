# Redis 6.0

## 资料

> [https://segmentfault.com/a/1190000020031841?utm\_source=tag-newest](https://segmentfault.com/a/1190000020031841?utm_source=tag-newest)
>
> 多线程 [https://cloud.tencent.com/developer/article/1483779](https://cloud.tencent.com/developer/article/1483779)

## 多线程

> * 多线程只是用来处理网络数据和协议解析，执行命令还是单线程
> * 流程
>   1. 主线程负责建立连接，读事件到来则放入一个全局等待读队列
>   2. 主线程处理完读事件后，通过RR（round robin）将这些分配给IO线程，然后主线程忙等待
>   3. IO把把数据读取并且解析完成
>   4. 主线程执行所有命令并且清空整个读队列
> * 整个过程无无锁，IO处理的时候主线程会等全部IO完成，所以不存在data race



