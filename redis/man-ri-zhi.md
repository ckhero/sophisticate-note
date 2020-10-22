# 慢日志

> [http://redisbook.com/preview/slowlog/content.html](http://redisbook.com/preview/slowlog/content.html)

## 命令

> ```
> CONFIG SET slowlog-log-slower-than 0 // 设置慢日志阈值
> ```
>
> ```
> CONFIG SET slowlog-max-len 5 // 慢日志条数
> ```
>
> ```
> SLOWLOG GET // 获取具体的慢日志
> ```



