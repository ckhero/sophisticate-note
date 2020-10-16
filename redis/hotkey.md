# HotKey

## 资料

> [https://segmentfault.com/a/1190000019745366?utm\_source=tag-newest](https://segmentfault.com/a/1190000019745366?utm_source=tag-newest)
>
> [https://blog.csdn.net/youanyyou/article/details/91697975](https://blog.csdn.net/youanyyou/article/details/91697975)

## 监控

> 1. 通过具体业务判断
> 2. client端统计
> 3. 代理层统计
> 4. redis-cli --hostkeys

## 问题？

> 数据倾斜，导致k服务不可用

## 解决

> 1. 二级缓存，代码端
> 2. 生成多个key，放到不同的redis实例



