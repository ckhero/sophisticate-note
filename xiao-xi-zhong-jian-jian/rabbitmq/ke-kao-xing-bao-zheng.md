# 事务

> [https://blog.csdn.net/hzw19920329/article/details/54340711](https://blog.csdn.net/hzw19920329/article/details/54340711)
>
> [https://blog.csdn.net/hzw19920329/article/details/54315940](https://blog.csdn.net/hzw19920329/article/details/54315940)

## 基于AMQP的事务

> 提供txSelect\(\)，txCommit\(\)以及txRollback\(\)，如果commit失败则进行Rollback，如果rollBack失败我理解的是没有commit的消息不会被消费者看到

## channel的confirm模式

> 发送消息，异步回调结果，ACK或者nack。发送失败
>
> * 普通confirm
>   * 串行的，发送失败重试
> * 批量发送，每个消息分配单调递增的序列号
>   * 批量发送后，失败重试，选择性重试，有可能会导致重复消息



