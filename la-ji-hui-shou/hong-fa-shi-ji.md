# 触发时机

> https://www.bookstack.cn/read/qcrao-Go-Questions/spilt.11.GC-GC.md

## 简述

> * 主动触发
>   * 调用runtime.GC，阻塞式的等待完成
> * 被动触发
>   * 监控线程，如果两分钟内没有GC，前置触发
>   * 分配内存的时候，会进行检测



