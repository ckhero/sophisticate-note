# 仪表盘

## 资料

> [https://cloud.tencent.com/developer/article/1580358](https://cloud.tencent.com/developer/article/1580358)

## 简介

> 安装
>
> ```
>  kubectl apply -f https://kuboard.cn/install-script/kuboard.yaml
> ```
>
> 卸载
>
> ```
> kubectl delete -f https://kuboard.cn/install-script/kuboard.yaml
> ```
>
> 获取token
>
> ```
> # 在第一个 Master 节点上执行此命令
> # 管理员token
> kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep kuboard-user | awk '{print $1}')   
>
> # 普通用户token
> kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep kuboard-viewer | awk '{print $1}')
> ```
>
> 获取暴露的端口号
>
> ```
> kubectl get svc -n kube-system
> ```





