---
title: 08django---的装换器
tags: Django
categories:
  - - 计算机科学
    - Python
    - Django框架
    - 零基础学Django框架
abbrlink: 41450
date: 2020-10-05 16:04:50
---
 日期：20019——10——07
IT人：小海豚
学习内容：
装换器
 https://news.163.com/19/0405/08/EC017RFK0001899O.html

https://news.163.com/19/0405/08/EC01HSST000189FH.html
  
在app bookapp的urls中
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160601964.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


​

注意：<html>表示可以是任何字母
在app bookapp的views中写入

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160613503.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在项目的urls中修改以下

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160624600.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在浏览器中输入网址
http://127.0.0.1:8000/19/0405/08/EC01HSST000189FH.html

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160639658.png#pic_center)

​


地址装唤器装换
字符串——》变量接收——》传递path中的<html>变量——》在app bookapp中的index函数的html变量接收到——》在format中输出地址信息
第二个地址
在浏览器中输入
 http://127.0.0.1:8000/19/0405/08/EC017RFK0001899O.html
 

​![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160650493.png#pic_center)


