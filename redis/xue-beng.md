## 雪崩

## 资料

> [https://blog.csdn.net/Chaoren666/article/details/89953969](https://blog.csdn.net/Chaoren666/article/details/89953969)
>
> [https://www.cnblogs.com/yoishion/p/10791501.html](https://www.cnblogs.com/yoishion/p/10791501.html)

## 描述

> * redis集群大面积故障
> * 缓存失效，但依然后大量的redis请求
> * redis失效后，请求转到mysql

## 解决方案

> * 提供高可用 的集群方案 eg.cluster
> * 开启本地缓存
> * 缓存降级
> * 错开缓存的失效时间，二级缓存，缓存预热





