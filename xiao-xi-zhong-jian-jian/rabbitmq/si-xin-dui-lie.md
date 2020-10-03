## 死信队列

## 资料

> [https://www.cnblogs.com/lyc88/articles/11232098.html](https://www.cnblogs.com/lyc88/articles/11232098.html)

## 消息变成死信的几种情况

> 消息TTL到期
>
> 消息被拒
>
> 队列到了最大长度

## 简述

> 消息和队列可以设置过期时间，消息过期后，会被转发到死信交换机，再由死信交换机分发到死信队列，然后正常消费



