击穿

资料

 [https://blog.csdn.net/sanyaoxu\_2/article/details/79472465](https://blog.csdn.net/sanyaoxu_2/article/details/79472465)

描述 高并发下去访问一个资源，刚好失效。全部打到数据库

     解决方案：

      1. 后台更新 ，逻辑复杂

      2。 二级缓存  浪费空间

      3. 加锁 降低并发

     2，3做选择。权衡，基本都是 3

