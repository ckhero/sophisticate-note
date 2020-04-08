# hystrix

## 资料

> [https://segmentfault.com/a/1190000012439580](https://segmentfault.com/a/1190000012439580)
>
> [https://blog.csdn.net/loushuiyifan/article/details/82702522](https://blog.csdn.net/loushuiyifan/article/details/82702522)
>
> [https://www.cnblogs.com/li-peng/p/11050563.html](https://www.cnblogs.com/li-peng/p/11050563.html)

## 流程

> 利用HystrixCommand或者HystrixObservableCommand对请求进行包装，然后判断是否熔断，线程池是否已满，如果满足直接走降级逻辑。否则执行请求，请求失败或者超时走降级逻辑，否则返回结果

## 设计目标

> * 对来自依赖的延迟和故障进行防护和控制
> * 阻止故障的连锁反应
> * 快速失败并且迅速恢复
> * 回退并且优雅降级
> * 提供近实时的监控和告警

## 如何实现

> * 使用命令行模式把对外部的调用包装在HystrixCommand或者HystrixObservableCommand对象中，然后放在单独的线程中去执行
> * 每个依赖都维护这一个线程池（或者信号量），线程池被耗尽则拒绝请求
> * 记录请求成功 失败 被拒 超时
> * 服务错误超过百分比，熔断打开，一段时间内停止对该服务的所有请求
> * 请求失败 被拒 则执行降级逻辑
> * 近实时的监控指标和配置变更

## 容错

* ### 资源隔离

> 对线程的隔离，主要通过线程池和信号量进行隔离

* ### 熔断
* ### 降级

## hystrix-go

#### 统计控制器

> 默认统计控制器记录着熔断器的所有状态，调用次数，失败次数 ，被拒次数
>
> ```
> type DefaultMetricCollector struct {
>     mutex *sync.RWMutex
>
>     numRequests *rolling.Number
>     errors      *rolling.Number
>
>     successes               *rolling.Number
>     failures                *rolling.Number
>     rejects                 *rolling.Number
>     shortCircuits           *rolling.Number
>     timeouts                *rolling.Number
>     contextCanceled         *rolling.Number
>     contextDeadlineExceeded *rolling.Number
>
>     fallbackSuccesses *rolling.Number
>     fallbackFailures  *rolling.Number
>     totalDuration     *rolling.Timing
>     runDuration       *rolling.Timing
> }
> ```
>
> Number保存了10秒内的Buckets数据信息，每个Bucket统计时长1秒
>
> ![](/assets/import-hystix.png)
>
> 字典字段
>
> `Buckets map[int64]*numberBucket`
>
> 中的
>
> `Key`
>
> 保存的是当前时间
>
> 每一次熔断器的状态修改都会先回去当前的时间戳 妙级的，没有则创建。修改完后去掉10s外的数据

### 流量控制

> 根据最大并发数，创建令牌桶，能得到令牌就执行，执行完后归还令牌



