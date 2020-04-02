# 应用场景

## 资料

> [https://www.cnblogs.com/yuanjiangw/p/10382423.html](https://www.cnblogs.com/yuanjiangw/p/10382423.html)

* ## 解耦

> * 传统模式 A系统为B C D提供服务，每增加一个系统都要修改A的代码
>
> * 解耦之后  相关系统只需要去订阅对应的主题就行，无需修改a的代码。
>
>   eg. 订单状态的流转

* ## 异步

> * 传统模式 A-&gt; B -&gt; C,一些非要的逻辑影响接口效率
>
> * 异步模式  A-&gt;消息中间件 &lt;-B-&gt;C
>
> eg. 登录后发送短信通知

* ## 削峰（削的数据库请求量）

> * 传统模式 并发请求-&gt;系统A-&gt;数据库，直接打到数据库，容易造成数据连接异常
> * 削峰模式 并发请求-&gt;消息队列 &lt;- 系统A-&gt;数据库。按照数据库的性能去处理并发量。在生成中，短暂的高峰是允许的。
>
>   eg.秒杀下单

## 缺点

> * 降低系统的可用性，需要保证消息中间件的高可用。
> * 系统复杂度增加
>
>   ```
>     需要保证数据一致性
>     需要保证消息不被重复消费
>
>    需要保证消息的可靠传输
>   ```


