# channel

### 资料

> [https://studygolang.com/articles/19740](https://studygolang.com/articles/19740)

## 简述

> 协程之间通信通道，优点是通过提供原子的通信原语，避免了竞态情形下复杂的锁机制

## buf

> 有缓冲的channel的特有结构，用存储数据。是个循环列表

### sendx和recvx

> 循环列表中发送和接收的Index

### sendq和recvq

> 发送发送\(channel &lt;-\)和接收\(&lt;-channel\)的协程 抽象出来的结构体的队列，是个双向列表

### mutex

> 互斥锁

发送和接受的时候会先锁住，然后发送或者接受。再解锁

g1  send buf满的时候，会阻塞，g1主动调用go的调度器，让g1让出m，进入等待状态

此时g2消费buf数据。channel将g1从等待队列中退出，将g1的数据写入缓冲，然后go的调度器唤醒g1，并把g1放到可执行的队列

g1取消费，buf为空，会阻塞，go的调度器让g1让出m，进入等待

g2 send  不加锁，直接把数据从g2  copy到 g1的栈中。g1无需再获取channel的锁，然后再从缓冲中取数据，减少内存操作。提高效率



## 初始化

> var c chan int
>
> c := make\(chan int\)



