# 内存调优

> https://blog.csdn.net/weixin\_44024220/article/details/104212225

## 简述

> 1. slice，map预分配内存
> 2. 尽可能使用值类型
> 3. map，channel，slice的值尽可能避免使用指针
> 4. 使用struct{} 优化，占0字节
> 5. 内存对齐
> 6. 对于性能要求高，且函数调用频繁的，尽量避免使用接口类型



