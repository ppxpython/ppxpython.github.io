---
title: Jmeter 分享1
abbrlink: 26381
date: 2022-07-13 18:14:44
tags:
---
# Jmeter  分享

## 一、简介

Apache JMeter是Apache组织开发的基于Java的**压力测试**工具。用于对软件做压力测试，它最初被设计用于Web应用测试，但后来扩展到其他测试领域。 可以用于测试静态和动态资源，例如静态文件、CGI 脚本、Java 对象、数据库、FTP 服务器 等等。JMeter 可以用于对服务器、网络或对象模拟巨大的**负载，**来自不同压力类别下测试它们的强度和分析整体性能。

## 二、安装

* 由于Jmeter是基于java开发，首先需要下载安装JDK （目前JMeter只支持到Java 8，尚不支持 Java 9）,配置环境变量。

  (1)  新增变量：JMETER_HOME：D:\apache-jmeter-5.2.1

  (2)  在CLASSPATH变量的最前面加入如下变量：   %JMETER_HOME%\lib\ext\ApacheJMeter_core.jar;%JMETER_HOME%\lib\jorphan.jar;

  (3)  在PATH变量的最前面加入如下变量：%JMETER_HOME%\bin;

  (4)  进入D:\apache-jmeter-5.2.1\bin，双击jmeter.bat，或在dos窗口输入jmeter命令打开jmeter界面，安装成功。
