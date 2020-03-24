Cluster 模式

资料 [https://blog.csdn.net/hguisu/article/details/82979320](https://blog.csdn.net/hguisu/article/details/82979320)

 哨兵模式的缺点是每个slave都存了全部的数据，比较浪费空间

cluster引入哈希槽的概念。 0 ~ 1616383，每个master负责一部分的槽

对key 用crc16进行hash 得到结果再用 1616384 取模确定存放的位置



**Gossip 协议有 meet，pong，ping组成 三次握手**



数据迁移

  node1 -》 node2 node1标记为migrating 。node2标记为importing

请求node1不存在返回ask，再向node2发起asking

存在则返回

部分存在则trying，会得到ask

node2 

 不存在重定向，刷新客户端中的node映射关系

  asking 直接执行



