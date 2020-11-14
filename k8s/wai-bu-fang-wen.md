# 外部访问

> [https://juejin.im/post/6844903974206701575](https://juejin.im/post/6844903974206701575)
>
> 端口转发
>
> [https://kubernetes.io/zh/docs/tasks/access-application-cluster/port-forward-access-application-cluster/](https://kubernetes.io/zh/docs/tasks/access-application-cluster/port-forward-access-application-cluster/)

## 对比

> 1. port-forward
>    1. 适合调试，不适合生产环境
>    2. kubectl port-forward  type/name targetPort:port
> 2. NodePort
>    1. 每个节点一个端口，过多的服务需要维护大量的端口
> 3. LoadBalance
>
>    1. 通常云服务商提供，不提供使用ingress
>
> 4. Ingress
>
>    1. 公开多个服务



