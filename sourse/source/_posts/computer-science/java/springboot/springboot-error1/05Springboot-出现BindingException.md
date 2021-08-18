---
title: 05Springboot--出现BindingException
tags: Error
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
abbrlink: 2954
date: 2020-10-05 17:00:28
---
 
# 项目场景：

 IDEA在启动时出现错误

# 问题描述：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170050317.png#pic_center)

   
```bash
2020-09-21 21:08:06.650 ERROR 23480 --- [nio-9000-exec-3] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed; nested exception is org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.example.mysportjava.dao.UserDao.getUserByMassage] with root cause

org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.example.mysportjava.dao.UserDao.getUserByMa
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170117931.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


# 原因分析：
多出空格
 
# 解决方案：

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170138566.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

  [ 我的博客，欢迎点击光顾](https://ppxpython.github.io/)
