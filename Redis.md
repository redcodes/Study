# Redis

## 简介

​	Redis是一款内存高速缓存数据库。Redis全称为：**Remote Dictionary Server**（远程数据服务），使用C语言编写，Redis是一个key-value存储系统（键值存储系统），支持丰富的数据类型，如：String、list、set、zset、hash。

​	Redis是一种支持key-value等多种数据结构的存储系统。可用于缓存，事件发布或订阅，高速队列等场景。支持网络，提供字符串，哈希，列表，队列，集合结构直接存取，基于内存，可持久化。

## 优点

- 读写性能优异

  ​	Redis能读的速度是110000次/s,写的速度是81000次/s。

- 数据类型丰富

  ​	Redis支持二进制案例的 Strings, Lists, Hashes, Sets 及 Ordered Sets 数据类型操作。

- 原子性

  ​	Redis的所有操作都是原子性的，同时Redis还支持对几个操作全并后的原子性执行。

- 丰富的特性

  ​	Redis支持 publish / subscribe, 通知, key 过期等特性。

- 持久化

  ​	Redis支持RDB, AOF等持久化方式

- 发布订阅

  ​	Redis支持发布/订阅模式

- 分布式

  ​	Redis Cluster

## 使用场景

​	缓存是Redis最常见的应用场景，主要是因为Redis读写性能优异，成为首选服务端缓存的组件。而且，Redis内部是支持事务的，在使用时候能有效保证数据的一致性。

1. ### 缓存

   - 读取数据前，先读Redis，如果没有数据，读取数据库，将数据存入Redis。

   - 向数据库插入数据时，同时写入Redis。

2. ### 限时业务

   可以使用expire命令设置一个键的生存时间，到时间后Redis会删除它。利用这一特性可以运用在限时的优惠活动信息、手机验证码等业务场景。

3. ### 计数器

4. ### 分布式锁

5. ### 演示操作

6. ### 排行榜

7. ### 点赞

8. ### 简单队列

## 编译

```
wget https://download.redis.io/releases/redis-6.2.4.tar.gz
tar -zxvf redis-6.2.4.tar.gz
cd redis-6.2.4
make
make install
```
## 配置

- 设置服务自启动

```
chkconfig redisd on
service redisd start
service redisd stop
```
- 设置密码

```
# 修改redis.conf配置文件中的requirepass 节点的值
requirepass chrdwHDHXT@522
```
- 对外开放连接

```
protected-mode no
# bind 127.0.0.1
```


## 测试

- 启动服务端

```
./redis-server /home/redis/redis-6.0.8/redis.conf
```

- 客户端连接

```
./redis-cli -h 120.53.233.203 -p 6379 -a chrdwHDHXT@522
```

- python测试

```
[root@VM-0-9-centos src]# python
Python 3.9.5 (default, Jun  3 2021, 23:35:18)
[GCC 4.8.5 20150623 (Red Hat 4.8.5-39)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import redis
>>> r = redis.StrictRedis(host='localhost', port=6379, password='chrdwHDHXT@522')
>>> r.set('foo', 'bar')
True
>>> r.get('foo')
b'bar'
```

## 数据结构

1. 简单动态字符串
2. 列表
3. 字典
4. 渐进式HASH
5. 整数集合
6. 跳跃表
7. 压缩列表
8. 快速列表

## 架构

## 常见问题

