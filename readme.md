### 需求
```
 - 异地跨机房容灾
 - 故障自动切换
 - 尽可能高的保证数据不丢失

```
### 调研
```
    ......

```
### 目的 

```
redis-sentinel 监控redis 主从同步等问题，当一台redis-master 断开，被sentinel 发现的时候自动切换redis-slave，然后redis-slave 变成master ，以前的master 就变成了slave 服务器，以保证数据不丢失。

相对ks8来说，那个太重，学习成本比较大，所以我选择了这个

```

### 安装
```

docker-compose up -d

```
#### 1.目录结构


```
redis-sentinel
    |
    ----/redis/
            |
            ---/config/
                    |
                    ---/redis.conf
            ---/data/

    ----/sentinel/
            |
            ---/config/
                    |
                    ---/redis.conf
            ---/data/

```
#### 2.配置文件
```
可以参看
    redis
        主 redis-master.conf
        从 redis-slave.conf
    
    sentinel
        主从 redis-sentinel.conf
        它的配置文件是一样的

```
