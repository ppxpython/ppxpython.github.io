---
title: Jmeter 分享2
abbrlink: 26189
date: 2022-07-13 18:14:53
tags:
---
# JMETER分享

## 一、接口测试

**注：接口参数可从附件/接口参数中拷贝txt文件内容，然后在http请求参数选择从剪切板复制添加**

##### 1、断言

响应断言

1. 包括：响应内容包括需要匹配的内容即代表响应成功，支持正则表达式
2. 匹配： 响应内容需要完全匹配需要匹配的内容即代表响应成功，不区分大小写，支持正则表达式
3. 相等：响应内容要完全等于需要匹配的内容才代表成功，区分大小写，支持正则
4. 字符串：返回结果包含指定结果的字符串，但是Substring不支持正则
5. 否：不进行匹配

断言持续时间

	在限定的时间内得到响应数据，超时同样为失败

JSON断言

	![](https://pic.imgdb.cn/item/62df48edf54cd3f937a925da.png)

##### 2、用户参数

使用方法：前置处理器中添加，设置每次迭代更新一次，需要增加线程数才能起作用

作用：可以更新参数

![](https://pic.imgdb.cn/item/62df4974f54cd3f937ab71f6.png)

##### 3、函数助手

使用方法：在工具中添加

##### 4、Bean shell

使用方法：在前置处理器中添加

作用：支持JAVA语言定义变量

例子：

vars.put("user","zj")

在变量中${user}即可使用

##### 5、CSV数据文件设置

文件名：C:/Users/Desktop/user_name.txt

变量名：username

忽略首行：False

是否允许带引号：False

遇到文件结束符再次循环：如果循环一百次，只有四个文件就True

线程共享模式：看变量的生效区域

优先使用用户参数>CSV数据  如需禁用，右键用户参数>禁用

##### 6、命令行启动

```shell
jmeter -n -t D:\apache-jmeter-5.4.3\TestCase\数据库测试.jmx -l mt_test.jtl -e
```

-n 以非GUI形式启动（命令行）启动 -t 测试脚本 -l 生成的文件名称 -e执行完脚本后生成html报告 -o测试报告存放的位置(不加会默认生成到bin\report-output)

如果有jtl文件想生成html报告(**生成的html报告可能与聚合报告数据不一致，以聚合报告为准，再使用jtl报告生成html报告**)

```shell
jmeter -g test.jtl -o /path
# -g：后跟test.jtl文件所在的路径
# -o：后跟生成的HTML文件存放的路径
```

报告数据项说明

Request->Label:请求名称即采样器名称
Executions->#Samples：共请求多少次，请求的数量(线程数 * 循环次数)
Executions->KO：错误数量
Executions->Error%：错误率
Response Time（ms）：响应时间
	Average：平均响应时间
	Min：最小响应时间
	Max：最大响应时间
	90%Line：90%线，90%用户响应不超过该时间
	95%Line：95%线，95%用户响应不超过该时间
	99%Line：99%线，99%用户响应不超过该时间
	Throughput：吞吐量，一般情况下可看做每秒完成请求数(和QPS类似)
	**特别强调下90th pct：这里指的是百分之九十的用户都不超过多少ms，并不是多少指百分之九十的用户是多少ms**
Network（KB/sec）：网络情况
	Received：每秒从服务器端接收到的数据量
	Sent：每秒从客户端发送的请求的数量

## 二、分布式部署

适用：压力测试

前提条件：

1. 运行相同版本的JMeter
2. 使用相同的java版本
3. 有基于SSL的RMI的有效密钥库，或者禁用SSL。
4. 都在一个网络

控制机：我们操作的机器，用于启动和传递测试任务，一般不执行测试任务（为了性能考虑）

执行机：用于执行控制机分发的测试任务，并上传测试数据到控制机

以多个jmeter运行在单机为例

控制机：

![](https://pic.imgdb.cn/item/62df43eaf54cd3f93793b635.jpg)

执行机：

![](https://pic.imgdb.cn/item/62df441af54cd3f937947ae7.jpg)

控制机&执行机：

![](https://pic.imgdb.cn/item/62df49f1f54cd3f937adabe5.png)
启动顺序

1、先启动执行机下的jmeter-server.bat，等待出现连接成功

![](https://pic.imgdb.cn/item/62df4a12f54cd3f937ae37e6.png)

2、执行控制机下的jmeter.bat

![](https://pic.imgdb.cn/item/62df4a2ff54cd3f937aeae42.png)

注意：

	1、任务并不是分发，而是拷贝

	2、执行机下不需要有测试脚本

	3、如果有用到CSV数据，则执行机下的相同路径也需要有csv配置文件