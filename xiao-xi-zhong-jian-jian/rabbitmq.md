# rabbitMq

## 资料

> [https://www.cnblogs.com/lyc88/articles/11232098.html](https://www.cnblogs.com/lyc88/articles/11232098.html)
>
> [https://zhuanlan.zhihu.com/p/79385336](https://zhuanlan.zhihu.com/p/79385336)
>
> [https://blog.csdn.net/qq\_30905661/article/details/82835765](https://blog.csdn.net/qq_30905661/article/details/82835765)  对比

## Exchange

> direct  根据route key 点对点直接发送
>
> fanout 将同一个消息发送给所有与他绑定的队列
>
> topic  根据key 模糊匹配后投递到响应的队列

## QUEUE

> 消息的载体，每个消息都会被投递到一个或者多个队列

## Binding

> 把exchange和queue按照规则绑定起来

## Routing Key

> exchange根据这个关键字进行投递

## vhost

> 一个broker里有多个虚拟机，用作不同的用户的权限管理

## Channel

> 消息通道，在客户端的每个连接里，可以建立多个channel



## 消息持久化

> 持久化的队列
>
> 设置临时队列
>
> 自动删除的队列

## 消息确认机制

> 1. 客户端发送ack，或者autoack
> 2. 消息消费确认后，会被删除

## 消息分发机制

> 多个消费者，消息循环分发

本身支持很多的协议：AMQP，XMPP, SMTP,STOMP

AMQP是最可靠的协议

消息确认

消息持久化

延时队列

