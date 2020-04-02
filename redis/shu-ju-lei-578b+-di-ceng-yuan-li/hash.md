# hash

## 资料

> [https://zhuanlan.zhihu.com/p/87803810](https://zhuanlan.zhihu.com/p/87803810)

## 底层结构

> ziplist或者hashtable
>
> * 键和值得长度都小于64
> * 元素个数小于512个
>
> 满足上述两个条件使用压缩列表（ziplist）

## **存储（实现）原理**

> Redis 的 Hash 本身也是一个 KV 的结构，类似于 Java 中的 HashMap。
>
> 外层的哈希（Redis KV 的实现）只用到了 hashtable。当存储 hash 数据类型时，
>
> 我们把它叫做内层的哈希。内层的哈希底层可以使用两种数据结构实现：
>
> ziplist：OBJ\_ENCODING\_ZIPLIST（压缩列表）
>
> hashtable：OBJ\_ENCODING\_HT（哈希表）

## 扩容

> [https://www.jianshu.com/p/ea5a747ade5d](https://www.jianshu.com/p/ea5a747ade5d)



