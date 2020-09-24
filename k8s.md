# K8S

## 资料

> [https://my.oschina.net/jamesview/blog/2994112](https://my.oschina.net/jamesview/blog/2994112)
>
> [https://mp.weixin.qq.com/s/iN2sY7cj\_AGCSqs9JOOCYw](https://mp.weixin.qq.com/s/iN2sY7cj_AGCSqs9JOOCYw)

## 集群包括两部分

> 一个master节点**（主节点）**
>
> * 负责管理和控制节点
>
> 一群node节点**（计算节点）**
>
> * 工作负载节点，里面是具体的容器

### Node节点

> Docker  容器
>
> kubelet  监视指派到Node的pod，包括创建 修改 监控 删除 等
>
> Kube-proxy  为pod提供代理
>
> Fluentd 负责收集日志，存储和查询
>
> **Pod 是k8s的基本操作单元 ，一个pod代表集群中运行的一个进程，内部分装了一个或者多个亲密关联的容器**



