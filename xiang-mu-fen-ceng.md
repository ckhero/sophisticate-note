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
>    2. 处理具体的业务逻辑
>    3. 目录位置: pkg/service 
> 3. Manager
>    1. 对第三方的接口的封装，预处理结果和转化异常信息，适配上层接口。包括RPC接口放在pkg/mgr/rpc下面
>    2. 对service层通用能力的下沉，如缓存方案，公共方法，中间件处理等

## 模块系统

> 对应我们的子系统，如user，rebate，merhant等
>
> 1. Rpc
>    1. 负责接收数据，校验数据
> 2. Service
>    1. 有自己的出入参数
>    2. 处理具体的业务逻辑
>    3. 目录位置: pkg/service
> 3. Manager
>    1. 对service层通用能力的下沉
>    2. 与DAO层的交互，Dao层的组合复用，事务处理
>    3. 目录位置:pkg/mgr
> 4. DAO
>    1. 与数据库交互
>    2. sql语句
>    3. 目录位置:pkg/dao

## 层级关系

> 1. Resetful-&gt;Service-&gt;Manger-&gt;RPC
>    1. service可以直接调用RPC
>    2. manager可以调用RPC
>    3. service可以调用manager
>    4. manager不能调用service，包括结构体
> 2. Rpc-&gt;Service-&gt;Manager-&gt;DAO
>    1. service 可以调用DAO
>    2. manager可以调用DAO
>    3. service 可以调用manager
>    4. manager不能调用service



