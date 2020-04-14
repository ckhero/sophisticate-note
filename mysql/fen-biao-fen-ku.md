# 分表分库

## 资料

> [https://www.cnblogs.com/aksir/p/9085694.html](https://www.cnblogs.com/aksir/p/9085694.html)
>
> [https://www.cnblogs.com/aksir/p/9085694.html](https://www.cnblogs.com/aksir/p/9085694.html)

## 简述

> * 垂直分表 不常用的，较大的字段放到扩展表
> * 垂直分库 针对不同的业务场景分库
> * 水平分表  按照某种规则 大表变小表。但是这些表还是同一个库 ,库级别还是有IO瓶颈
> * 水平分表分库 将切割的表分到不同的库里面去，突破单库的性能瓶颈压力，突破io，连接数，硬件资源等的瓶颈
> *



