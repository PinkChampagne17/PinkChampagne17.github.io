# Redis 基本命令

## 切换数据库
redis默认有16个数据库。

```bash
127.0.0.1:6379> select 3    #切换到3号数据库
OK

127.0.0.1:6379[3]> select 0 #切换到0号数据库
OK
```

## Key
```bash
127.0.0.1:6379> set name morty
OK

127.0.0.1:6379> get name
"morty"

127.0.0.1:6379> set name2 rick
OK

127.0.0.1:6379> keys *  # 获取当前数据库所有的key
1) "name"
2) "name2"

127.0.0.1:6379> dbsize  # 返回当前数据库keys的数量
(integer) 2
```

## 清空数据库
```bash
127.0.0.1:6379> flushdb     #清空当前数据库
OK

127.0.0.1:6379> flushall    #清空所有数据库
OK
```


