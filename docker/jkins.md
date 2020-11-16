# jkins

> 如何构建golang项目  [https://cloud.tencent.com/developer/article/1433233](https://cloud.tencent.com/developer/article/1433233)
>
> ssh key 添加 [https://www.cnblogs.com/xiaoxi-3-/p/9680205.html](https://www.cnblogs.com/xiaoxi-3-/p/9680205.html)
>
> [https://www.qikqiak.com/k8s-book/docs/37.Jenkins Pipeline.html](https://www.qikqiak.com/k8s-book/docs/37.Jenkins Pipeline.html)
>
> 插件地址 https://plugins.jenkins.io/ui/search/?sort=relevance&categories=&labels=&view=Tiles&page=1&query=kubernetes

## docker安装

> docker run -u root --rm -d -p 8080:8080 -p 50000:50000 -v jenkins-data:/var/jenkins\_home -v /var/run/docker.sock:/var/run/docker.sock  jenkinsci/blueocean

## 几个问题

> 1. golang 文件 linux 运行
>    1. CGO\_ENABLED=0 GOOS=linux GOARCH=amd64 
> 2. github需要账号密码登陆
>    1. echo [http://18801613198%40163.com:suanni123@git.zk020.cn](http://18801613198%40163.com:suanni123@git.zk020.cn) &gt; git-credentials.txt && mv git-credentials.txt ~/.git-credentials
> 3. 容器间通信问题
>    1. docker的四种网络模式



