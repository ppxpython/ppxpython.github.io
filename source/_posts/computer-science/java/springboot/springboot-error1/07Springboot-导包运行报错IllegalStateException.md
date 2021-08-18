---
title: 07Springboot--  导包运行报错IllegalStateException
tags: Error
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
abbrlink: 16083
date: 2020-10-05 17:12:30
---
 
# 项目场景：

 运行IDEA 时出现错误

# 问题描述：

```bash
java.lang.IllegalStateException: Error processing condition on org.springframework.boot.autoconfigure.context.PropertyPlaceholderAutoConfiguration.propertySourcesPlaceholderConfigurer
```
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/202010051712559.png#pic_center)


# 原因分析：

 依赖
# 解决方案： 

```bash
    <dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-tomcat</artifactId>
<!--	<scope>provided</scope>-->
	</dependency>
```
在pom.xml文件中将scope注释
再加上

```bash
	<dependency>
		<groupId>javax.servlet</groupId>
		<artifactId>javax.servlet-api</artifactId>
		<version>3.1.0</version>
	</dependency>
```
