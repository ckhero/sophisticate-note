# RedisObject

## 结构体

> ```
>  typedef struct redisObject {
>         unsigned type:4;// 数据类型 string、hash、list、set、zset
>         unsigned encoding:4; //物理编码方式
>         unsigned lru:REDIS_LRU_BITS; /* lru time (relative to server.lruclock) */
>         int refcount;
>         void *ptr;
>     } robj;
> ```



