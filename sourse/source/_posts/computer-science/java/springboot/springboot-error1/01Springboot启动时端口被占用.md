---
title: 01Springboot启动时端口被占用
tags: Error
abbrlink: 50465
date: 2020-09-28 12:02:42
categories:
  - - 计算机科学
    - Java
    - SpringBoot框架
    - SpringBoot框架常见错误集合
---
 
# 项目场景：

 Springboot在启动时出现端口8888被占用
# 问题描述：
 Springboot在启动时出现端口被占用
 

```bash
错误提示：
Description:
Web server failed to start. Port 8888 was already in use.
Action:
Identify and stop the process that's listening on port 8888 or configure this application to listen on another port.
Disconnected from the target VM, address: '127.0.0.1:54879', transport: 'socket'
[ERROR] Command execution failed.
Command execution failed.

```

 
 
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200928120616508.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

 

# 原因分析：

 由于之前开启vue项目启动，再启动后端时会报错。
 

# 解决方案：
 

```powershell
netstat -aon|findstr "9000"
查看端口号运行进程
taskkill /pid   进程号  -f`

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200928121040878.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

 

--------------------------------------------------------------------------------

