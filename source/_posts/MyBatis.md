---
title: MyBatis
date: 2022-03-11 08:55:15
tags:
- MyBatis
---

### MyBatis 是如何进行分页的？

MyBatis 提供了逻辑分页，使用RowBounds实现。先把数据全部查询出来，再根据offset和limit截断返回。
可以再sql中直接书写带有物理分页的参数来完成物理分页功能，也可以使用分页插件来完成。

### MyBatis 插件运行原理

MyBatis可以编写针对ParameterHandler、ResultSetHandler、StatementHandler、Executor 这4中接口的插件。 MyBatis使用JDK动态代理为需要拦截的接口生成代理对象以实现对接口方法得拦截功能。

### MyBatis 是否支持延迟加载

MyBatis仅支持 association 关联对象和 collection 关联集合对象的延迟加载。

### 延迟加载的原理

使用 CGLIB 创建目标对象的代理对象，当调用目标方法时，进入拦截方法。

### ${} 和 #{} 的区别

${} 是字符串替换 #{} 是预处理，#{} 可以有效防止sql注入。

### MyBatis 执行批量插入，能返回数据库主键列表吗

- 对于支持生成自增主键的数据库，使用 useGenerateKeys 和 keyProperty
- 对于不支持生成自增主键的数据库，使用 <selectKey\>

### MyBatis中Executor执行器的区别

- SimpleExecutor：每次执行update/select都开启一个Statement对象，用完立刻关闭。
- ReuseExecutor：执行update/select，以sql作为key查找Statement对象，存在就是用，不存在则创建。
- BatchExecutor：执行update，将sql都添加到批处理中然后逐一执行

