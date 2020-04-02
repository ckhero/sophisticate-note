# dictEntry

## 简述

> Redis 的 KV 结构是通过一个 dictEntry 来实现的。

## 定义如下

> ```
> typedef struct dictEntry {
>   void *key; /* key 关键字定义 */
>   union {
>     void *val; uint64_t u64; /* value 定义 */
>     int64_t s64; double d;
>   } v;
>   struct dictEntry *next; /* 指向下一个键值对节点 */
> } dictEntry
> ```



