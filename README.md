# docker-env

build test environment, like mysql, redis,zookeeper and so on.

## 快速开始

为了方便在需要开发环境的时候，能够快速搭建一个环境来使用，避免把时间浪费在不必要的搭建环境的基础上，这里使用docker-compose配置了几个常用的环境，例如centos,mysql,redis等等。

### 启动容器

- 交互模式

```shell
docker-compose up
```

- 后台进程方式

```shell
docker-compose up -d
```

### 关闭容器

```shell
docker-compose down
```

### 进入容器

一般来说，在每个环境的docker-compose.yml里设置了container_name，而这个container_name属性是我们需要的。

```shell
docker exec -ti container_name /bin/bash
```

## MySQL

MySQL数据库快速启动设置

## Redis

Redis快速启动环境
