# redigo

## 资料

> [https://blog.csdn.net/xiaohu50/article/details/51606349](https://blog.csdn.net/xiaohu50/article/details/51606349)

## 配置场景

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



