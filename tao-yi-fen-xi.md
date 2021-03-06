# 逃逸分析

## 资料

> [https://www.cnblogs.com/sunsky303/p/11121657.html](https://www.cnblogs.com/sunsky303/p/11121657.html)
>
> [https://cloud.tencent.com/developer/article/1422376](https://cloud.tencent.com/developer/article/1422376)
>
> 避免内存逃逸 [https://chai2010.cn/advanced-go-programming-book/ch3-asm/ch3-05-control-flow.html](https://chai2010.cn/advanced-go-programming-book/ch3-asm/ch3-05-control-flow.html)
>
> [https://www.jianshu.com/p/dcd87431a8af](https://www.jianshu.com/p/dcd87431a8af)

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
>    1. channel,map和slice里面放指针会逃逸
>    2. 简单取址后，如果不发生函数外的调用不会逃逸
>    3. 局部变量被外部引用，生命周期大于栈

## 避免

> unsafe.Pointer 是一个真实的指针，但是对编译器而言是一个int类型，通过这个把指针隐藏起来。达到避免逃逸



