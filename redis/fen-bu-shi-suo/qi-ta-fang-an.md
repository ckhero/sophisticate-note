# 其他方案

## 资料

> zookeeper [http://www.imooc.com/article/284956?block\_id=tuijian\_wz](http://www.imooc.com/article/284956?block_id=tuijian_wz)
>
> https://www.zhihu.com/question/65852003/answer/656091418
>
> 数据库

## zookeeper

> 临时顺序节点
>
> 1 创建mylock的锁节点，下面创建顺序节点，线程1   0000001节点，线程2 0000002节点
>
> 2 创建完成后判断最前面那的节点是不是自己的节点，如果是加锁成功，如果不是，加速失败，然后监听上一个节点。
>
> 3 业务处理完后，删除自己的节点。监听线程加锁成功
>
> 4 过程中如果线程1 宕机了。zk会自动释放线程1的节点



