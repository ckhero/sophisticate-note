# 并发数控制

> https://zhuanlan.zhihu.com/p/153093074

## 简述

> 利用缓存channnel，channel类型使用struct{}，因为struct{}内存占用大小为0

```
func UseChan() {
	ch := make(chan struct{}, 5)
	for  {
		 i := 1
		ch <- struct{}{}
		go func(t int) {
			defer func() {
				<-ch
			}()
			fmt.Printf("G - %d \n", t)
		}(i)
	}
}
```



