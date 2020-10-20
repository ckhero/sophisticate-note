# content-length

> [https://cloud.tencent.com/developer/article/1501751](https://cloud.tencent.com/developer/article/1501751)

## 简述

> 1. http 1.0  
>    1. 这个字段可有可无
> 2. 如果开启gizp  content-lenght 是压缩后的长度
> 3. content-lenght &gt; 实际长度
>    1. 导致请求超时，服务端会一直等超出的字段数据
> 4. content—length &lt; 实际长度
>    1. 会被截取
>    2. 如果是keep alive的状态，后续请求会报错
>    3. 如果不是keep alive  ，后续一直被截取
> 5. 不确定content-length
>    1. 使用Transfer-Encoding: chunked，content-lenght会被忽略



