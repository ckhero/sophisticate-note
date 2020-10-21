# 同步

> [https://studygolang.com/articles/96](https://studygolang.com/articles/21533)
>
> https://studygolang.com/articles/21533

## 为什么要同步

> 至于为什么需要同步呢，类似线程要做同步差不多，现在的cpu都是多核，假设一核一个线程同时一起访问同一块内存中的数据吗，那么可能上一ns第一个线程刚把数据从寄存器拷贝到内存，第二个线程马上又把此数据用它修改的值给覆盖了，这样共享数据变会乱套。

## 方案

> 1. Mutex
> 2. channel
> 3. sync.WaitGroup?



