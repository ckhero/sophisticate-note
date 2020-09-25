# 压缩

## 资料

> [https://zhuanlan.zhihu.com/p/43319212](https://zhuanlan.zhihu.com/p/43319212)
>
> [https://blog.csdn.net/bbwangj/article/details/82178774](https://blog.csdn.net/bbwangj/article/details/82178774)
>
> 完整 [http://dockone.io/article/8163](http://dockone.io/article/8163)

## 方法

> 1. 使用专为docker而生的linux系统 apline
> 2. 每个RUN COPY对应一层可以结合操作
> 3. 多阶段构建，比如golang的编译阶段的配置在运行阶段是不需要的。可以舍弃
> 4. google 的distroless



