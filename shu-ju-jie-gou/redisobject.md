# RedisObject

## 资料

> [https://blog.csdn.net/qq\_35433716/article/details/82177585](https://blog.csdn.net/qq_35433716/article/details/82177585)

## 结构体

> ```
>  typedef struct redisObject {
>         unsigned type:4;// 数据类型 string、hash、list、set、zset
>         unsigned encoding:4; //物理编码方式
>         unsigned lru:REDIS_LRU_BITS; /* lru time (relative to server.lruclock) */
>         int refcount;//refcount表示对象的引用计数。
>         void *ptr; //ptr指针指向真正的存储结构
>     } robj;
> ```

## 物理编码方式

> ```
> #define REDIS_ENCODING_RAW 0     /* Raw representation */
>     #define REDIS_ENCODING_INT 1     /* Encoded as integer */
>     #define REDIS_ENCODING_HT 2      /* Encoded as hash table */
>     #define REDIS_ENCODING_ZIPMAP 3  /* Encoded as zipmap */
>     #define REDIS_ENCODING_LINKEDLIST 4 /* Encoded as regular linked list */
>     #define REDIS_ENCODING_ZIPLIST 5 /* Encoded as ziplist */
>     #define REDIS_ENCODING_INTSET 6  /* Encoded as intset */
>     #define REDIS_ENCODING_SKIPLIST 7  /* Encoded as skiplist */
> ```



![](/assets/redis-encoding.png)



