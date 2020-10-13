# 方法集

> https://studygolang.com/articles/15249?fr=sidebar
>
> https://www.jianshu.com/p/d93656cdce0a
>
> https://studygolang.com/articles/5072

## 简单method

> \*T和T类型的方法集合互相继承

## 接口中的method

> 外部类型没有实现接口，会继承内部类型的接口
>
> 外部类型实现了接口，会覆盖内部类型的接口
>
> ```
> type cat stuct {
>     name string
> }
>
> type BlackCat struct {
>     cat
>     Age int
> }
> blackCat 叫外部类型。cat叫内部类型
> ```

## 注意

> 在接口的method中，对于普通类型的T，T的methods set里面不包含\*T实现的method，但是\*T会继承T的接口



