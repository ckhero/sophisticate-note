# Count

## 资料

> [https://www.cnblogs.com/javabg/p/9583931.html](https://www.cnblogs.com/javabg/p/9583931.html)
>
> [https://www.cnblogs.com/yjd\_hycf\_space/p/9985393.html](https://www.cnblogs.com/yjd_hycf_space/p/9985393.html)

## 资料

> l  count\(\*\)包括了所有的列，相当于行数，在统计结果的时候，不会忽略列值为NULL  
>
> l  count\(1\)包括了忽略所有列，用1代表代码行，在统计结果的时候，不会忽略列值为NULL  
>
> l  count\(列名\)只包括列名那一列，在统计结果的时候，会忽略列值为空（这里的空不是只空字符串或者0，而是表示null）的计数，即某个字段值为NULL时，不统计。

## 效率

> l  列名为主键，count\(列名\)会比count\(1\)快  
>
> l  列名不为主键，count\(1\)会比count\(列名\)快  
>
> l  如果表多个列并且没有主键，则 count（1） 的执行效率优于 count（\*）  
>
> l  如果有主键，则 select count（主键）的执行效率是最优的  
>
> l  如果表只有一个字段，则 select count（\*）最优。



