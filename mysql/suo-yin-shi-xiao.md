# 索引失效

## 资料

> [https://www.cnblogs.com/wdss/p/11186411.html](https://www.cnblogs.com/wdss/p/11186411.html)

> 1. 列与列对比
> 2. 存在null条件
> 3. 有or not r  not != &lt;&gt; in  like "%adfa"
> 4. 条件上包含函数
> 5. 数据类型隐式转换

## 数据类型隐式转换导致的问题？

> * int类型的 左右两边都转成float，两边都是唯一的不影响索引的使用
> * string类型的时候 右边唯一，左边不唯一 1000  1000a 转成float后都是 1000，导致索引失效



