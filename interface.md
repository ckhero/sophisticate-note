# interface

## 资料

> [https://mp.weixin.qq.com/s/re\_9CmGm3xEbY7xCr5CYbQ](https://mp.weixin.qq.com/s/re_9CmGm3xEbY7xCr5CYbQ)

## 结构

> 有方法的iface
>
> ```
> type iface struct {
> 	tab  *itab
> 	data unsafe.Pointer
> }
> ```
>
> itab 里面包含方法集的指针，动态类型的指针，静态类型的指针
>
> ```
> type itab struct {
> 	inter *interfacetype
> 	_type *_type
> 	hash  uint32 // copy of _type.hash. Used for type switches.
> 	_     [4]byte
> 	fun   [1]uintptr // variable sized. fun[0]==0 means _type does not implement inter.
> }
> ```
>
>
>
> 没有方法的eface
>
> ```
> type eface struct {
> 	_type *_type
> 	data  unsafe.Pointer
> }
> ```





## 作用

> * 泛型变成
> * 隐藏具体实现



