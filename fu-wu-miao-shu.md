# 服务描述

## 资料

> [https://blog.csdn.net/haponchang/article/details/90746408](https://blog.csdn.net/haponchang/article/details/90746408)

## 简述

> 服务调用首先要解决服务如何对外描述。包括服务名，入参，出参格式，如何解析

## 常见的解决方案



| 方式 | 使用场景 | 缺点 |
| :--- | :--- | :--- |
| resetfull api | 跨语言平台，组织内外都可用 | 使用http作为通讯协议，相比tcp性能较差 |
| xml | Java平台，一般做组织内部 | 不支持跨语言平台 |
| IDL | 跨语言平台，组织内外都可用 | 修改不能向前兼容 |


