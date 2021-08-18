---
title: 07django--path的语法
tags: Django
categories:
  - - 计算机科学
    - Python
    - Django框架
    - 零基础学Django框架
abbrlink: 2669
date: 2020-10-05 16:02:33
---
 日期：2019——10——06
IT人：小海豚
学习内容：
Path的语法
从django2.1以后用path之前用的是url
标准语法
Path(route,view,name=None,**kwargs)
Route:
端口以后url的地址，到/结束，表示路径
View:
表示路径匹配成功后，需要调用的视图，必须是个函数如果是class的话，必须要用as_view()函数装换为函数
name：
表示别名
**kwargs：
表示一个字典

前面两个是必选项
创建的newwebsite002是之前的，查看06django
教程
在之前的views不变
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160009690.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


​

在之前创建的app book的urls中

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160022822.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

打开项目所在地址cmd开启服务器


​![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160032813.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


成功

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160042503.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

证明服务器已经跑起来了
继续刷新

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160052289.png#pic_center)

​

修改app bookapp中的urls


​![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160101176.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


在输入网址查看
http://127.0.0.1:8000/index

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160110848.png#pic_center)

​

输入http://127.0.0.1:8000/index/web/
查看


​![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160119998.png#pic_center)


也可以写成多分级目录
修改app bookapp中的urls
注释#path('',views.index,name='index'),

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516012813.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

​

在浏览器中执行
http://127.0.0.1:8000/index/web/a/b/c/index.html/


​![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516013813.png#pic_center)


成功
注意：当出现路径相同时，会自动匹配第一个之后机就默认不匹配了


​![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516014867.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


结果一直是：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005160156332.png#pic_center)

​
