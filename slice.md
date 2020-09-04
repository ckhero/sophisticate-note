# slice

## 资料

> [https://studygolang.com/articles/16861](https://studygolang.com/articles/16861)

## 简述

> 是数组的抽象。可以理解为动态数组，提供cap len append方法

## append

> 首先检查数组容量够不够，够的话，直接添加
>
> 不够的话创建新的容量足够的底层数组，先将之前的元素复制过来，再将新元素添加进去

## 扩容

> 小于1024，扩容因子  2
>
> 大于等于1024 ，扩容因子 1.25
>
> 不支持缩容，会报错
>
> ```
> func growslice(et *_type, old slice, cap int) slice {
>     ...
>     if et.size == 0 {
>         if cap < old.cap {
>             panic(errorString("growslice: cap out of range"))
>         }
>         
>         return slice{unsafe.Pointer(&zerobase), old.len, cap}
>     }
>     ...
> }
> ```

## 操作

> * 切片中追加切片
>
> ```
> arr1 := []int{1,2,3}
> arr2 := []int{1,2,3}
> arr2 = append(arr1, arr2...)
> ```
>
> * 创建切片
>
> ```
> var a []int // nill slice. point to nil
> b := []int{} // empty slice, ponit to empty array
> c := make([]int, 0)
> ```
>
> * 复制 - 在复制时会按照最少的 Slice 元素个数进行复制
>
> ```
> dst := []int{1, 2, 3}
>  src := []int{4, 5, 6, 7, 8}
>  n := copy(dst, src)
> ```



