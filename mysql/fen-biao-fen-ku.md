# 分表分库

## 资料

> [https://www.cnblogs.com/aksir/p/9085694.html](https://www.cnblogs.com/aksir/p/9085694.html)
>
> [https://zhuanlan.zhihu.com/p/83674503](https://zhuanlan.zhihu.com/p/83674503)
>
> 分页查询  [https://blog.csdn.net/uiuan00/article/details/102716457](https://blog.csdn.net/uiuan00/article/details/102716457)
>
> 简单查询 [https://zhuanlan.zhihu.com/p/83674503](https://zhuanlan.zhihu.com/p/83674503)

## 简述

> * 垂直分表 不常用的，较大的字段放到扩展表
> * 垂直分库 针对不同的业务场景分库
> * 水平分表  按照某种规则 大表变小表。但是这些表还是同一个库 ,库级别还是有IO瓶颈
> * 水平分表分库 将切割的表分到不同的库里面去，突破单库的性能瓶颈压力，突破io，连接数，硬件资源等的瓶颈

## 水平分表切分规则

> * range 
>
> 从0 - 100000， 100000- 20000
>
> * hash取模
>
> 根据用户id hash取模
>
> * 时间

## 分库分表面临的问题”

1. ## 分页查询

### 全局视野

> * order by time offset x limit y 改写成order by time offset 0 limit x \* y
> * 对取出的数据排序
> * 缺点  随着数据量变大，性能急剧下降

### 业务折中

> * ##### **禁止跳页**
> * ** **只能 跳下一页。得到前一页的time\_max
>
> * 每次跳页的时候 order by time offset x limit y 改写成 where time &gt; time\_max order by time offset x limit y
>
> * 特点  每次就返回一页数据
>
> * ##### 允许模糊数据
> * 每个库分配的数据是均匀的 order by time offset x limit y 改写成 order by time offset x/n limit y/n

### 二次查询

> 1 order by time offset X limit Y 改写成 order by time offset X/N limit Y/N
>
> 2 计算出time的范围
>
> 3 利用time的最大值和最小值去取数据
>
> 4 排序得到结果

## **非partition key的查询问题（水平分库分表，拆分策略为常用的hash法）**

> * 映射法  把partitio key 和非partitiion key 做映射

## MYCAT

> [https://blog.csdn.net/yinni11/article/details/82707757](https://blog.csdn.net/yinni11/article/details/82707757)



