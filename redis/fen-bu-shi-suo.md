# 分布式锁

## 资料

> 锁过期 任务没执行完 [https://blog.csdn.net/wutengfei\_java/article/details/100699538](https://blog.csdn.net/wutengfei_java/article/details/100699538)

## 要求

> 互斥性  
> 可重入性

## 释放锁的时候保证释放的是自己的锁

> （ a,b，c线程进来。a加锁 处理超时，锁失效，b加锁处理，此时 a处理完成释放锁了b的锁，c线程获取锁成功。gg）
>
> 通过版本号来控制

## 增加重入性， key 线程标识 重入次数

> multi
>
> setnx key val
>
> expires key time
>
> exec

multi用来保证原子性，加时间防止死锁

