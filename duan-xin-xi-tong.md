# 短链系统

> https://www.cnblogs.com/wanghui-garcia/p/10421659.html



## 短链生成

> * 发号器策略
> * uuid.New4\(\).String
>   * 利用本var Reader io.Reader 强随机商户生成器生成随机数
>   * 然后利用version  ，variant对随机数变体
>   * 最后吧4位byte转成8位的16进制
> * 把生成的32位uuid，四位一个组合的16进制转成32位的整型得到 res
> * res%62得到chars数组的索引，拼接成8字节的短链

## 可能出现的问题

> 1. 重复问题
>    1. 利用uuid将此概率降到最低
>    2. 数据做唯一索引



