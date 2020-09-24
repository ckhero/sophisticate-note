# 内存对齐

## 资料

> [https://www.jianshu.com/p/49f7e6f56568](https://www.jianshu.com/p/49f7e6f56568)
>
> [https://studygolang.com/articles/22818](https://studygolang.com/articles/22818)
>
> [http://blog.haohtml.com/archives/19040](http://blog.haohtml.com/archives/19040)

## 简述

> cpu读取内存的时候不是一个字节一个字节去读取的，而是以2，4，8，16这种粒度去读取
>
> 32位操作系统默认对其系数是4，64位的为8

## 原因

> 1. 不是所有平台都能访问任意地址上的数据
> 2. 不内存对其的话可能会导致CPU两次读取内存，带来额外的开销

## 对齐规则

> 1. 针对具体的字段，对齐系数 = min（字段本身的大小， 编译器的对齐系数），偏移量为对齐系数的整数倍
> 2. 针对结构体，对齐系数= min\(结构体中字段最大的值，编译器 的对齐系数\)



