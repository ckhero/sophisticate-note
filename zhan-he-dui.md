# 栈和堆

> 直接通过 go build -gcflags ‘-m -l’ 就可以看到逃逸分析的过程和结果

## 简述

> 栈 分配廉价，堆分配昂贵.
>
> * 栈
>   * 两个CPU指令，一个push到栈空间完成分配，一个是从栈空间释放
> * 堆
>   * 找到足够大的内存空间，后续要通过GC来释放

## 资料

> [https://studygolang.com/articles/11878](https://studygolang.com/articles/26113)
>
> [https://studygolang.com/articles/26113](https://studygolang.com/articles/26113)
>
> [http://www.huamo.online/2019/06/25/%E6%B7%B1%E5%85%A5%E7%A0%94%E7%A9%B6goroutine%E6%A0%88/](http://www.huamo.online/2019/06/25/深入研究goroutine栈/)
>
> 好 [https://studygolang.com/articles/19386](https://studygolang.com/articles/19386)

## golang

> 栈
>
> * 栈中的变量是独占的
> * 每个函数对应一个独享栈，这个栈的生命周期是这个 函数的开始和结束。
> * 优势是比较轻量，随用随弃，存活期跟随函数 
>
> 堆
>
> * 全局访问块
> * 可共享
> * 不会自动释放由垃圾回收控制

## 



