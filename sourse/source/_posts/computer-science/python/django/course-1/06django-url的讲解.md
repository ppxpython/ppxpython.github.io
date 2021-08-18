---
title: 06django--url的讲解
tags: Django
categories:
  - - 计算机科学
    - Python
    - Django框架
    - 零基础学Django框架
abbrlink: 18420
date: 2020-10-05 15:57:17
---
 日期：2019——09——28
IT人：小海豚
学习内容：
统一资源定位器
协议protocol：http，https，ftp
域名hostname+端口port
路径path
参数parmeters
查询query
描点fragment
django中配置urls
创建一个newwebsite002的django文件和book的app
命令行输入

```bash
django-admin startproject newwebsite002
```

```bash
cd newwebsite002
```

```bash
ptrhon manage.py startapp book
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155244250.png#pic_center)

​

显示出

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155505621.png#pic_center)

​

在浏览器中检查
开启服务器

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155519786.png#pic_center)

​

成功

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155528944.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在setting中配置注册 app book
添加'book',

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155537408.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在app views视图中写入两个函数

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155546495.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​


在app book中创建一个urls文件
进行配置

![在这里插入图片描述](https://img-blog.csdnimg.cn/202010051555572.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在app book urls中编码

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100515560640.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在项目中做个映射
在项目newwebsite002的urls中编码


​
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155615113.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


成功

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155623854.png#pic_center)

​


切换网址后


​![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005155631652.png#pic_center)


表示成功
注意：在path语句中在路径中要加上/