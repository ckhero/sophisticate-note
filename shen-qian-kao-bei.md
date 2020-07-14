# 深浅拷贝

## 资料

> [https://www.cnblogs.com/guichenglin/p/12736203.html](https://www.cnblogs.com/guichenglin/p/12736203.html)

## 简述

> 深拷贝
>
> 拷贝的是数据本身，创造一个新的对象。新对象与原对象不共享内存。新创建的对象会开辟一个新的内存空间，新对象的值修改，不影响原对象，
>
> 值类型的数据，默认是深拷贝：Array Int String Struct Float Bool
>
>
>
> 浅拷贝
>
> 拷贝的是数据地址，只复制指向对象的指针，此时新老对象指向的内存地址是一样的，新对象值修改会影响老对象的值。释放内存地址时会释放老对象的值
>
> 引用类型的数据，默认全部是浅copy，slice，map



