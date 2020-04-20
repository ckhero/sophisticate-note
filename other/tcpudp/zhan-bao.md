# 沾包

## 简述

> 客户端发送的多个包被当做一个数据包去处理。也称数据的无边界性，read/recv不知道数据包的开始和结束标识，只能当做连续的数据流去处理
>
> tcp的数据发送和接收是无关。read和recv会尽可能多的从接收缓冲区读取数据，所有发送三次 abc，有可能一次独处abcabcabc。服务器把三次发送的消息当做一次去处理

## 解决思路

> * 消息定长
> * 消息之前用特殊符号区分
> * 显示长度，如先发送消息长度，再发送消息
> * 组合上面的各种策略

## http协议的解决策略

> 请求头用特殊符号（\r\n）结束，如果有请求体，请求头中会有表示请求体的长度


