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

4. 配置

   > config/elasticsearch.yml

   ```yaml
   network.host: 0.0.0.0
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

## 启动

常见错误：

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









