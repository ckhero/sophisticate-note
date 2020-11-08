# 四种网络模式

> https://blog.csdn.net/huanongying123/article/details/73556634

## 简述

> 1. bridge
>    1. --net=bridge
>    2. 默认模式，为容器提供单独的命名空间
> 2. host
>    1. --net=host
>    2. 不提供单独的命名空间，共享宿主机的网络配置
>    3. mac不支持
> 3. none
>    1. --net=none
>    2. 不设置网络配置，需要手动配置
>    3. 拥有独立的命名空间
> 4. container
>    1. –net =container:containerNmae
>
>    2. 与已经存在的容器共享网络配置