* 官网下载地址：[http://jmeter.apache.org/download_jmeter.cgi](https://link.zhihu.com/?target=http%3A//jmeter.apache.org/download_jmeter.cgi)
* 下载完成后解压zip包


  ![](https://pic.imgdb.cn/item/62cea0dff54cd3f9371565fc.jpg)
* 启动JMeter，双击JMeter解压路径（apache-jmeter-3.3\bin）bin下面的jmeter.bat即可
* Jmeter是支持中文的，启动Jmeter 后， 点击Options -> Choose Language来选择语言

  ![](https://pic.imgdb.cn/item/62cea12ef54cd3f93715e7e8.jpg)

## 三、 jmeter使用

### 1.jmeter的主要元件

(1) **测试计划**：是使用 JMeter 进行测试的起点，它是其它 JMeter测试元件的容器

(2) **线程组**：代表一定数量的用户，它可以用来模拟用户并发发送请求。实际的请求内容在Sampler中定义，它被线程组包含。

(3) **配置元件**：维护Sampler需要的配置信息，并根据实际的需要修改请求的内容。

(4) **前置处理器**：负责在请求之前工作，常用来修改请求的设置

(5) **定时器**：负责定义请求之间的延迟间隔。

(6) **取样器(Sampler)**：是性能测试中向服务器发送请求，记录响应信息、响应时间的最小单元，如：HTTP Request Sampler、FTP Request Sample、TCP Request Sample、JDBC Request Sampler等，每一种不同类型的sampler 可以根据设置的参数向服务器发出不同类型的请求。

(7) **后置处理器**：负责在请求之后工作，常用获取返回的值。

(8)**断言**：用来判断请求响应的结果是否如用户所期望的。

(9) **监听器**：负责收集测试结果，同时确定结果显示的方式。

(10) **逻辑控制器**：可以自定义JMeter发送请求的行为逻辑，它与Sampler结合使用可以模拟复杂的请求序列。

### 2.常用操作

* **启动jemter后一般会默认生成一个测试计划，在测试计划下可以添加线程组，其中线程组有下面几种重要的参数。**

  * 线程数：虚拟用户数，用于并发测试。
  * Ramp-Up Period(in seconds)准备时长：设置的虚拟用户数需要多长时间全部启动。如果线程数为10，准备时长为2，那么需要2秒钟启动10个线程，也就是每秒钟启动5个线程。
  * 循环次数：每个线程发送请求的次数。如果线程数为10，循环次数为100，那么每个线程发送100次请求。总请求数为10*100=1000 。如果勾选了“永远”，那么所有线程会一直发送请求，一到选择停止运行脚本。
* **在线程组下添加测试的请求类型，例如http请求、TCP请求等，注意一些请求可能需要添加额外的插件才能实现（例如UDP）。下面以常用的http请求为例。**
* 协议：向目标服务器发送HTTP请求协议，可以是HTTP或HTTPS，默认为HTTP 。

  * 服务器名称或IP ：HTTP请求发送的目标服务器名称或IP 。
  * 端口号：目标服务器的端口号，默认值为80 。
  * 方法：发送HTTP请求的方法，可用方法包括GET、POST、HEAD、PUT、OPTIONS、TRACE、DELETE等。
  * 路径：目标URL路径（URL中去掉服务器地址、端口及参数后剩余部分）
  * Content encoding ：编码方式，默认为ISO-8859-1编码，这里配置为utf-8。

![](https://pic.imgdb.cn/item/62cea14cf54cd3f937161cdb.jpg)

##### 注：

POST和GET请求方法各有利弊，简单介绍一下POST和GET的请求方法的区别，POST是把参数放在body里面，而GET的是把请求的参数放在URL里面，这样传递参数的长度会受到限制。

## 四、实例演示

### 1.学生登录接口

#### 1.1接口的地址

https://mapi.ekwing.com/student/User/login

![](https://pic.imgdb.cn/item/62cea166f54cd3f9371644ad.jpg)

（1）协议：https   服务器名称：mapi.ekwing.com    端口号：空

（2）请求方法：GET　路径：/student/User/login　　内容编码：utf-8

注意：路径输入的时候，不能有空格。

（3）请求的参数

{"driverType": "HMA-AL00", "is_http": "1", "driverCode": "3.9.0", "osv": "10", "username": "13528263544", "client": "student", "v": "3.7.8", "password": "f379eaf3c831b04de153469d1bec345e", "os": "Android", "deviceToken": "F4%3A63%3A1F%3A1D%3A45%3AFE"}

（4）请求头参数

{"Accept-Language": "zh-Hans-CN;q=1", "Accept-Encoding": "utf-8", "Connection": "keep-alive", "Accept": "*/*", "User-Agent": "EKWStudent/3.8.8 (iPhone; iOS 13.2.3; Scale/2.00)", "Host": "mapi.ekwing.com", "Content-Type": "application/json"}

（5）点击运行

（6）察看结果树

![](https://pic.imgdb.cn/item/62cea17bf54cd3f93716650d.jpg)

### 2.获取作业列表的接口

地址：https://mapi.ekwing.com/student/Hw/getlist

![](https://pic.imgdb.cn/item/62cea190f54cd3f9371688a7.jpg)

（1）协议：https   服务器名称：mapi.ekwing.com    端口号：空

（2）请求方法：POST　路径：/student/Hw/getlist　内容编码：utf-8

注意：路径输入的时候，前面不能有空格。

（3）请求的参数

{"driverType": "HMA-AL00", "is_http": "1", "uid": "${uid}", "sortField": "publish_times", "driverCode": "3.9.0", "sortMethod": "desc", "osv": "10", "token": "${token}", "client": "student", "v": "3.7", "author_id": "${uid}", "os": "Android", "method": "unfinish", "deviceToken": "F4%3A63%3A1F%3A1D%3A45%3AFE", "page": "1"}

（4）请求头参数

{"Accept-Language": "zh-Hans-CN;q=1", "Accept-Encoding": "utf-8", "Connection": "keep-alive", "Accept": "*/*", "User-Agent": "EKWStudent/3.8.8 (iPhone; iOS 13.2.3; Scale/2.00)", "Host": "mapi.ekwing.com", "Content-Type": "application/json"}

（5）点击运行

（6）察看结果树

![](https://pic.imgdb.cn/item/62cea1aaf54cd3f93716b0f6.jpg)

因为获取作业列表接口的一些请求参数值是登录接口的返回参数值，也就是说获取作业列表接口和登录接口存在依赖的关系，下面重点了解一下如何使用Jmeter做多个接口的测试。

## 五、访问多个接口

### 1、什么是接口参数依赖

接口参数依赖又称作接口依赖，简单点说就是后面的接口要用到前面的接口产生的数据。

比如：我们一个接口B需要A接口返回的参数token作为自己的请求参数。常见的场景如：访问一个需要登录才能浏览的接口。

下面以获取作业列表的接口需要依赖登录接口为例，进行介绍。

### 2.json提取器的使用

利用Jmeter进行接口参数依赖的测试，主要有两种方式，第一种利用正则表达式，第二种是JSON提取器，本次先介绍JSON提取器解决接口参数之间的依赖的方法。

（1）创建Json提取器

http请求-->右击-->添加-->后置处理器-->JSON提取器

![](https://pic.imgdb.cn/item/62cea1bdf54cd3f93716cef7.jpg)

（2）填写参数值

![](https://pic.imgdb.cn/item/62cea1e0f54cd3f937170564.jpg)

![](https://pic.imgdb.cn/item/62cea1e9f54cd3f937171280.jpg)

需要填写数据的字段是Names of created variables、JSON Path expressins、Match No.(0 for Random )

Names of created variables指的是登录接口中的参数名，如token，uid

JSON Path expressins 是对登录接口的参数token和uid进行提取，格式为$.data.token,$.data.uid

Match No.(0 for Random )是指匹配数字（0代表随机，1代表第一个，-1代表所有），可为空即默认第一个

（3）保存

### ３.学生的登录接口和获取作业列表接口之间的依赖关系

(1) 首先，如上述介绍成功访问了学生的登录接口，获得token值。

(2) 使用Jmeter工具中的json提取器，提取登录接口的token值，uid值，author_id值作为获取作业列表的接口的参数。

在第二个接口的察看结果树中的请求的Request Body能够看到token、uid、author_id值和登录接口的响应数据中的Body值是一样的，就说明提取成功了，然后在获取作业列表接口的token、uid、author_id的参数后加上值，格式分别是${token},${uid},${author_id}

![](https://pic.imgdb.cn/item/62cea190f54cd3f9371688a7.jpg)

(3) 点击运行

(4)察看结果树

响应数据中的Response Body中stasus值为0，代表获取作业列表接口请求成功了。

![](https://pic.imgdb.cn/item/62cf78acf54cd3f9370f03d0.jpg)

补充：这里将两个接口都放在一个线程组下，更为操作简单，也可以将两个接口都放在两个线程组下，操作起来相对复杂。



