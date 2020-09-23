# bitmap

## 资料

> [https://www.jianshu.com/p/a8dbef6f2820](https://www.jianshu.com/p/a8dbef6f2820)

## 优点

> 通过一个bit位来表示元素对应的状态，其中key就是元素对应的值，节省空间
>
> setbit和getbit的时间复杂度都是o（1），其他位运算数效率也高

## 使用

> setbit key offset \[0\|1\]
>
> get key offset
>
> bitcount key // 计算为1的bit数量
>
> bitop \[and \| or \| xor\] destkey key1 key2 .. // 对key1  key2 。。做位运算结果保存在destkey



