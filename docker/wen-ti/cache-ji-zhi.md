# cache

> 1. docker build 镜像的时候如果某个命令的内容没有发生改变，会使用上一次缓存的文件层
>    1. 不变或者变化很少的体积较大的依赖库和经常修改的自有代码分开
>    2. 固定使用某台机器上 的docker build，可以利用cache



