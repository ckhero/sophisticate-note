# 单表最大

## 资料

> [https://www.cnblogs.com/niuben/p/11250191.html](https://www.cnblogs.com/niuben/p/11250191.html)
>
> [https://blog.csdn.net/n88lpo/article/details/86486263](https://blog.csdn.net/n88lpo/article/details/86486263)

## 简述

> 为了提高性能，会把索引加载到内存中。innodb buffer size 足够大的情况下，其能完全加载进内存。当单表到一定数据量之后，导致内存无法存储其索引，使得之后的查询会产生磁盘 IO，从而导致性能下降。
>
> 阿里巴巴推荐500万行 2g做分表分库



