---
title: 06Springboot-- 导包错误
tags: Error
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
abbrlink: 22758
date: 2020-10-05 17:06:52
---
 
# 项目场景：

 运行IDEA 时出现错误

# 问题描述：

```bash
Cannot resolve org.apache.tomcat.embed:tomcat-embed-core:9.0.36
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170459456.png#pic_center)

# 原因分析：

刚刚想学习springboot的缓冲机制 在新建项目的时候发现了这么一个错误
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170723193.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170731919.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
这两个都在指明tomcat9.0.36无法下载成功
但是你之前运行其他的spring boot项目是 web依赖的tomcat是可以运行的
这个时候你就会联想到是版本的问题了吧
# 解决方案：

  所以我们可以打开一个之前可以运行的springboot项目
找到右边的maven，点击
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100517084951.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170839795.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
你会发现你的tomcat的版本是其他 我这里是9.0.35， 所以这个时候嘛
我们打开之前无法使用的springboot项目
打开它的pox.xml

 

```bash
  <properties>
        <java.version>1.8</java.version>
    </properties>
```
只需添加成

```bash
 <properties>
        <java.version>1.8</java.version>
        <tomcat.version>你的tomcat版本号</tomcat.version>
    </properties>
```
然后点击左边的maven 再install就ok了![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170947274.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170956861.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
 