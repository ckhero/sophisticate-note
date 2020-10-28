# szet

## 结构

> 有序结合元素个数小于512 & 元素大小小于64字节  使用ziplist ，否则使用skiplist

## 设计原因

> 压缩表的优势是提高内存使用率，但是无法排序，不支持范围查找。能做到元素的快速查找。
>
> 跳表，无法做到快速查找，但能做到排序和范围查找

## 命令

> zadd key scoer member
>
> zrange key 0 100  withscores
>
> zremrangebyrank key start  end

## 应用场景

> * 排行榜
> * 延时注销，scoer 为时间戳，member为userid，筛选满足的userid 删除



