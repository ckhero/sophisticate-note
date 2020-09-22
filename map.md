
---

map

数组加+链表

overflow 对应0 是工作的bucket数组，1对应旧的bucket数组，因为扩容后，map进行的是增量迁移。

扩容

加载因子导致的 扩容两倍

溢出桶导致的等量扩容（溢出桶是一个链表，处理哈希冲突 最大为8）

## 资料

> [https://blog.csdn.net/bluehawksky/article/details/90448023](https://blog.csdn.net/bluehawksky/article/details/90448023)
>
> [https://studygolang.com/articles/23562](https://studygolang.com/articles/23562)

## 遍历无序？

> [https://studygolang.com/articles/21118](https://studygolang.com/articles/21118)
>
> 遍历前先生成一个数据数，因为不同版本的迭代遍历规则不一致，所以，所以干脆直接无序遍历
>
> 可以通过把key放在数组里面变的有序

## key类型

> 任何类型，只要他的key可以比较，除了slice，map，function



