# 部署docker

## 资料

> [https://www.cnblogs.com/levcon/p/12641376.html](https://www.cnblogs.com/levcon/p/12641376.html)
>
> 镜像仓库密码 [https://blog.csdn.net/zhangxiangui40542/article/details/83106358](https://blog.csdn.net/zhangxiangui40542/article/details/83106358)

## 常用命令

> kubectl create namespace &lt;namespace&gt;  //创建命名空间
>
> kubectl create secret docker-registry regcred --docker-server=hub.docker.com --docker-username=ckhero --docker-password=suanni123 --docker-email=18801613198@163.com -n cl-test    //创建镜像仓库密码
>
> kubectl get pods -n &lt;ns&gt;  // 查看摸个命名空间下的 pods
>
> kubectl get svc -n &lt;ns&gt;  // 查看某个命名空间下的服务情况



