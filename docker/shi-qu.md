# 时区

> [https://blog.csdn.net/evilcry2012/article/details/54315170](https://blog.csdn.net/isea533/article/details/87261764)

## 命令

> ```
> RUN apk update apk add tzdata
> RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
> RUN echo 'Asia/Shanghai' >/etc/timezone
> ```



