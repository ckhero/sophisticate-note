# 限流

> https://www.cnblogs.com/biglittleant/p/8979915.html

## 命令

> `limit_req_zone $binary_remote_addr zone=one:10m rate=1r/s;`
>
> * 第一个参数：$binary\_remote\_addr 表示通过remote\_addr这个标识来做限制，“binary\_”的目的是缩写内存占用量，是限制同一客户端ip地址。
> * 第二个参数：zone=one:10m表示生成一个大小为10M，名字为one的内存区域，用来存储访问的频次信息。
> * 第三个参数：rate=1r/s表示允许相同标识的客户端的访问频次，这里限制的是每秒1次，还可以有比如30r/m的。
>
> `limit_req zone=one burst=5 nodelay;`
>
> * 第一个参数：zone=one 设置使用哪个配置区域来做限制，与上面limit\_req\_zone 里的name对应。
> * 第二个参数：burst=5，重点说明一下这个配置，burst爆发的意思，这个配置的意思是设置一个大小为5的缓冲区当有大量请求（爆发）过来时，超过了访问频次限制的请求可以先放到这个缓冲区内。
> * 第三个参数：nodelay，如果设置，超过访问频次而且缓冲区也满了的时候就会直接返回503，如果没有设置，则所有请求会等待排队。



