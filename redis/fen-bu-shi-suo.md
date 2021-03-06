# [分布式锁](/redis/fen-bu-shi-suo.md)分布式锁

## 资料

> 锁过期 任务没执行完 [https://blog.csdn.net/wutengfei\_java/article/details/100699538](https://blog.csdn.net/wutengfei_java/article/details/100699538)
>
> redis官网 分布式锁 [https://redis.io/topics/distlock](https://redis.io/topics/distlock)
>
> redlock [https://www.cnblogs.com/rgcLOVEyaya/p/RGC\_LOVE\_YAYA\_1003days.html](https://www.cnblogs.com/rgcLOVEyaya/p/RGC_LOVE_YAYA_1003days.html)

## 集群下的分布式锁

> Redlock算法

## 要求

> 互斥性  
> 可重入性
>
> 不会死锁，客户端崩溃没有释放锁，其他的客户端也能获得锁
>
> 加锁和释放锁都是同一个客户端

## 释放锁的时候保证释放的是自己的锁

> （ a,b，c线程进来。a加锁 处理超时，锁失效，b加锁处理，此时 a处理完成释放锁了b的锁，c线程获取锁成功。gg）
>
> 通过版本号来控制

## 增加重入性， key 线程标识 重入次数

> 最新建议  j加锁
>
> > ```
> > set  key_name my_random_value NX PX 30000
> > ```
>
> 释放
>
> ```
> if redis.call("get",KEYS[1]) == ARGV[1] then
>     return redis.call("del",KEYS[1])
> else
>     return 0
> end
> ```
>
> watch
>
> multi
>
> setnx key val
>
> expires key time
>
> exec

multi用来保证原子性，加时间防止死锁

## 应用场景

> * 防止库存超卖，涉及优化，分段库存

## 注意的问题

> * 分布式节点防止单节点故障
> * 任务执行时间超过锁的过期时间。利用watch dog 对key延时
> * master加锁成功后，还没同步到从库的时候就宕机了。线程2 获取锁成功。redlock算法。



