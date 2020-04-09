# select epoll的区别

## 区别

> 1. select无差别轮询，epoll只轮询活跃的链接
> 2. select 最大连接数 32位 32^32 64位 32^64，epoll 1g内存可以打开10w
> 3. io效率，select随着连接数增加效率变低，epoll只受活跃连接数影响
> 4. epoll是事件驱动，会把哪个链接操作了什么告诉我们，所以我们所有链接的操作都是有意义的
> 5. 内存copy，select从内存copy到用户空间，epoll和用户共享一块内存空间



