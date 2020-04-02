# list

## 资料

> [https://www.cnblogs.com/javazhiyin/p/11063944.html](https://www.cnblogs.com/javazhiyin/p/11063944.html)

> 数据对象小于64字节 & 数据对象个数小于512 使用 ziplist，否则使用双链表

## 结构

> typedef struct list{
>
> //表头节点
>
> listNode \*head;
>
> //表尾节点
>
> listNode \*tail;
>
> //链表所包含的节点数量
>
> unsigned long len;
>
> //节点值复制函数
>
> void \(\*free\) \(void \*ptr\);
>
> //节点值释放函数
>
> void \(\*free\) \(void \*ptr\);
>
> //节点值对比函数
>
> int \(\*match\) \(void \*ptr,void \*key\);
>
> }list;

## 特点

> * 双向链表
> * 可以直接获得头部和尾部
> * 常数是将复杂度获得长度



