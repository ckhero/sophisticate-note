TCP/UDP

## 资料

> [https://www.cnblogs.com/fundebug/p/differences-of-tcp-and-udp.html](https://www.cnblogs.com/fundebug/p/differences-of-tcp-and-udp.html)
>
> 实现可靠的UDP [https://www.jianshu.com/p/6c73a4585eba](https://www.jianshu.com/p/6c73a4585eba)
>
> TCP如何实现可靠性的传输 [https://blog.csdn.net/wodewutai17quiet/article/details/82252454](https://blog.csdn.net/wodewutai17quiet/article/details/82252454)
>
> [http://c.biancheng.net/view/2358.html](http://c.biancheng.net/view/2358.html)

|  |
| :--- |


|  | UDP | TCP |
| :--- | :--- | :--- |
| 是否连接 | 无连接 | 面向连接 |
| 是否可靠 | 不可靠传输，不使用流量控制和拥塞控制 | 可靠传输，使用流量控制和拥塞控制 |
| 连接对象个数 | 支持一对一，一对多，多对一和多对多交互通信 | 只能是一对一通信 |
| 传输方式 | 面向报文 | 面向字节流 |
| 首部开销 | 首部开销小，仅8字节 | 首部最小20字节，最大60字节 |
| 适用场景 | 适用于实时应用（IP电话、视频会议、直播等） | 适用于要求可靠传输的应用，例如文件传输 |

## UDP实现可靠传输

> * 添加seq/ack机制，确保数据发送到对端
> * 添加发送和传输缓存，主要是用户超时重传
> * 添加超时重传

## TCP如何实现可靠性的传输

> * 三次握手建立连接
> * 确认应答和 序列号
> * 超时重传 利用 序列号去重
> * 流量控制  发送端接收到都有缓冲区
> * 拥塞控制



