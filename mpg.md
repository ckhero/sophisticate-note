## MPG

## 资料

> [https://i6448038.github.io/2017/12/04/golang-concurrency-principle/](https://i6448038.github.io/2017/12/04/golang-concurrency-principle/)
>
> 调优[https://www.cnblogs.com/linguanh/p/9510746.html](https://www.cnblogs.com/linguanh/p/9510746.html)

M 真正的计算机资源可以理解为 os thread

P 逻辑处理，M的上下文，对应一个处理队列

G 调度的最小单位，保存了goroutine的stack。goroutine运行状态和goroutine执行函数

G产生的时候会找一个可用P加入该P的工作队列。P会去寻找一个可用的M 去执行自身队列里面的goroutine

如果关联的M阻塞，P会去寻找下一个可用的M，如果找不到可用的M会去创建新的M。如果P的队列为空，他会去找其他的P的处理队列和全局的处理队列的任务 拿一半过来处理

