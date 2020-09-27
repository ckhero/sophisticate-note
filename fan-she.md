## reflect

## 资料

> [https://studygolang.com/articles/2157](https://studygolang.com/articles/2157)
>
> [https://studygolang.com/articles/26612](https://studygolang.com/articles/26612)

## 简述

> 在编译时不知道类型的情况下，可更新变量，查看值，调用方法以及对他们的布局机制进行调整的机制
>
> 一种检查存储在接口变量中的\(类型  值\)对的机制

## 操作函数

> reflect.ValueOf\(\) 获取输入参数接口中的数据的值，如果为空返回0
>
> reflect.TypeOf\(\) 获取输入参数接口中的值得类型。如果为空返回nil

## 三大规则

> * 接口数据-&gt; 反射对象  
> * ```
>   reflect.ValueOf(aaa).Interface()
>   ```
>
> * 反射对象-&gt; 接口数据
> * 修改接口数据 【v.Elem\(\).Canset\(\)】



