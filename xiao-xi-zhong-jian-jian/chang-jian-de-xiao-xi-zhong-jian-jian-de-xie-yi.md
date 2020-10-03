常见的消息中间件的协议

**6.1 AMQP协议**

> AMQP即Advanced Message Queuing Protocol,一个提供统一消息服务的应用层标准高级消息队列协议,是应用层协议的一个开放标准,为面向消息的中间件设计。基于此协议的客户端与消息中间件可传递消息，并不受客户端/中间件不同产品，不同开发语言等条件的限制。  
> 优点：**可靠、通用**

**6.2 MQTT协议**

> MQTT（Message Queuing Telemetry Transport，消息队列遥测传输）是IBM开发的一个即时通讯协议，有可能成为物联网的重要组成部分。该协议支持所有平台，几乎可以把所有联网物品和外部连接起来，被用来当做传感器和致动器（比如通过Twitter让房屋联网）的通信协议。  
> 优点：**格式简洁、占用带宽小、移动端通信、PUSH、嵌入式系统**

**6.3 STOMP协议**

> STOMP（Streaming Text Orientated Message Protocol）是流文本定向消息协议，是一种为MOM\(Message Oriented Middleware，面向消息的中间件\)设计的简单文本协议。STOMP提供一个可互操作的连接格式，允许客户端与任意STOMP消息代理（Broker）进行交互。  
> 优点：**命令模式（非topic\queue模式）**

**      6.4 XMPP协议**

> > XMPP（可扩展消息处理现场协议，Extensible Messaging and Presence Protocol）是基于可扩展标记语言（XML）的协议，多用于即时消息（IM）以及在线现场探测。适用于服务器之间的准即时操作。核心是基于XML流传输，这个协议可能最终允许因特网用户向因特网上的其他任何人发送即时消息，即使其操作系统和浏览器不同。  
> > 优点：通用公开、兼容性强、可扩展、安全性高，但XML编码格式占用带宽大

**6.5 其他基于TCP/IP自定义的协议**

> 有些特殊框架（如：redis、kafka、zeroMq等）根据自身需要未严格遵循MQ规范，而是基于TCP\IP自行封装了一套协议，通过网络socket接口进行传输，实现了MQ的功能。



