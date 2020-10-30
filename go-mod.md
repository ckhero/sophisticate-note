# Go Mod

> [https://colobu.com/2018/08/27/learn-go-module/](https://colobu.com/2018/08/27/learn-go-module/)

## 简述

> * go mod tidy //增加丢失的依赖，删除不需要的依赖
> * // indirect
>   * 表示依赖不是直接引用，是依赖的依赖
>   * go mod why  &lt;包名&gt;  // 查看被谁依赖

## demo

> git私有仓库配置:
>
> golang 环境变量配置\(根据自己的操作系统来\):     
>
> \# 私有仓库跳过https验证
>
> export GOINSECURE=git.zk020.cn
>
> \# 下载包走代理
>
> export GO111MODULE=on
>
> export GOPROXY=https://goproxy.io,direct
>
> \# 私有仓库的配置
>
> export GOPRIVATE=\*.zk020.cn
>
> export GIT\_TERMINAL\_PROMPT=1



