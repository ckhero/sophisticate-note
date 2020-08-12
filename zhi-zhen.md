# 指针

## 资料

> Go 普通指针类型、unsafe.Pointer、uintptr之间的关系
>
> [https://www.cnblogs.com/-wenli/p/12682477.html](https://www.cnblogs.com/-wenli/p/12682477.html "Go 普通指针类型、unsafe.Pointer、uintptr之间的关系")

## uintptr

> * 一个足够大的无符号整型，用来表示任意地址
> * 可以进行数值计算

## unsafe.Pointer

> * 代表一个可以指向任意类型的指针
> * 不可进行数值计算
> * 四种区别于其他类型的操作
>   * 任意类型的指针值均可转成Pointer
>   * Pointer可以转成任意类型的指针值
>   * uintptr均可转成Pointer
>   * Pointer均可转成uniptr



