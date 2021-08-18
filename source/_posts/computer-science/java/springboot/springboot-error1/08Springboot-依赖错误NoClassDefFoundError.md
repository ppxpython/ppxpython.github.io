---
title: 08Springboot-- 依赖错误NoClassDefFoundError
tags: Error
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
abbrlink: 314
date: 2020-10-05 17:17:21
---
 
# 项目场景：

前后端启动成功没有错误，但在登录是出现错误

# 问题描述：
前后端启动成功没有错误，但在登录是出现![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005171754870.png#pic_center)
后端呢SpringBoot报出错误
```bash
 ERROR c.e.c.f.w.e.GlobalExceptionHandler - [handleException,83] - Handler dispatch failed; nested exception is java.lang.NoClassDefFoundError: javax/xml/bind/DatatypeConverter
```
  


# 原因分析：

 JDK版本号是：
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005171833209.png#pic_center)
今天在使用JDK 13.0 环境下使用IDEA 时候出现了这个错误，错误日志如下：
 我是采用了增加依赖解决的
故障原因：
JAXB API是java EE 的API，因此在java SE 9.0 中不再包含这个 Jar 包。
java 9 中引入了模块的概念，默认情况下，Java SE中将不再包含java EE 的Jar包
而在 java 6/7 / 8 时关于这个API 都是捆绑在一起的
# 解决方案： 

 ## 解决方案一： 
降低JDK 版本到 JDK 8
## 解决方案二:（亲测可行）
手动加入这些依赖Jar包

```bash
<dependency>
        <groupId>javax.xml.bind</groupId>
        <artifactId>jaxb-api</artifactId>
        <version>2.3.0</version>
    </dependency>
    <dependency>
        <groupId>com.sun.xml.bind</groupId>
        <artifactId>jaxb-impl</artifactId>
        <version>2.3.0</version>
    </dependency>
    <dependency>
        <groupId>com.sun.xml.bind</groupId>
        <artifactId>jaxb-core</artifactId>
        <version>2.3.0</version>
    </dependency>
    <dependency>
        <groupId>javax.activation</groupId>
        <artifactId>activation</artifactId>
        <version>1.1.1</version>
    </dependency>
```
