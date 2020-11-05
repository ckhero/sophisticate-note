# 项目分层

> 参考阿里的项目分层和之前的项目经验

## BFF系统

> 对应我们interface项目
>
> 1. Restful
>    1. 负责接收数据，校验数据
>    2. 有自己的出入参，对应parameter里面的request和reply，用于和前端的交互
> 2. Service
>    1. 有自己的出入参数，放在bean文件里，用In和Out结尾
>    2. 处理业务逻辑



