# 索引原理

## 资料

> [https://blog.csdn.net/bohu83/article/details/81104432](https://blog.csdn.net/bohu83/article/details/81104432)

## 聚簇索引和非聚簇索引

> [https://www.cnblogs.com/jiawen010/p/11805241.html](https://www.cnblogs.com/jiawen010/p/11805241.html)
>
> [https://my.oschina.net/xiaoyoung/blog/3046779](https://my.oschina.net/xiaoyoung/blog/3046779)
>
> 1 聚簇索引索引和行数据被同时载入到内存，获得数据更快
>
> 2 聚簇索引，叶子节点存放的是主键值不适用数据地址，这样子数据变化的时候只需要维聚簇促索引，不需要维护二级索引
>
> 3 非聚簇索引，数据的的物理地址凌乱的，读取更耗时
>
> 4 对于数据量巨大的时候偶，非局聚簇索引 占一些优势



