# 栈和堆

直接通过 go build -gcflags ‘-m -l’ 就可以看到逃逸分析的过程和结果

## 资料

> [https://studygolang.com/articles/11878](https://studygolang.com/articles/26113)
>
> [https://studygolang.com/articles/26113](https://studygolang.com/articles/26113)

## golang

> 栈
>
> * 栈中的变量是独占的
> * 每个函数对应一个独享栈，这个栈的生命周期是这个 函数的开始和结束。
> * 优势是比较轻量，随用随弃，存活期跟随者函数 
>
> 堆
>
> * 全局访问块
> * 可共享
> * 不会自动释放由垃圾回收控制

## 栈逃逸

> * 尝试申请较大的结构体或者数组
> * 变量会被重复使用 
> * 编译期间不能确定变量 的大小



