# 索引失效

## 资料

> [https://www.cnblogs.com/wdss/p/11186411.html](https://www.cnblogs.com/wdss/p/11186411.html)



## 场景

> 1. like 以%开头
> 2. 数据隐式转换
> 3. or 前后有字段未用索引
> 4. 对索引字段进行计算
> 5. 组合索引，不是第一个索引
> 6. not  &lt;&gt;   !=  索引肯定失效
> 7. 全表扫描比索引扫描快的时候

## 数据类型隐式转换导致的问题？

> * int类型的 左右两边都转成float，两边都是唯一的不影响索引的使用
> * string类型的时候 右边唯一，左边不唯一 1000  1000a 转成float后都是 1000，导致索引失效



