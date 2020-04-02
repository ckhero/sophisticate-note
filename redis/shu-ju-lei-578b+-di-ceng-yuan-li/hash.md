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
>
> 渐进式rehash 的详细步骤：
>
> 　　　　　　1、为ht\[1\] 分配空间，让字典同时持有ht\[0\]和ht\[1\]两个哈希表
>
> 　　　　　　2、在几点钟维持一个索引计数器变量rehashidx，并将它的值设置为0，表示rehash 开始
>
> 　　　　　　3、在rehash 进行期间，每次对字典执行CRUD操作时，程序除了执行指定的操作以外，还会将ht\[0\]中的数据rehash 到ht\[1\]表中，并且将rehashidx加一
>
> 　　　　　　4、当ht\[0\]中所有数据转移到ht\[1\]中时，将rehashidx 设置成-1，表示rehash 结束





