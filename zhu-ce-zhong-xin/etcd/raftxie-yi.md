# RAFT协议

## 资料

> [https://www.jianshu.com/p/3c6a4fd6a7cc](https://www.jianshu.com/p/3c6a4fd6a7cc)
>
> [https://zhuanlan.zhihu.com/p/27207160](https://zhuanlan.zhihu.com/p/27207160)

## 架构

> 状态机: 当我们说一致性的时候，实际就是在说要保证这个状态机的一致性。状态机会从log里面取出所有的命令，然后执行一遍，得到的结果就是我们对外提供的保证了一致性的数据
>
> Log: 保存了所有修改记录
>
> 一致性模块: 一致性模块算法就是用来保证写入的log的命令的一致性，这也是raft算法核心内容

## 如何保证一致性？

#### **Leader election**

> Leader Follower Candidate
>
> * Leader 所有请求的处理者，接受client的请求，本地处理完后同步给其他的节点，多数同步成功，才算写入成功
>
> * Follower 被动更新，接受Leader的请求，然后写入本地日志文件
>
> * Candidate Follower在一段时间为接收到Leader心跳会变为Candidate，发起新一轮的选举

#### **Log Replication**

> Leader收到客户端的请求后会把命令追加到log中，然后同步给其他的节点。确保多数节点都追加成功后，然后这条命令会追加到状态机里面。之后才返回客户端成功。如果追加过程中网络问题或者follower宕机4，会一直请求指导成功。

#### **Safety**

> Raft保证被选为新leader的j节点拥有所有已提交的log entry。后选择发送投票请求的时候回带上term和index ，通过比较term和index来确定s会否要给他投票

#### **Log Compaction**

#### **集群拓扑变化**

> 先发送要变更的信息，然后再发送变更的确认信息。
>
> 避免直接发送确认信息的时候发生多主的情况

### 脑裂

[https://www.cnblogs.com/williamjie/p/11137118.html](https://www.cnblogs.com/williamjie/p/11137118.html)

> 引入一个新的概念, region leader。region leader 是一个逻辑上的概念, 任意时刻对于某一个 region 来说, 一定只拥有一个 region leader, 每个 region leader 在任期之内尝试每隔 t 时间间隔, 在 raft group 内部更新一下 region leader 的 lease. 所有的读写请求都必须通过 region leader 完成，

# 流程

> 1. follower把自己的term + 1，然后状态变为候选者
> 2. 发送投票消息给其他的服务器
> 3. 受到多数投票者变为leader，并且不定期给其他follower发送信条
> 4. 投票结束后，候选者收到来自leader的消息的时候，把本地term 更新为leader的term
>    1. 选票瓜分候选者等待leader的信息超时，这个超时时间会随机取，第一个超时的人会得到其他人的投票，成为leader，然后发送心跳



