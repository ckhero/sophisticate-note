# 调试工具

> [https://github.com/fullstorydev/grpcui](https://github.com/fullstorydev/grpcui)
>
> [https://chai2010.cn/advanced-go-programming-book/ch4-rpc/ch4-08-grpcurl.html](https://chai2010.cn/advanced-go-programming-book/ch4-rpc/ch4-08-grpcurl.html)
>
> https://github.com/uw-labs/bloomrpc

## 步骤

> 1. go get github.com/fullstorydev/grpcui
> 2. go install github.com/fullstorydev/grpcui/cmd/grpcui
> 3. grpcui -plaintext localhost:12345

## 依赖

> 1. 需要开启反射服务
>    1. reflection.Register\(r.server\)

## BloomRpc

> ```
> npm run start-server-dev
> npm run start-main-dev
> ```



