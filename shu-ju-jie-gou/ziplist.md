# ziplist

## 资料

> [https://blog.csdn.net/qiangzhenyi1207/article/details/80353104](https://blog.csdn.net/qiangzhenyi1207/article/details/80353104)
>
> [https://segmentfault.com/a/1190000016901154](https://segmentfault.com/a/1190000016901154)

## 简述

> 一个经过特殊编码的双向链表。不能存指向上一个节点和下一个节点的指针，而是存上个节点的长度和当前节点的长度。牺牲部分的读写性能，来换取高效的内存空间使用率。时间换空间。只用在字段数量少，值较小的场景



