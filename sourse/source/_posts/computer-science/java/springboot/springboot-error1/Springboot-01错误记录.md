---
title: Springboot--01错误记录
tags: Error
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
abbrlink: 21245
date: 2020-10-05 16:46:35
---
 问题1：
Identify and stop the process that's listening on port 8080 or configure this application to listen on another port.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005164657909.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516470549.png#pic_center)




问题2
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516471577.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


二、解决方式：
1.检查自己写的注解是否错了，并没有。
2.在网上查找解决方式：如下所示：
步骤一：
　　在springboot的配置文件添加，mybatis的配置如下所示：
　　

```bash
mybatis:
  typeAliasesPackage: com.xxx.xxx.dao.entity
  mapperLocations: classpath:mapper/*.xml
```

 
 步骤二：
　　①将接口与对应的实现类放在与application启动类的同一个目录或者他的子目录下，这样注解可以被扫描到，这是最省事的办法。（没测试）
　　②或者在启动类上加上@MapperScan或者@ComponentScan注解，手动指定application类要扫描哪些包下的注解，如下所示： 
　　

```bash
@SpringBootApplication
@ComponentScan(basePackages = {"com.xxx.xxx.dao"})
　　③或者在接口上添加@Mapper注解。
@Mapper
public interface UserMapper {
}

```

 

问题3：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005164810350.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

原因：
修改了mapper类的名称对应要修改路径
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005164820942.png#pic_center)

问题4：
添加数据时未添加外键
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005164831130.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

添加sql输入外键unit_ID
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516484178.png#pic_center)

问题5:
 

```bash
Error starting ApplicationContext. To display the conditions report re-run your application with 'debug' enabled.
2020-09-12 14:40:39.211 ERROR 60268 --- [           main] o.s.boot.SpringApplication               : Application run failed
```

 
常见注释错误，查看代码中的@注释
问题6:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005164915811.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

问题7：
在测试的时候报出
415
更改一下请求头

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005165030667.png#pic_center)
