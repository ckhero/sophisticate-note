# 持久化 方案

> https://segmentfault.com/a/1190000015983518
>
> https://blog.csdn.net/chuanxincui/article/details/89306882
>
> https://www.cnblogs.com/zxs117/p/11242026.html



## 小结

> 定时任务 timeEvent
>
> redis自带定时任务通过配置文件 hz 10实现，表示1s内执行10次，最大值为500，一般不建议超过100，执行过于频繁会带来CPU的更大消耗。
>
> rdb效率比aof高
>
> 重启后优先启动 aof，因为aof的数据比较完整，最多丢失1s的数据
>
> rdb和aof都是通过fork子进程的方式去做持久化，fork会阻塞主进程，降低fork的频率



