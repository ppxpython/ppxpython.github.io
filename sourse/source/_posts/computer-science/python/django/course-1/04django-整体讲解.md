---
title: 04django--整体讲解
tags: Django
categories:
  - - 计算机科学
    - Python
    - Django框架
    - 零基础学Django框架
abbrlink: 56296
date: 2020-10-05 15:48:26
---
 日期：2019——09——27
IT人：小海豚
学习内容：
导包的文件

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005154700648.png#pic_center)

​

一般都不用但不能够删除


​![](https://img-blog.csdnimg.cn/2020100515471044.png#pic_center)



settings配置文件
urls统一资源编译器
wsgi网管接口
app中
News
大部分功能在app news中完成
Mingrations

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005154746558.png#pic_center)
 
​

数据库映射时使用，一般不修改
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005154754927.png#pic_center)

 
​

admin管理文件
apps定义app名字
models模型写数据库
tests测试文件
urls配置app的urls，和项目的urls进行交互
views视图文件
Bd.sqlite3默认使用的数据库
Manage.py项目管理文件