# 事务特性的原理

## 资料

> [https://www.cnblogs.com/kismetv/p/10331633.html](https://www.cnblogs.com/kismetv/p/10331633.html)

## 持久性

> mysql把数据写入缓冲池，然后有个线程会把缓冲池里面的数据同步到磁盘。如果宕机会导致数据丢失。所以写入的时候会把数据库写入redo\_log，通过redo\_log来恢复数据。因为redo\_log是顺序写入，开销低。缓冲池的同步是页级的数据，数据传输大

## 原子性

> mysql会把写操作的逆向命令写入undo\_log。如果发生回滚通过undo\_log来进行，保障事务原子性

## 隔离性

> 读写锁+MVCC

## 一致性

> 通过其他三个特性来保证一致性



