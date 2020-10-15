# 锁表场景

> 8.0 [https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-operations.html](https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl-operations.html)
>
> 5.6 [https://dev.mysql.com/doc/refman/5.6/en/innodb-online-ddl-operations.html](https://dev.mysql.com/doc/refman/5.6/en/innodb-online-ddl-operations.html)
>
> 5.7 [https://dev.mysql.com/doc/refman/5.7/en/innodb-online-ddl-operations.html](https://dev.mysql.com/doc/refman/5.7/en/innodb-online-ddl-operations.html)

## 索引操作

| 操作 | 5.6 | 5.7 | 8.0 |
| :--- | :--- | :--- | :--- |
| 创建二级索引 | No | No | No |
| 删除索引 | No | No | No |
| 索引改名字 | / | No | No |
| 添加全文索引 | Yes | Yes | Yes |
| 添加空间索引 | / | Yes | Yes |
| 更改索引类型 | No | No | No |

## 主键操作

| 操作 | 5.6 | 5.7 | 8.0 |
| :--- | :--- | :--- | :--- |
| 添加主键 | No | No | No |
| 删除主键 | Yes | Yes | Yes |
| 删除并添加 | No | No | No |

## 字段操作

| 操作 | 5.6 | 5.7 | 8.0 |
| :--- | :--- | :--- | :--- |
| 增加字段 | No\*\[添加自增字段锁表\] | No\*\[添加自增字段锁表\] | No\*\[添加自增字段锁表\] |
| 删除字段 | No | No | No |
| 修改字段名字 | No\*\[仅仅改变名字的时候不锁表\] | No\*\[仅仅改变名字的时候不锁表\] | No\*\[仅仅改变名字的时候不锁表\] |
| 字段重排序 | No | No | No |
| 设置默认值 | No | No | No |
| 更改字段类型 | Yes | Yes | Yes |
| 修改varchar size | No | No | No |
| 删除默认值 | No | No | No |
| 修改auto-increment 的值 | No | No | No |
| making column NULL | No | No | No |
| making column NOT NULL | No | No | No |
| 修改enum和set的字段 | No | No | No |



