redis中的哈希槽

对 16384 取模

区别

> 1 redis集群使用的哈希槽的概念。哈希槽没有直接使用hash算法，使用的是crc16效验算法
>
> 2 一致性哈希使用的是圆环，无法很好的控制数据分布，可能会产生数据倾斜。哈希槽是自定义分配的空间
>
> 3 槽位的转移和分派，redis集群不会自动分配。需要人工干预。另外redis集群的高可用是通过主从同步与主从间的故障转移来实现的

优点

> 再容错性和扩展性上和一致性哈希一致，都是对受影响的数据进行转移，而不影响其他的数据



