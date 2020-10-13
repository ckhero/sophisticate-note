# TapTap

> * slice 初始化
> * golang哪些情况会panic
> * 三次握手和四次挥手异常情况，为什么是三次，不是两次或者四次
> * golang中没有隐藏的this指针
> * 通用的序列化反序列化
> * 内存实时排行榜，500w数据
> * syslog，这个没记清楚？
> * channel是同步的还是异步的？
> * 初始化结构体
> * 撸一遍好吧 https://blog.csdn.net/ahaotata/article/details/84104437
> * 下面这段代码有问题吗？有问题的话加一行代码解决
>
>   * ```
>     func TestMap() {
>         wg := sync.WaitGroup{}
>         wg.Add(200)
>         m := make(map[int]int)
>         for j := 0; j < 100; j++ {
>             go func() {
>                 fmt.Println(j)
>                 if _, ok := m[j]; ok {
>                     fmt.Println("get data", j)
>                 } else {
>                     fmt.Println("no data")
>                 }
>                 wg.Done()
>             }()
>         }
>
>         for j :=0; j < 100; j ++ {
>             go func(t int) {
>                 m[t] = t
>             }(j)
>             wg.Done()
>
>         }
>         wg.Wait()
>     }
>     ```



