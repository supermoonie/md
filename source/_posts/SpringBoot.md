---
title: SpringBoot
date: 2022-03-10 20:06:43
tags: 
- Spring 
- SpringBoot
---

### SpringBoot自动装配原理

- 启动类上的 `SpringBotApplication` 会在类启动时为SpringBoot开启一个 `EnableAutoConfiguration` 注解自动配置功能
- 有了 `EnableAutoConfiguration` 就会
  - 从 `META-INF/spring.factories` 加载可能用到的自动配置类
  - 去重，并将exclude和excludeName携带的类排除
  - 过滤，`@ConditionOnXXX`
    
<!-- more -->
    
### SpringBoot配置加载顺序

- properties 文件
- YAML 文件
- 系统环境变量
- 命令行参数

### bootstrap.properties 和 application.properties 的区别

- bootstrap：由父ApplicationContext 加载，配置在应用程序上下文的引导阶段生效。一般用在Spring Cloud配置中使用这个文件。
- application：由ApplicationContext 加载，用于SpringBoot 项目的自动化配置。