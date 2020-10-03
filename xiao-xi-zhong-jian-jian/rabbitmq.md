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
> topic  根绝路由的key发送

本身支持很多的协议：AMQP，XMPP, SMTP,STOMP

AMQP是最可靠的协议

消息确认

消息持久化

延时队列

