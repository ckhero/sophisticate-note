# Docker

## 常用命令

> docker build -t  &lt;包名&gt;:&lt;版本号&gt;  &lt;Dockerfile路径&gt;   //打包镜像
>
> docker images // 镜像列表
>
> docker rmi &lt;镜像名字&gt;    // 删除镜像
>
> docker ps -a   // 查看所有容器
>
> docker attach &lt;容器id&gt;  // 进入容器
>
> docker exec -it &lt;容器id&gt;   /bin/bash //命令行模式进入容器
>
> docker rm -f  &lt;容器id&gt;    // 删除容器
>
> docker run -it &lt;镜像名字&gt; /bin/bash    //启动容器并以命令行模式进入容器



