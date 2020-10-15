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



