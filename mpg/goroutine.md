# goroutine

## 资料

> 抢占式调度 [https://tonybai.com/2017/11/23/the-simple-analysis-of-goroutine-schedule-examples/](https://tonybai.com/2017/11/23/the-simple-analysis-of-goroutine-schedule-examples/)
>
> 抢占式调度完整版 [http://xiaorui.cc/archives/6535](http://xiaorui.cc/archives/6535)
>
> [https://tonybai.com/2017/06/23/an-intro-about-goroutine-scheduler/](https://tonybai.com/2017/06/23/an-intro-about-goroutine-scheduler/)

## 简述

> golang程序启动的时候会启动一个symon（监控线程）

## sysmon作用

> * 释放闲置5分钟以上的span物理内存
> * 两分钟内如果没有进行gc，轻质尽心
> * 处理长时间未处理的网络轮询的结果
> * 释放因为syscall长时间阻塞的p
> * 对阻塞G进行抢占



