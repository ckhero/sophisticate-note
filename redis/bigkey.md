# BigKey

> [https://www.cnblogs.com/os-linux/p/11928930.html](https://www.cnblogs.com/os-linux/p/11928930.html)
>
> [https://www.cnblogs.com/evakang/p/11610087.html](https://www.cnblogs.com/evakang/p/11610087.html)

## 问题

> 数据倾斜，部分实例内存不够用

## 解决

> 分而治之，分段处理

## 发现

> 1. redis-cli -h -a --bigkeys
> 2. 下载rdb文件本地复原，在查看
> 3. d第三方工具redis-rbd-cli

## redis4.0之后大key的发现和删除

>

