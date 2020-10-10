# RocketMQ

> [https://www.jianshu.com/p/286cac4625b6](https://www.jianshu.com/p/286cac4625b6)

## 流程

> * 预备阶段      将消息发送到rocketmq，但消息只存储在commitLog中，消费端不可见
> * 本地事务
> * 确认阶段      小rocketmq发送确认消息，是之前的消息对消费端可见

## 异常

> 1. 预备阶段发送失败，流程不会走下
> 2. 本地事务失败，comitLog中的消息对消费端不可见
> 3. 确认阶段失败，rocketmq服务端会回查消息



![](/assets/rocketmq-2pc.png)

