kafka

## 资料

> 为什么高吞吐？ [https://www.jianshu.com/p/30036748174a](https://www.jianshu.com/p/30036748174a)
>
> 消费者的三种模式 [https://baijiahao.baidu.com/s?id=1647192820875012954픴=spider&for=pc](https://baijiahao.baidu.com/s?id=1647192820875012954&wfr=spider&for=pc)

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



