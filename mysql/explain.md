# explain

## 资料

> [https://www.cnblogs.com/tufujie/p/9413852.html](https://cloud.tencent.com/developer/article/1093229)

## type

> const  主键或者唯一索引与常数比较，只有一条匹配记录
>
> eq\_ref  联表查询的使用利用主键或者唯一索引去做关联，最多只会返回一条关联数据
>
> ref 使用非唯一索引或者唯一索引的前缀去做比较，能得到多条记录
>
> range 范围查找
>
> index  只需要扫描索引树就行
>
> all  全表扫描

## extra

> use index 索引覆盖，只需要查找索引就行
>
> distinct 查找到需要的行之后就不再继续查找下去
>
> use where   获取整条记录，一条条比较过去
>
> file sort 文件排序
>
> temp 临时

rows

