---
title: mysql安装教程
abbrlink: 28265
date: 2022-01-06 10:16:34
tags:
categories:
  - [电脑,软件配置,安装教程]
---
mysql安装教程

### **正文：**

现在作为服务器操作系统的一般有三种，Windows Server，Linux，Unix，在这里我们只介绍在windows下和linux下安装mysql，Unix下安装应该和linux差不多。

### **Windows下安装MySQL：**

1. 在浏览器中打开[https://www.mysql.com/](https://www.mysql.com/)，进入MySQL的官方网站，国内的网打开可能有点儿慢，稍微等待一下
2. 在打开的网页中选择downloads标签，如下图：

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MjQxNmE3YWRjMDIyYTJmNTY4ZjYyNDUzODZlZjA1YmJfblBwb2NKREtrNDNZNkR5V2ZXZ0dUdVN5M2dweWJOdktfVG9rZW46Ym94Y25WbHZOdFpUOE1hOE43blRFS2VQaVpPXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

3. 在打开的标签页中，滑到页面的最下面，可以看到MySQL Community Edition  [Community (GPL) Downloads »](http://dev.mysql.com/downloads/)  的字样，点击[Community (GPL) Downloads »](http://dev.mysql.com/downloads/)，如下图：

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MTk0YmI0NzRjNzk0OTA0ZjM4Mzk2NjY0YzZmMjhhZTFfYXVEUUp5ck40UWdTa0FkWFdoUXJ1SEZKeVRrekl5ZTlfVG9rZW46Ym94Y25rYVI2Z2VSVmNFZERUZUR1a0hDMXNmXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

4. 在之后打开的页面中，点击[MySQL Community Server](http://dev.mysql.com/downloads/mysql/) (GPL)，如下图：

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDc4ZTM2MTExNjdiMTI1OTY4NGJhMjJlYzYzMWI0NWNfTVZ6R0w4REdPc3JzVFJaWmIzNWZiZVRSUDVleWpZNmlfVG9rZW46Ym94Y242eDNGZnd1MWc5UUNHU2dIbTVmbDdjXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

5. 在之后打开的页面中就可以看到相关的下载项了，如下图：

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDI0ZjAwYjBmOTUyOTg5ODE3NjU5ZDMwZGZiODI2ZjZfZ0FwT2YyRkZ5UVJ1SUlJUFRJenAyMVZMQ1lNUzlaczVfVG9rZW46Ym94Y25kVVZNQ1VmMjYxeHVBTm85VlRuMlBjXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

在图中第一个红色框标注的地方就是选择操作系统，这里我们选择Microsoft Windows，可以看到第二个红色框是Recommended download，这里就要区分了，如果是新手建议点击这个，因为这个版本的MySQL不用自己配置，就是普通的安装文件，直接一路next就安装完了，如果想深入学习，那么点击Other downloads内容区的下载，可以看到前两个是正式版，后两个是debug版，一般选择前两个，根据自己的机器32位还是64位选择下载，下载下来是个zip文件，安装的自己配置，相对复杂

6. 如果选择了MySQL Installer进去页面之后，如下：

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjMwM2I3ZjczMjkzYWRkM2FmYWQ5N2IyZDM5MWM1MDhfVHg5N1RiSVRxTjFnTHM1eDFCTTBsRDlkck9XSjJJeWhfVG9rZW46Ym94Y24zYWtobzhtNVg1MWU4NFZoYWowUVBoXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

选择第二个下载项进行下载，这里不管是新手还是老手，都会要求先登录再下载，如果没有账号可以注册一个，因为现在MySQL归Oracle所有了，不得不遵循这个规矩

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=M2ZmNjVlYmVjMmFiNDhhYzRhODJlMjM4MWFlMjgwMjdfS3pUUmNZMFNHa0MwNnRoUGltVzM5eEI2MlppZmxCWGhfVG9rZW46Ym94Y25EcDJTREg4VnRuZm9VMkxqY2VFbkFnXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

#### **为防止有的同学无法下载，这里贴出下载链接：**

MySQL Installer 5.7 ：[http://cdn.mysql.com//Downloads/MySQLInstaller/mysql-installer-community-5.7.16.0.msi](http://cdn.mysql.com//Downloads/MySQLInstaller/mysql-installer-community-5.7.16.0.msi)

MySQL 5.7 Windows (x86, 32-bit), ZIP Archive ：[http://cdn.mysql.com//Downloads/MySQL-5.7/mysql-5.7.16-win32.zip](http://cdn.mysql.com//Downloads/MySQL-5.7/mysql-5.7.16-win32.zip)

MySQL 5.7 Windows (x86, 64-bit), ZIP Archive ：[http://cdn.mysql.com//Downloads/MySQL-5.7/mysql-5.7.16-winx64.zip](http://cdn.mysql.com//Downloads/MySQL-5.7/mysql-5.7.16-winx64.zip)

MySQL Installer 只有32位的，没有64位的

### **如果下载的是mysql installer，请看这里：**

1. 双击安装文件，可能会出现下面的画面：

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=OTIwM2ZiYjA1MWFlNGVlMDQzMDE1MzI5ZmYxNmM2MjVfMEVrek9qbEdFMU5MTlNEME9nUVUySzVKaEx3Q1dURkpfVG9rZW46Ym94Y245d25uRUlRR2tldE5QaDJuZFlEekhnXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

意思就是MySQL需要.NET Framework4.0才能继续安装，那我们就安装一下

2. 用浏览器打开[http://www.microsoft.com/zh-cn/download/details.aspx?id=17718](http://www.microsoft.com/zh-cn/download/details.aspx?id=17718)，点击下载，就可以很顺利的下载下来了，下载完直接安装

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=N2EwMjU3Y2Q2ZGEwMDcwODIxYTk0ODZiMDQwY2ZjYTZfRElTc1dtb094ZXVOalI3NVhMMEViemx5cVRWQmptcGVfVG9rZW46Ym94Y243elRjZ2Q3M1VCUVJldHZYMWxUNk81XzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ODI5YjczZDM5OGFiMzMxZTI3NmFmNjg2YTI1ZjQxMmRfSVJ0amF1ZTh4aUtPeW82ZjBBSUJ3YVRGSXBSTTFiWWdfVG9rZW46Ym94Y25nVTlCNkJNa1BrMVRmQW9iVTBpM3ZCXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

3. 点击完成，然后再双击MySQL安装文件，这次就能正常安装了~

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjkxZmFiOWNjOTNkMjFiOWI4ZTE4NTYyN2I1Y2RiZDRfaHAxUHNtVnZjY21LZDJtdDhvaGJIaUYzSFhJUEFvbm9fVG9rZW46Ym94Y25qNWRtUWhabmFkTFBUcTZ0N01UWjFiXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

4. 接下来就是一些说明协议啥的

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NjhmZTA2MDMwNTY2ZTFmYmE1MTMwN2UxZjEwODk1YzlfYjR0eW9DbndLRUZtUzZPa2owMTFDQXlGeGJyclBtbDZfVG9rZW46Ym94Y25xMXlOcEhZRHYxT0FrM0RxWGhjSW1kXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

5. 同意协议，打钩之后，点击next，然后出现，选择安装选项的界面，一般选择第一个就行，这个选项包含了一些MySQL其它组件，像MySQL Workbench，MySQL for Excel等等，如果只安装MySQL数据库，选择第二项Server only就行，这里我选择了第一项

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MWM3YmI0MTgzOTdlNjM0NjJmY2Y5MjhkOTA2Y2RkNDJfajByVnJNaGtRTExncDhYNWxrdnFyaDFIY0VWdDdpVFVfVG9rZW46Ym94Y25HVkwycEJSREVqM29WeGJZRTVpWVNnXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

6. 点击next出现检查必需项，如果电脑安装了VC2013运行库，Excel，VisualStudio前三项就会自动打上勾，因为我是虚拟机演示的，所以没有装这些，点击next的时候会出现警告框，不去管它，直接点击是跳过

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=OTdlNzhhZGNlZTM3YTYxNTEyZjNjZmNmOTgyNjRmMDdfN2ZmZlZaQTRTUEVKUk5wTGpjOEdnVkFrSGw3cldVcjBfVG9rZW46Ym94Y25ValNrbGNaWkxrdmg4UEMwanRPd1NiXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NWM0ODBkZGFhMTk3MmQ1ODVhMzk3MDJkNWZhYTYzZTBfNHRhVUJsdVhwbTJBUTJqbzRYMVJrVms1ejVGQk95ZDZfVG9rZW46Ym94Y251bmRKU1lIaWZpS25nNnAzMENpVDJlXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

7. 然后出现即将要安装的软件和插件

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjAzMjYzY2I3ZjNhYzlmMDkyNzEwZTZkNjM5ZGRhZWNfZUdpY0c2OXk2YjMyeVdWV1k2YmFoWmk2RHZ4YTNqek9fVG9rZW46Ym94Y25pZzZrZlk0N1NlajVmOG1uME5peHVBXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

8. 点击execute开始执行安装，等全部安装完之后，点击next，图中第三项表示安装失败，不去管它，是一个odbc数据源，我们一般不用这个

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YzVkMmQzZTM3NzYwMmExYjE3NWIxMGUyNDJlYWM1NzJfYXJKQlU5eGVKaFdZajBDcXV2M1VhMjE3Ylg3R0dzUXBfVG9rZW46Ym94Y25SUDBkcWZCTmREOWRPaFAwUHZpeEVmXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

9. 之后出现配置界面

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NWQxNjVhMWY3OTcxOTE0MGJlNmVjNjZhY2QyZWEzOWFfSVZCSGZmaUR5UkdVUFhkMkNzT0xqWHJjZ2xGMFRwMzhfVG9rZW46Ym94Y25TckVNR0VXbTFDMkg3SHZ6dmhHbmZnXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

10. 点击next之后开始配置，第一个配置的是mysql的运行模式和网络，其中Config Type表示运行模式，如果安装mysql是做开发用，就直接选择第一个默认的就行，第二个Server Machine表示运行模式为服务器模式，这些模式的不同会导致MySQL占用系统资源的不同，第二个配置的是网络相关，表示链接MySQL的时候使用TCP/IP协议，并指定端口号为3306，这些如果没有特殊要求就不要去改

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NmRiODYzMTQxYjUxNzFjZWFlMzIzMDc2MGMwNWE3ZmRfVzAybXZ4MDJtNTlESUY1TjNMS2g1ZnhNc1FPc3lCUHZfVG9rZW46Ym94Y25PMHVCYmhiNVM5RllrS0tpSUtCMXRkXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

11. 配置完成之后点击next，需要填写MySQL中root用户的密码，长度最低为4位，第二栏中还可以添加普通用户，一般开发用不用再建立用户了，直接使用root就可以，所以我们填完密码之后点击next

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NjkxNmZiZTllM2Q2NmJkZmJiZjUyNTBmOTE2ZWI4MmFfdnFJS2dLWTU5ZVpNWXlmY1JrMzZ2V3lacUNldHYzd1dfVG9rZW46Ym94Y24wS2RmUW5ZVEg1eFN1S2oxcGRWeVRrXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

12. 以下图片中需要配置的是MySQL的运行方式，第一个单选框表示是否将MySQL服务作为一个windows服务来运行，windows server name表示MySQL服务在windows server中的名称，第二个单选框表示是否在系统启动时自动启动MySQL，

第三个单选框表示MySQL服务以哪个账户运行，这一页的基本别动，直接next

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NzEzMDJhZGUzMWM5OWI3MWE5MTBhMjc0ZDNlZGUyNzFfb1JzVlZ1NGRnbWI5cmpZb29RQUUxTGZRWko5TzN0UkhfVG9rZW46Ym94Y241RFhQSk5MWUY0V0FmRDlwaU96N2plXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

13. 下面这个是关于MySQL的插件和扩展，直接next

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MzFjZmQ4NDU0Zjg5NjhkZTIyMzRmNTdhNWUzMGFjYTlfSHBXM0x6NWU4SExUUk5UN094ZzBpa1p5czJMc1paQURfVG9rZW46Ym94Y25PcFdKd3NpMUJKWVBTcDF5Y0NmYUFiXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

14. 然后出现下面的界面，直接点击execute

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTRlMTVjMDUyYzRhMzA3YTZjZjI0ZjA0Njk0MjE3OTRfYnRieDdSOTRoVDhiSXZIRVdZdVlpRG15c280U0Q2Z3lfVG9rZW46Ym94Y251SWsyQVkyRU5iT0ZNZTlkODdsMURoXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

15. 配置完之后点击finish

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZWE4OWY3MzA0ZWFjOGNhNWMxMThhYmI4MWQ1NzNhZjNfT1hqNWowcTBSQ1daZXVZMWY5YnlkVjZHTWozYVJKSG5fVG9rZW46Ym94Y24xR3V4U1dGT3pZYXhTOTFwWEJXcjlNXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

16. 然后再配置MySQL的实例，点击下图中的next

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDM1NzViN2Y0OGIyZjgyMTI4NTI4YzUwMGRmMTdiYTVfMEFkRExvVU5ldXlMMVVlOURqdFR4MGRuMVZlQ3gxOTVfVG9rZW46Ym94Y25mVE9xdUM1MTdCTFYydUJwa29CRnJkXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

17. 之后点击下图中的check，然后点击next

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=OWQzMTQ5N2JjZTcwMTMyMGJiZmVlYzE2Yjk5YmIzNWJfMUl5VjJYUTdaQTZJVXB3RzFJaTdaNFgwck9iS0NyanRfVG9rZW46Ym94Y25MSXh3MDlvTVlhdU5BWWFJNmZmbjRnXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

18. 点击下图中的execute

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MTNhM2Y2MzA1ZDUzMzcxOTAxNzFkZTgwNjlkOTIwOTlfNXpsUFpqTHNRdW9lQlFyUHJ2a2tOcE9MU1JFem9FTFVfVG9rZW46Ym94Y25rR0l2TlRLRjAwWHA2NTlmVWNhREJkXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

19. 执行完毕之后点击finish，又回到了主程序，然后点击next

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=N2UyMzM1ZmFiMzhlZTYwMzZmNDc1NzE1ZDg1YzA5MThfYWxWSTIzelRFWW0yVHhnZHN4T0VWYlY5ejlzQWJzMHRfVG9rZW46Ym94Y25CM3JxN29XbmdhVEhmZkY2cjFQUnpmXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

20. 然后点击下图中的finish

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=OGYzZGQ1MDhkNjYyYjM4ZDgwYThhODU5MGQyMzI3OTZfaXZYY2JqT2FvR0RjRmFZOGU2SXZSV3VRdENYVTFhMEtfVG9rZW46Ym94Y25ScmFkTGxWeXBzQVlGakIzbXp4R0pMXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

finally，配置完了~~~我们开始验证一下，在开始菜单找到 MySQL 5.7 Command Line Client打开，之后提示输入密码，输入刚开始安装的时候你配置的密码，出现下图表示你安装成功了

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjNiMTdlM2E2NzIzMWYyMGUyNWEzZTU4NzViNTlmZGJfZzNiUERHVTA2aFVxYW1NaEsyNGZ4VWhHWXR2cG5wcjJfVG9rZW46Ym94Y25ZTWlsS09HS2VEZ2Z2RFZvbUQ3bEY1XzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ODNjMWM1MjkzMTgyMmEzMWIyMWY1ZDdhZTFkZmIwYzlfS0ZkYU1wOTBtMkRKOEpkeUpTWm1JaHpCcjc4bXNSQ0xfVG9rZW46Ym94Y244S0l4aUsyd3ZORTlwOU9QUXV1TmdnXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=N2E5MzkyOTA4ZTQxMWNjNDNkZjU4ZmU3NjE4NDgzM2RfT2x0ZWc3NTNxUmZBTnlkQWxjaTBBQ1JPaG0zRGZlV1VfVG9rZW46Ym94Y25UamdFbHIxeUF4THFTZkQ3YXoxNFNlXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

### **下载zip安装包的看这里：**

1. 首先解压你下载的安装包，得到一个名为mysql…的文件夹

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MGIzMzA3NGRmNWQ2YTI1NzgyZmVkNTBhMjI0ZDEyY2VfMmlvbmZtV3NoRWxweGg0RlpKTmJQNFZHRDFLajZ4Y21fVG9rZW46Ym94Y25sMGpNemw3N2Y3eFlBRTk0NXdhNlJmXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

2. 把这个文件夹移动到你想安装mysql的地方，也就是你移动到的目录就是安装mysql的目录，比如我的放在C:\Program Files下面
3. 打开我的电脑->属性->高级->环境变量，在系统变量里选择PATH,在其后面添加: 你的mysql bin文件夹的路径 (如: C:\Program Files\mysql-5.7.16-winx64\bin )，注意是追加,不是覆盖 ，然后确定

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NzBhOWU5Yjg0Njg3MjM2Nzg4OThiMjYzODAyYWRjOTBfanVXbDk4MmYxNmJIS0I1RUZ4MkdRTHFVanlFc2V1dVNfVG9rZW46Ym94Y24yRGxyZk1DS0JKQjR5NU5Wd2VpQVBaXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

4. 在mysql目录中新建文件夹data，还需要修改一下配置文件，mysql默认的配置文件是mysql目录中的my-default.ini，比如我的是C:\Program Files\mysql-5.7.16-winx64\my-default.ini

用记事本打开在其中修改或添加配置，之后保存关闭

[mysqld]

basedir= C:\Program Files\mysql-5.7.16-winx64（mysql所在目录）

datadir= C:\Program Files\mysql-5.7.16-winx64\data（mysql所在目录\data）

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YThhZTZiMmEwMzBiZWMyY2E1MThmY2UxZmY3MmU0NTlfNnFJbW43WUVqbXB1Z0c1OXNMOUdaVjJkWWZiN1pvRm1fVG9rZW46Ym94Y25QRXhmcVF5bXBiQ0NjUERmN1JvT3FiXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

5. 以管理员身份运行cmd（一定要用管理员身份运行，不然权限不够），输入命令 cd C:\Program Files\mysql-5.7.16-winx64\bin  回车

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZmRkYTY4NjliZWFiZjhlY2MwYTM4YjI1MTkwNDVlODFfdzkwMlJuWEhHa2xNUm1Eald2ZEFyS3VkQkEyQlR5U0pfVG9rZW46Ym94Y25pdW1hbEY4ZmdiWm91V2xGd2N1ZkFoXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

6. 然后再输入mysqld --initialize-insecure --user=mysql 回车

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MTE0NjhkZTRjY2FhMzZmNzVhMThjMDM5NGQ3MDZjNjZfb3hKdDluV2ZNelAwRHExUlgzWDJNcVMwTWNHdERyUlJfVG9rZW46Ym94Y24yenhWZHVyek5JdVpwMGlLRTg3dktkXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

7. 之后再输入 mysqld install 回车

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NGU1ZTFmZmMxMmUzZTYwNTQyYjNiZTI0ODkxNTk5MDJfWmV6TkNobFJvZXRDSkhaRzNLTEFlY0dJdlg1MzVlSG1fVG9rZW46Ym94Y24yeE1YdGVybjJ1aDNibDNWdnVKR1ZDXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

8. 输入net start mysql 回车启动mysql服务

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MGMxZGY4ZDE2YjRjZTczZTBmNjMxZDA4MDZjNGM2NTFfamRTbHQ0bjFtck8zYkkzbDF3NFVMN1JicUxLMEllZEZfVG9rZW46Ym94Y25JT3hJejBES0tqYlZaRWEwbDI2Z09iXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

9. 从上图看到mysql服务已经启动了，我们输入mysql -u root -p 回车登录mysql数据库

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=OWNhNDVjYjg1N2QwZDVkN2RmOTNhYzkzN2NmYjhkNDFfRmllSWd4OE10T3ZRZnhrSUV4bnQzazBIQzEwOWJVQWJfVG9rZW46Ym94Y240TjZodzgycTlzVEtURzVKaTBvYjNjXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

10. 要求输入密码，刚刚安装完是没有密码的，直接回车

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjQzOGJlYTQwYWZmNGQ4MTJmMDU0NGNkYzE3NDE5NWRfb2RaWXlIaGpQODZYb2szYlJrdVpOVDZDZkNLWlBSODFfVG9rZW46Ym94Y256bzNidW1pU0NyVkNiQTZrVkRPdHBjXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

看到已经进入了mysql，我们输入show databases; 回车可以看到数据库已经显示出来了，这个是不是比安装版的更简单

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MzJiYTg1NGFjZGZmYzRhMzI3OWE5YzE2Njg4NWMwNjhfb0t1T1BVWDFSVUltd2I4RjRYR3VoekVsNHJrVGVqREhfVG9rZW46Ym94Y25jcGxmVUpIWExjWVhSa3JuYmpEOGFlXzE2NDE0MzU0MDY6MTY0MTQzOTAwNl9WNA)

### **Linux下安装mysql：**

这个请看其他人写好的：[http://jingyan.baidu.com/article/fec7a1e5f8d3201190b4e782.html](http://jingyan.baidu.com/article/fec7a1e5f8d3201190b4e782.html)

> [http://www.cnblogs.com/shenliang123/p/3203546.html](http://www.cnblogs.com/shenliang123/p/3203546.html)
