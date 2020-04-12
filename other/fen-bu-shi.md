# 分布式

## 资料

> [http://www.ruanyifeng.com/blog/2018/07/cap.html](http://www.ruanyifeng.com/blog/2018/07/cap.html)

## CAP原则

> CAP原则又称CAP定理，指的是在一个分布式系统中，
>
> [一致性](https://baike.baidu.com/item/一致性/9840083)\(Consistency）、
>
> [可用性](https://baike.baidu.com/item/可用性/109628)（Availability）、
>
> 分区容错性（Partition tolerance）
>
> CAP 原则指的是，这三个要素最多只能同时实现两点，不可能三者兼顾。

## 不能兼顾CA的原因

> 为了保证一致性，则再node1写的时候，必须要锁住node2的读写操纵。待数据同步后再放开读写。违背可用性
>
> 如果保证可用性，一致性就不能保证。

## 



