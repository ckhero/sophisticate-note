# hash

## 底层结构

> ziplist或者hashtable
>
> * 键和值得长度都小于64
> * 元素个数小于512个
>
> 满足上述两个条件使用压缩列表（ziplist）



