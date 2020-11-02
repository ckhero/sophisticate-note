# redigo

## 资料

> [https://blog.csdn.net/xiaohu50/article/details/51606349](https://blog.csdn.net/xiaohu50/article/details/51606349)

## 配置场景

> * wait 表示没有可用连接的时候是否等待
> * MaxIdle  空闲连接池的大小，空闲连接池是个栈式结构，先进后出
> * MaxActive 连接池最大连接数限制，主要考虑服务端支持的连接数上限，y自己应用之间瓜分连接数
> * IdleTimeout 空闲连接池超时时间，一旦超时，就从空闲连接池摘除。该超时时间应该小于服务端的超时时间

### 高频场景

> * 调高MaxIdle，数目小于MaxActive，避免连接超时后需要重新建立连接
> * 尽量调高MaxActive
> * IdleTimeout调小，设置短点也无所谓

### 低频场景

> * 调低MaxIdle
> * IdleTimeout调小
> * MaxActive随意，够用就好

## 从连接get新连接流程

> 1 如果wait是true 维护一个 buf size 为MaxActive的通道，每使用一个从通道里面取一个数据，释放的时候往通道里面塞数据stuct{}{}
>
> 2 清除过期的空闲连接
>
> 3 如果有可用的空闲连接从空闲连接去取
>
> 4 没有可用的空闲连接，产生新的连接，
>
> 234期间会加锁



