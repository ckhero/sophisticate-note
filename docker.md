# Docker

## 资料

> [https://www.runoob.com/docker/docker-dockerfile.html](https://www.runoob.com/docker/docker-dockerfile.html)

## Docker是什么

> Docker是一个容器化平台，以容器的形式把程序以及所有依赖打包在一起，确保程雪能在所有平台运行

## 缩小镜像

> [https://blog.csdn.net/bbwangj/article/details/82178774](https://blog.csdn.net/bbwangj/article/details/82178774)

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
> docker exec -it &lt;容器id&gt;   /bin/bash //命令行模式进入容器  【-i是交互式操作，-t 是终端】
>
> docker rm -f  &lt;容器id&gt;    // 删除容器
>
> docker run -it &lt;镜像名字&gt; /bin/bash    //启动容器并以命令行模式进入容器
>
> docker history &lt;镜像名字&gt;  //可以看到 构建了几层

## Dockerfile

> FROM    基于什么镜像
>
> RUN &lt;shell命令&gt;   // shell命令，docker build 的时候运行
>
> RUN \["可执行文件名字", "参数1", "参数2"\]
>
> COPY &lt;原路径&gt;   &lt;目标路径&gt;
>
> CMD &lt;shell命令&gt; // docker run 的时候运行
>
> CMD \["可执行文件名字", "参数1", "参数2"\]
>
> CMD \["参数1", "参数2"\]   // 为ENTRYPOINT指令指定的程序提供默认参数
>
> ENTRYPOINT \["可执行文件名字", "参数1", "参数2"\]  //
>
> ```
>     类似CMD ，不会被命令行的指定参数的指令覆盖，而且这些参数会被当做参数传递给ENTRYPOINT指令指定的程序
>
>    但是docker run --entrypoint  会覆盖指令
>
>    搭配 CMD使用，定参使用ENTRYPOINT，变参使用CMD
> ```
>
> ENV  &lt;key1&gt;=&lt;v1&gt;  &lt;ke2&gt;=&lt;v2&gt;    //设置环境变量
>
> ENV  &lt;key1&gt;  &lt;v1&gt;
>
> VOLUME &lt;路径&gt;
>
> VOLUME \[&lt;路径&gt;，&lt;路径&gt;\]   // 或者docker run -v
>
> EXPOSE  &lt;port1&gt;  &lt;port2&gt;   //docker run -P 会随机映射到EXPOSE的端口
>
> WORKDIR   &lt;工作目录&gt;



