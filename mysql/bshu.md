# b+树

## 资料

> [https://www.jianshu.com/p/71700a464e97](https://www.jianshu.com/p/71700a464e97)
>
> [https://blog.csdn.net/Fmuma/article/details/80287924](https://blog.csdn.net/Fmuma/article/details/80287924)

## 优点

> 1. 内部节点不存关键信息的指针，好处是io代价低，每个节点能存放更多的key，降低树的高度
> 2. 叶子节点是双向链表，方便范围查找
> 3. 所有查询都要查到叶子节点，查询效率更稳定
> 4. 内部节点索引是有序的，方便二分查找，提高查找效率
> 5. 内部节点更小，这样子同一块磁盘能存放更多的节点。减少了io



