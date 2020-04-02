# docker-env

build test environment, like mysql, redis,zookeeper and so on.

## 快速开始

为了方便在需要开发环境的时候，能够快速搭建一个环境来使用，避免把时间浪费在不必要的搭建环境的基础上，这里使用docker-compose配置了几个常用的环境，例如centos,mysql,redis等等。

### 启动容器

启动容器有两种方式：交互模式和后台进程模式。

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

一般来说，在每个环境的docker-compose.yml里设置了container_name，而这个container_name属性的值是我们需要的。

```shell
docker exec -ti container_name /bin/bash
```

对于MySQL来说，docker-compose.yml设置如下：

```yml
version: '3.1'
services:
    mysql:
        image: mysql:5.7.29
        container_name: mysql5.7
        command: mysqld --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci --init-connect='SET NAMES utf8mb4;' --innodb-flush-log-at-trx-commit=0
        volumes: 
            - ./data:/var/lib/mysql
        environment: 
            MYSQL_ROOT_PASSWORD: root
        ports:
        - "3306:3306"
```

那么对应的进入容器内部的方式如下

```shell
docker exec -ti mysql5.7 /bin/bash
```

## MySQL

MySQL数据库快速启动设置

## Redis

Redis快速启动环境
