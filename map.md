
---

map

数组加+链表

## overflow 对应0 是工作的bucket数组，1对应旧的bucket数组，因为扩容后，map进行的是增

## 量迁移。

扩容

加载因子导致的 扩容两倍

溢出桶导致的等量扩容（溢出桶是一个链表，处理哈希冲突 最大为8）

## 资料

> [https://studygolang.com/articles/30516](https://studygolang.com/articles/30516)
>
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

## 扩容

> ```
> 扩容因子：loadFactor := count / (2^B)
> ```
>
> 1. 两倍扩容:扩容因子大于6.5
> 2. 等量扩容:overflow的bucket过多，B小于15的时候 超过2^B扩容，超过15的时候超过2^15

## 为什么不安全

> 有个flags字段，有写操作的时候会被标记为1，如果还有其他线程进来的操作的话会报恐慌

## 初始化

> var a map\[string\]string
>
> a := map\[string\]string{}
>
> a := make\(map\[string\]string\)

# 介绍

> 1. 底层是一个hmap
> 2. hmap重要字段有count，B，buckets，oldbuckets
>    1. count是元素数量
>    2. 2^B是buckets的数量
>    3. buckets是桶数组，里面的元素是一个溢出桶，每个桶里面能放8个元素
>    4. oldbuckets是在迁移的时候使用
> 3. key的定位
>    1. 低B位确定在桶数组中的位置
>    2. 插入时候找到第一个空位插入，key为他的高8位的值
>    3. 查找的时候遍历溢出桶，比较高8位和key的值
>    4. 再桶里面 key和valuef分别绑定在一起，考虑内存对齐
> 4. 会触发扩容
> 5. 扩容后迁移是渐进式扩容，每次最多迁移两个桶，插入，删除，更新都会触发
> 6. 遍历的时候杀出元素会报错



