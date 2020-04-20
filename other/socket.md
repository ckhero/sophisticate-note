# socket

## 简述

> 套接字，计算机中通信的一种约定或一种方式
>
> unix/linux   未打开的文件分配一个整数ID，就是文件描述。网络连接也是个文件，也有文件描述
>
> windows 文件句柄，区分scoket 和文件，把socket当做一个网络连接对待

## 类型

#### 流格式套接字（SOCK\_STREAM）面向连接的套接字【TCP】

> * **数组在传输过程中不会消失**
> * **顺序传递  **tcp协议\(传输控制协议\),控制数据按照顺序达到并不出错。保证数据的准确性
> * **数据发送和结束不同步  ** 流式套接字内部有个缓冲区（字符数组）,通过socket传输的数据保存到这个缓冲区。接收端收到数据后不一定直接读取。

#### 数据报格式套接字\(SOCK\_DGRAM\) 无连接的套接字【UDP】

> 不可靠的，不按顺序传递，追求速度为目的的套接字
>
> * **强调效率不保证顺序**
> * **传输的数据可能丢失**
> * **限制每次传输的大小**
> * **数据的发送和j接受是同步的**


