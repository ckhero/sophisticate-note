# 精确一次消费

## 资料

> [https://blog.csdn.net/qq\_18581221/article/details/89766073](https://blog.csdn.net/qq_18581221/article/details/89766073)

## 简述

> 比如kafka，手动提交offset

## 消息有状态

> 比如订单状态，可以根据状态去做

## 目标容器有幂等性

> 比如消息要投递容器是es，本身具有幂等性

## 消息无状态，目标容器没有幂等性

> 通过数据库去做幂等操作，记录分区和offset



