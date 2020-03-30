# HTTP2

## 资料

> [https://developers.google.com/web/fundamentals/performance/http2/?hl=zh-cn](https://developers.google.com/web/fundamentals/performance/http2/?hl=zh-cn)

## 核心 - 二进制分帧层

> 定义如何封装http消息并在客户端和服务端之间传输
>
> 这里所谓的“层”，指的是位于套接字接口与应用可见的高级 HTTP API 之间一个经过优化的新编码机制：HTTP 的语义（包括各种动词、方法、标头）都不受影响，不同的是传输期间对它们的编码方式变了。 HTTP/1.x 协议以换行符作为纯文本的分隔符，而 HTTP/2 将所有传输的信息分割为更小的消息和帧，并采用二进制格式对它们编码。



