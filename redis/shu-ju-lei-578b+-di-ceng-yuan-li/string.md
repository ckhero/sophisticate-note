# String

## 资料

> [https://blog.csdn.net/wj1314250/article/details/92794412](https://blog.csdn.net/wj1314250/article/details/92794412)
>
> [https://blog.csdn.net/qq193423571/article/details/81637075](https://blog.csdn.net/qq193423571/article/details/81637075)
>
> [https://www.jianshu.com/p/975bd36f68ea](https://www.jianshu.com/p/975bd36f68ea)
>
> [https://www.cnblogs.com/instant7/p/12586334.html](https://www.cnblogs.com/instant7/p/12586334.html)
>
> [https://blog.csdn.net/beijing20120926/article/details/16338149](https://blog.csdn.net/beijing20120926/article/details/16338149)

## 简述

> SDS动态字符串，结构体  字段 len，free，buf\[\]

## 编码格式

> * 当存储是64位有符号整型的时候使用 int编码
> * 当存储的字符串长度 len&lt;= 44 使用 embstr编码，将SDS结构体嵌入RedisObject对象。内存地址连续
> * 长度大图 len&gt;44 使用raw编码，SDS结构体和RedisObject分开。内存地址不连续

## 存入int？

## 特点

> * 预分配空间，惰性删除

## 扩容

> 小于1m的时候扩容因子为2，大于1M的时候每次增加1M

## 优点

> * 常数时间复杂度获取字符串长度
> * 预分配空间，减少内存分配次数
> * 动态扩容，不用担心内存溢出



