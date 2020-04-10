# String

## 资料

> [https://blog.csdn.net/wj1314250/article/details/92794412](https://blog.csdn.net/wj1314250/article/details/92794412)
>
> [https://blog.csdn.net/qq193423571/article/details/81637075](https://blog.csdn.net/qq193423571/article/details/81637075)

## 简述

> SDS动态字符串，结构体  字段 len，free，buf\[\]

## 存入int？

## 特点

> * 预分配空间，惰性删除

## 扩容

> 小于1m的时候扩容因子为2，大于1m的时候每次增加1m

## 优点

> * 常数时间复杂度获取字符串长度
> * 预分配空间，减少内存分配次数
> * 动态扩容，不用担心内存溢出



