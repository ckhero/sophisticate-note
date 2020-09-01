AOF

## 资料

> [https://segmentfault.com/a/1190000015983518](https://segmentfault.com/a/1190000015983518)

AOF 记录每次的写操作命令，重启的时候会重新执行这些命令恢复数据

```
  appendfsync everysec ：

        always 把每个写命令立即同步到aof，非常慢

       everysec 每一秒同步一次，比较折中（通常的方案，最多丢失一秒的数据）

        no redis不处理，交给os处理，非常快也不安全
```

> 命令写入 -&gt; aof 重写
>
> 命令写入 -&gt; aof\_buf -&gt; 同步到aof磁盘。避免实时写入磁盘带来的高io，影响性能
>
> 重写阶段发生的变化会同时写入aof\_buf 和 aof rewrite buf 避免重写失败数据丢失

## 缺点

> * 生成的文件大，回复速度慢
> * 相对而言开启AOF的QPS比RDB的QPS性能低



