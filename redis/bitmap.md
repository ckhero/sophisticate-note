bitmap

资料

[https://www.jianshu.com/p/62cf39db5c2f](https://www.jianshu.com/p/62cf39db5c2f)

[https://www.jianshu.com/p/4c8e119f35db](https://www.jianshu.com/p/4c8e119f35db)

原理 图解  [https://www.sohu.com/a/300039010\_114877](https://www.sohu.com/a/300039010_114877)

[https://blog.csdn.net/u011957758/article/details/74783347](https://blog.csdn.net/u011957758/article/details/74783347)

最大值 2^32-1/\(8 \* 1024  \*1024\) = 512m

描述

> 用最小的单位bit来表进行01设置，表示对应元素的状态或者

最大缺点

> 偏移量大的时候会占用过大的内存，比如偏移量1000 会初始化1000的bitmap，初始值为0

goole的改进

> google 的EWAH堆bitmap做了优化 EWAH 中把bitmap存储与long数组，long中的每个元素都可存64位。谷歌把这个叫做word
>
> 创建一个bitmap的时候会有4个word
>
> word分两种 lw存储数据的。RLW 存储跨度信息 （第一个word）
>
> |  |
> | :--- |
>
>
> | getbit key offset | 对key所存储的字符串值，获取指定偏移量上的位（bit） |
> | :--- | :--- |
>
>
> | setbit key offset value | 对key所存储的字符串值，设置或清除指定偏移量上的位（bit） 1. 返回值为该位在setbit之前的值 2. value只能取0或1 3. offset从0开始，即使原位图只能10位，offset可以取1000 |
> | :--- | :--- |
>
>
> | bitcount key \[start end\] | 获取位图指定范围中位值为1的个数 如果不指定start与end，则取所有。_**1表示的字节不是位的个数**_ |
> | :--- | :--- |
>
>
> | bitop op destKey key1 \[key2...\] | 做多个BitMap的and（交集）、or（并集）、not（非）、xor（异或）操作并将结果保存在destKey中 |
> | :--- | :--- |
>
>
> | bitpos key tartgetBit \[start end\] | 计算位图指定范围第一个偏移量对应的的值等于targetBit的位置 1. 找不到返回-1 2. start与end没有设置，则取全部 3. targetBit只能取0或者1 |
> | :--- | :--- |

应用场景

> 可以对数据进行纵向扩展。比如要统计100w用户今天的签到人数
>
> 只要需要陪陪 1000000/ 8 / 1024/ 1024 = 1000000/ 8 / 1024/ 1024 = 0.192m的空间



