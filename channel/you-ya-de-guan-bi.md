## 优雅的关闭

## 资料

> [https://gfw.go101.org/article/channel-closing.html](https://gfw.go101.org/article/channel-closing.html)

### 通道关闭原则

> * **不要在数据接收方或者多个发送者的情况下关闭通道**
> * 通用原则是 **不要关闭已经关闭的通道**（关闭已关闭的会报恐慌）
> * 向已经关闭的通道发送消息会报恐慌



