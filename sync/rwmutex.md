# RWMutex

> https://zhuanlan.zhihu.com/p/98443808

```
type RWMutex struct {
    w           Mutex  // held if there are pending writers
    writerSem   uint32 // 用于writer等待读完成排队的信号量
    readerSem   uint32 // 用于reader等待写完成排队的信号量
    readerCount int32  // 读锁的计数器
    readerWait  int32  // 等待读锁释放的数量
}
```

## 简述

> 读的时候readerCount++ 如果小于0加锁失败等待readerSem信号
>
> 写的时候先加排它锁，然后把readerCount-rwmutexMaxReaders，如果readerWait还有，则等待writeSem信号。



