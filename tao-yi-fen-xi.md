# 逃逸分析

## 资料

> [https://www.cnblogs.com/sunsky303/p/11121657.html](https://www.cnblogs.com/sunsky303/p/11121657.html)
>
> [https://cloud.tencent.com/developer/article/1422376](https://cloud.tencent.com/developer/article/1422376)

## 为什么要分析

> 最好处是减少gc的压力，不逃逸的分配在栈上，函数返回时回收资源，不需要标记清除
>
> 栈与栈之间内存不共享

## 逃逸场景

> 1. 容量未知，make\(\[\]int, L\)
> 2. 大容量对象
> 3. 函数字面量
> 4. 动态类型\(interface\) ，编译期间无法确定类型
> 5. 局部变量指针类型



