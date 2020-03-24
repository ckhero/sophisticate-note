更新策略

资料 [https://cloud.tencent.com/developer/article/1344228](https://cloud.tencent.com/developer/article/1344228)

facebook的做法  先更新数据再删除缓存

缺点。

 a写，b读 的时候刚好失效。b在a写完之前读取旧的数据，然后在a删除缓存之后去更新缓存。避免的方法是延迟删除，减少这种发生的概率

如果面试官问你 删除后 高并发怎么办。考虑缓存击穿的问题

