# 并发模型

> https://cloud.tencent.com/developer/article/1349213

## 类型

> 1. 单进（线）程，循环处理
> 2. 多进程
>    1. apache
>    2. php-fpm ，子进程抢占式处理请求
> 3. 多线程
> 4. 单线程 加 回调（callback）和事件轮询
>    1. nginx 多进程（单线程） & 多路复用



