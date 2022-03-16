---
title: elasticsearch
date: 2021-11-19 12:09:04
tags:
---

## 安装

1. 新建用户

   ```shell
   useradd elsearch
   passwd elsearch
   ```

2. 下载： [https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.5.4.tar.gz](https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.5.4.tar.gz) 

3. 解压

   ```shell
   tar -zxvf elasticsearch-6.5.4.tar.gz
   ```
<!--more-->
4. 配置

   > config/elasticsearch.yml

   ```yaml
   network.host: 0.0.0.0
   # 配置以下三者，最少其一
# [discovery.seed_hosts, discovery.seed_providers, cluster.initial_master_nodes]
   cluster.initial_master_nodes: ["node-1"]

   xpack.security.enabled: true
   xpack.security.transport.ssl.enabled: true
   ```
   
   > config/jvm.options

   ```properties
# network.host 如果不是localhost 或者 127.0.0.1，会默认为生产环境，对环境要求较高。机器内存较大不需要修改
   -Xms1g
   -Xmx1g
   ```

   > /etc/sysctl.conf
   
   ```properties
   vm.max_map_count=655360
   ```
   
   ```bash
   # 使上面的配置生效
   sysctl -p
   ```
   
5. 密码配置

   ```shell
   ./bin/elasticsearch-setup-passwords auto
   ```

6. 密码重置

   > config/elasticsearch.yml

   注释掉 `xpack.security.enabled: true` 重启es，删除索引 `.security-7` 

7. 

启动常见错误：

> ERROR: [1] bootstrap checks failed
> [1]: max file descriptors [65535] for elasticsearch process is too low, increase to at least [65536]

```bash
vim /etc/security/limits.conf
```

```properties
* soft nofile 65536
* hard nofile 65536
* soft nproc 2048
* hard nproc 4096
```

重新登录后生效

## 基本概念

> 索引

一个 索引 类似于传统关系数据库中的一个 数据库 ，是一个存储关系型文档的地方。

> 文档

类似于传统关系数据库中的一个表结构









