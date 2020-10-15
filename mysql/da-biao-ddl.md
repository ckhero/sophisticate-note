# 大表DDL

> [https://zvv.me/amp/1313.html](https://blog.csdn.net/eagle89/article/details/105735204?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~sobaiduend~default-1-105735204.nonecase&utm_term=mysql 大表改字段&spm=1000.2123.3001.4430)

## pt-online-schema-change流程

> 1. 创建临时的新表，含索引和新字段
> 2. 创建更新，删除，新增的触发器
>
> 3. 一块一块的复制
>
> 4. 复制完成后修改表名字



