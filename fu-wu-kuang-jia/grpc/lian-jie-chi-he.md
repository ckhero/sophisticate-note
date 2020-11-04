# 连接池

> [http://xiaorui.cc/archives/6001](http://xiaorui.cc/archives/6001)
>
> [https://zhuanlan.zhihu.com/p/100200985](https://zhuanlan.zhihu.com/p/100200985)

## 为什么要用连接池

> * 网络引起的队头阻塞
> * golang rpc client的锁竞争

## Go-micro 中的grpc

> 1. 实例化连接池
> 2. 获取一个链接
> 3. 判断连接的过期时间ttl，如果超过的话选择下个可用连接
>    1. 如果没有活跃的stream，关闭链接
>    2. 因为服务端有超时机制，所以要关闭
> 4. 判断连接中的stream数量maxStreams，如果超过选择下个链接。
> 5. 建立连接
> 6. 释放的时候，如果连接池数量超标直接释放。



