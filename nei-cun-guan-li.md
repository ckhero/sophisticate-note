# 内存管理

> [https://tonybai.com/2020/03/10/visualizing-memory-management-in-golang/](https://tonybai.com/2020/03/10/visualizing-memory-management-in-golang/)

## 简述

> * golang将内存划分为8KB大小的内存页
> * mspan是mheap管理内存页的基本结构，是一个双向列表，包含页的起始位置，span size class 和span中页数量，mspan被分为67个列别，从8byte到32KB
>   \*



