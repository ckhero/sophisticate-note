# 指针

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



