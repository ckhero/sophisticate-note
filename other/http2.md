# HTTP2

## 资料

> [https://developers.google.com/web/fundamentals/performance/http2/?hl=zh-cn](https://developers.google.com/web/fundamentals/performance/http2/?hl=zh-cn)
>
> [https://blog.csdn.net/qq\_41635167/article/details/89484445](https://blog.csdn.net/qq_41635167/article/details/89484445)
>
> [https://www.jianshu.com/p/13c68c56a78f](https://www.jianshu.com/p/13c68c56a78f)
>
> [https://blog.csdn.net/howgod/article/details/102597450](https://blog.csdn.net/howgod/article/details/102597450)

## 核心 - 二进制分帧层

> 定义如何封装http消息并在客户端和服务端之间传输
>
> 这里所谓的“层”，指的是位于套接字接口与应用可见的高级 HTTP API 之间一个经过优化的新编码机制：HTTP 的语义（包括各种动词、方法、标头）都不受影响，不同的是传输期间对它们的编码方式变了。 HTTP/1.x 协议以换行符作为**纯文本的分隔符**，而 HTTP/2 将所有传输的信息分割为**更小的消息和帧，并采用二进制格式对它们编码**。

## 数据流 ，消息和帧

> 数据流  已建立的双向字节流，可以承载一条或多条消息
>
> 消息 与逻辑请求和响应对应的一些列的帧
>
> 帧  http2通信的最小单位，包含帧头和所属的数据流
>
> 所有通信都在一个tcp请求上完成，此链接可以承载任意数量的双向数据流
>
> 每个数据流都一个唯一的标识符和优先级信息，用于承载双向消息
>
> 每条消息都是一个逻辑http消息，包含一个或多个帧
>
> 帧是最小的单位，不同的消息的帧可以交互发送

## 请求和响应

> * 并行交错发送多个消息
> * 并行响应多个消息
> * 一个链接内，可以并行发送和响应多个消息
> * 消除不必要的延迟和提高网络容错的利用率，从而减少页面加载时间

## 数据流优先级 {#%E6%95%B0%E6%8D%AE%E6%B5%81%E4%BC%98%E5%85%88%E7%BA%A7}

## 每个来源一个连接 {#%E6%AF%8F%E4%B8%AA%E6%9D%A5%E6%BA%90%E4%B8%80%E4%B8%AA%E8%BF%9E%E6%8E%A5}

> 有了分帧机制，不再依赖多个tcp链接去并行复用数据流

## HTTP2和HTTP的区别

> * http2采用二进制格式而非文本格式
> * http2 多路复用，而非有序阻塞的，一个连接只处理一个请求
> * 使用报头压缩，降低开销
> * http2会主动推送响应到客户端

## 缺陷

> 1. 丢包重传的时候会阻塞整个TCP链接，比http1.1耗时更多，因为http1.1可以开启多个链接值阻塞其中一个
> 2. 使用https的时候还有一个TLS的握手过程，TCP 耗时1.5RTT，TLS耗时1-2个RTT



