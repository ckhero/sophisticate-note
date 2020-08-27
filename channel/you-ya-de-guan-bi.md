## 优雅的关闭

## 资料

> [https://gfw.go101.org/article/channel-closing.html](https://gfw.go101.org/article/channel-closing.html)
>
> [https://www.jianshu.com/p/d24dfbb33781](https://www.jianshu.com/p/d24dfbb33781)

### 通道关闭原则

> * **不要在数据接收方或者多个发送者的情况下关闭通道**
> * 通用原则是 **不要关闭已经关闭的通道**（关闭已关闭的会报恐慌）
> * 向已经关闭的通道发送消息会报恐慌
> * 从无缓冲已关闭的通道里读取数据，会读取空值
> * 从有缓冲已关闭的通道里读取数据，先读取未读取的数据



