kafka

## 资料

> 为什么高吞吐？ [https://www.jianshu.com/p/30036748174a](https://www.jianshu.com/p/30036748174a)
>
> 消费者的三种模式 [https://baijiahao.baidu.com/s?id=1647192820875012954픴=spider&for=pc](https://baijiahao.baidu.com/s?id=1647192820875012954&wfr=spider&for=pc)
>
> 精确一次 [https://blog.csdn.net/lzufeng/article/details/81906031](https://blog.csdn.net/lzufeng/article/details/81906031)
>
> [https://cloud.tencent.com/developer/article/1530090](https://cloud.tencent.com/developer/article/1530090)
>
> [https://www.zhihu.com/search?type=content&q=kafka原理](https://www.zhihu.com/search?type=content&q=kafka原理)

## 优点

> 1** 快速持久化**，通过磁盘顺序读写和零拷贝机制，可以再O\(1\)的开销下j进行持久化
>
> 2 **高吞吐** 一台普通的机器就能达到10w/s的吞吐
>
> 3 **高堆积** 支持消费者长时间的离线。消息堆积量大
>
> 4 **完全的分布式**  Broker Producer Consumer都支持原生自动分布式，依赖zookeeper自动实现负载均衡
>
> 5 **支持Hadoop数据并行加载**

## 为什么高吞吐？

> * 磁盘顺序读写
> * 零拷贝
> * 数据以分区形式存放
> * 批量压缩

## kafka事务

> * 原子性的体现是，生产者将多条消息一次向broker的多分区写入，要么都成功，要么都失败

## 精确一次

> * 为每个生产者分配一个PID
> * 用序列号标记发送的消息，这个序列号严格递增。broker会去校验这个序列号

## 分区选择

> 1. 指定分区
> 2. 设置partion-key
> 3. 轮询



