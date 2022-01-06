---
title: '05Springboot--数据库拼写错误BindingException: Invalid bound statement '
tags: Error
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
abbrlink: 22577
date: 2020-10-05 17:04:01
---
 
# 项目场景：

 运行IDEA 时出现错误

# 问题描述：

```bash
org.apache.ibatis.binding.BindingException: Invalid bound statement (not found): com.example.mysportjava.dao.UserDao.getUserByMassage
 
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170459456.png#pic_center)

# 原因分析：

 映射文件拼写错误

# 解决方案：

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005170519357.png#pic_center)
1 问题实质: dao层(又叫mapper接口)跟mapper.xml文件没有映射
2 问题原因: 出现这种映射问题的原因分为低级原因和更低级原因两种
                     更低级原因:
                                              (1)dao层的方法和mapper.xml中的方法不一样;
                                              (2)mapper中的namespace resultParameter 和对应的dao层entity层不一样
                                              (3)拼写错误 如漏写 少写 多写....
                                              上述这些原因都会导致两者不能映射 这些检查和修正的工作自己来吧不会的百度就行
                  低级原因: spring配置文件中关于mybatis的与xml文件路径寻找相关的配置没有写
                                    导致调用dao层方法时,没有寻找dao.xml文件的正确路径 结果dao迷路了 从而两者无法映射
3 解决思路: 把dao.xml(或mapper.xml)路径配置写好!!!!
                     既然出发点(dao)已经确定,目的地(dao.xml/mapper.xml)也确定了
                     想到到达就必须画一条到dao.xml的路
4 解决步骤:
                   (1)打开spring-context.xml配置文件
                   (2)找到class为org.mybatis.spring.SqlSessionFactoryBean 这个bean
                   (3)找到name为mapperLocations的property
                   (4)在list标签中添加一个value
                                     例如:
                                             <value>classpath:/info/mappings/**/*.xml</value>
                  重启,问题解决!!!
                 注:classpath是配置好的类路径 要想知道表示什么 最简单的方式是参考其他list看一眼比对项目结构就了然了


  [ 我的博客，欢迎点击光顾](https://ppxpython.github.io/)
