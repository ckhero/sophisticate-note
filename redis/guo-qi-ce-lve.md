# 过期key的删除策略

> [https://blog.csdn.net/weixin\_37589896/article/details/78744765](https://blog.csdn.net/weixin_37589896/article/details/78744765)
>
> 淘汰策略 [https://blog.csdn.net/ligupeng7929/article/details/79603060](#)

## 三种策略

> 1. 被动删除
>    1. 读写一个key的时候，会出发惰性删除，直接删除掉这个key
>    2. cpu友好，内存不友好
> 2. 主动删除
>    1. 由于惰性删除无法保证冷数据及时删除，所以redis会定期主动淘汰过期的key
>    2. serverCon定时任务定时删除，淘汰任务有超时机制，保证淘汰不会阻塞太多应用请求
>    3. hz设置频率，默认每秒10次
>    4. 主从模式，只有主节点进行该策略
> 3. 超maxmemory的时候，触发主动清理策略
>    1. 永不删除
>    2. valatile-lru  设置过期时间的keyj进行lru
>    3. allkeys-lru  所有的key进行lru
>    4. volatile-random  设置了过期的key进行随机删除
>    5. allkeys-random 所有key随机删除
>    6. volatile-ttl 设置过期key的里面删除最快过期的

## 注意事项

> 1. 主从模式下，被动删除和主动删除只会发生在master，然后同步到slave
> 2. 超内存的情况，
>    1. 每次读写请求都会触发redis.c/freeMemoryIfNeeded\(void\)处理超出内存的请求，这个过程是阻塞的。
>    2. 同时还会触发清理策略，清理策略不是针对所有key，而是抽样形式，抽取maxmemory-samples个key然后进行处理。默认是5个

## **Replication link和AOF文件中的过期处理**

> 统一由master处理，然后传递下去



