小结

slave启动后向master发起sync请求，master收到后开启bgsave，然后向slave发送快照数据。bgsave和发送阶段使用缓冲区记录操写命令。salve收到快照后，载入快照。master在快照发送完后会将缓冲区的命令同步给slave。

slave完成快照载入和缓冲区的命令执行完毕后，完成初始化操作。后续的master每执行一个一个命令都会同步给slave，

如果期间断开2.8后会将断开链接这段时间的数据增量复制给slave

建立连接的时候全量同步，后续是增量同步

优点

> master自动同步给slave 读写分离，减轻master的读压力
>
> slave也可以同步给其他的salve，减轻master的同步压力

缺点

> 不具备容错 和自动回复。master宕机需要等待重启或者切换ip
>
> 不具备高可用，master宕机后，未同步的数据为丢失，
>
> 多个salve重启的时候，分开重启，减轻master的io压力
>
> 较难支持在线扩容。扩容复杂



