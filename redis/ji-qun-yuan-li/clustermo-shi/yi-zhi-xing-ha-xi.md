一致性哈希

资料 [https://www.jianshu.com/p/735a3d4789fc](https://www.jianshu.com/p/735a3d4789fc)

一致性哈希是对 2^32次取模，一个圆环。

> 先将节点hash定位节点位置，比如ip。
>
> 数据进来后对key进行hash如果定位到节点，就用该节点。
>
> 如果不在节点上。就定位到顺时针的下一个节点

主要用来解决机器增加或者减少大面积的数据重新哈希的问题。

> 新增节点的只要对相关区间内的数据重新哈希就行
>
> 如果节点宕机，数据会被定位到下哥节点

缺点

> 节点数较少的的时候，容易导致数据倾斜

解决

> 引入虚拟节点，每个节点都会多次hash产生很多虚拟节点。dubbo的负载均衡中就有这种思想



