# 队首阻塞

## 资料

> [https://www.cnblogs.com/hustdc/p/8487366.html](https://www.cnblogs.com/hustdc/p/8487366.html)

## 简述

> http1.0 发生在客户端，要等前一个请求完成后才能发送后一个请求
>
> http1.1 发生在服务端，先到的请求要先响应
>
> http2 二进制分帧层，并行交错发送多个请求，互相不干扰。并行交错响应多个请求，互相不影响。 只有丢包的时候会出现队首阻塞



