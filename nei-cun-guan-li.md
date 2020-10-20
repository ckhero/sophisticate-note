# 内存管理

> [https://tonybai.com/2020/03/10/visualizing-memory-management-in-golang/](https://tonybai.com/2020/03/10/visualizing-memory-management-in-golang/)

## 简述

> * golang将内存划分为8KB大小的内存页
> * mspan
>   * mheap管理内存页的基本结构
>   * 是一个双向列表
>   * 包含页的起始位置，span size class 和span中页数量，
>   * mspan被分为67个列别，从8byte到32KB
>   * 每个span对应两个，一个scan class，一个 noscan class。再GC时候，noscan class 无需遍历span
> * mcentral
>   * 将相同类别的span 归类到一起。每个mcentral包含两个spanlist
>   * empty
>     * 包含没有空闲对象的span或缓存mcache中的span，此处的span被释放的时候，被移动到non-empty链表
>   * non-empty
>     * 有空闲对象的span双向链表，从mcentral申请span的，mcentral从该链表中获取span移动到empty
>     * mcentral没有空闲对象的时候，从mheap中申请



