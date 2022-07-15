---
title: 01postman学习
tags: Postman
categories:
  - - 软件测试
    - 软件测试工具学习
    - 接口测试工具
    - Postman
abbrlink: 12511
date: 2020-10-20 09:00:40
sticky: true
---
# 系列文章目录
 
@[TOC](文章目录) 
# 前言


 本文为视频学习的截图记录，
 用途：以方便以后学习翻阅
 主要以图片的形式展现
这里附上视频链接：[postman学习](https://www.bilibili.com/video/BV1Gt4y1D7co?p=5)


# 一、postman是什么？
postman是一个HTTP客户端，用于发送请求和接收响应，是专门用于测试API的工具

# 二、 接口是什么？
IT 行业从 WWW 万维网时代 的 C/S、B/S 架构，到移动互联网时代的大前端时代，发展到云计算时代以 IaaS（基础架构即服务），PaaS（平台即服务），SaaS（软件即服务）为代表的云端架构，如今更是进入到万物互联的物联网时代，网络连接着我们生活的方方面面，而承载这些连接的连接点，就是网络接口，接口是不同网络应用之间联系、交互、相互作用的入口和桥梁。

如下图，是接口在软件系统中所处位置的示意图： 
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102009213540.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

# 三、 接口测试和接口测试的目的
## 1.什么是接口测试
百度百科中：

> 接口测试是测试系统组件间接口的一种测试。接口测试主要用于检测外部系统与系统之间以及内部各个子系统之间的交互点。测试的重点是要检查数据的交换，传递和控制管理过程，以及系统间的相互逻辑依赖关系等。


![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110441401.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110449981.png#pic_center)

 接口测试是测试系统组件间接口的一种测试，
 主要用于测试系统与外部其他系统之间的接口，
 以及系统内部各个子模块之间的接口。
## 2.为什么要进行接口测试

 1. 现在很多系统前后端架构是分离的，因为不同端（前段，后端）的工作进度不一样，所以我们要针对最开始出来的接口，以及需要调用其他公司的（银行，支付宝，微信，qq等）一些接口进行接口测试及验证数据，从安全层面来说，只依赖前端进行限制已经完全不能满足系统的安全要求（绕过前端太容易了）， 需要后端同样进行控制，在这种情况下就需要从接口层面进行验证。在这种情况下就需要从接口层面进行验证。前后端传输、日志打印等信息是否加密传输也是需要验证的，特别是涉及到用户的隐私信息，如身份证，银行卡等。
 2.  如今系统越来越复杂，传统的靠前端测试已经大大降低了效率，而且现在我们都推崇测试前移也叫 测试左移，希望测试能更早的介入测试，那接口测试就是一种及早介入的方式。例如传统测试，你是不是得等前后端都完成你才能进行测试，才能进行自动化代码编写。 而如果是接口测试，只需要前后端定义好接口，那这时自动化就可以介入编写接口 自动化测试代码，手工测试只需要后端代码完成就可以介入测试后端逻辑而不用等待前端工作完成。
 3.  简单概括：
 ①.越底层发现bug，它的修复成本是越低的。
 ②.前端随便变，接口测好了，后端不用变，前后端是两拨人开发的。
 ③.检查系统的安全性、稳定性，前端传参不可信，比如京东购物，前端价格不可能传入-1元，但是通过接口可以传入-1元。
 ④.如今的系统复杂度不断上升，传统的测试方法成本急剧增加且测试效率大幅下降，接口测试可以提供这种情况下的解决方案。
 ⑤. 接口测试相对容易实现自动化持续集成，且相对UI自动化也比较稳定，可以减少人工回归测试人力成本与时间，缩短测试周期，支持后端快速发版需求。接口持续集成是为什么能低成本高收益的根源。
 ⑥.   现在很多系统前后端架构是分离的，从安全层面来说：
 (1)、只依赖前端进行限制已经完全不能满足系统的安全要求（绕过前面实在太容易）， 需要后端同样进行控制，在这种情况下就需要从接口层面进行验证。
 (2)、前后端传输、日志打印等信息是否加密传输也是需要验证的，特别是涉及到用户的隐私信息，如身份证，银行卡等。
## 3.接口测试重点
 测试的重点是
 

 1.  检查接口参数传递的正确性
 2. 检查 接口功能实现的正确性
 3. 检查输出结果的正确性
 4. 检查各种异常情况的容错处理的完整性和合理性

 保证系统的正确和稳定为核心，重要性主要体现为以下几个方面：
（1）能够提早发现 bug，符合质量控制前移的理念。
（2）接口测试低成本高效益，因为接口测试可以自动化并且是持续集成的。
（3）接口测试从用户的角度对系统接口进行全面检测。实际项目中，接口测试会覆盖一定程度的业务逻辑


## 4.接口测试分类
针对软件接口的分类一般有如下几种情况：

 1. 系统与系统之间的调用
 如微信向用户提供统一的对外接口，程序员调用接口完成基于微信的小程序等；
 2. 同一系统内部上层服务对下层服务的调用
 如一个软件程序一般分为表示层，业务层和数据层，表示层调用业务层的接口来完成自己的工作，而业务层又会调用数据层的接口来实现相应的业务等。

 
# 四、postman进行接口测试

## 1.HTTP知识
HTTP是超文本传输协议，其定义了客户端与服务器端之间文本传输的规范。HTTP默认使用80端口，这个端口指的是服务端的端口，而客户端使用的端口是动态分配的。当我们没有指定端口访问时，浏览器会默认帮我们添加80端口。 需要注意的是，现在大多数访问都使用了HTTPS协议，而HTTPS的默认端口为443，如果使用80端口访问HTTPS协议的服务器可能会被拒绝。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020100309267.png#pic_center)
 HTTP 请求/响应的步骤：
客户端连接到Web服务器->发送Http请求->服务器接受请求并返回HTTP响应->释放连接TCP连接->客户端浏览器解析HTML内容

1、客户端连接到Web服务器
一个HTTP客户端，通常是浏览器，与Web服务器的HTTP端口（默认为80）建立一个TCP套接字连接。例如，http://www.baidu.com

2、发送HTTP请求
通过TCP套接字，客户端向Web服务器发送一个文本的请求报文，一个请求报文由请求行、请求头部、空行和请求数据4部分组成。

3、服务器接受请求并返回HTTP响应
Web服务器解析请求，定位请求资源。服务器将资源复本写到TCP套接字，由客户端读取。一个响应由状态行、响应头部、空行和响应数据4部分组成。
4、释放连接TCP连接
若connection 模式为close，则服务器主动关闭TCP连接，客户端被动关闭连接，释放TCP连接;若connection 模式为keepalive，则该连接会保持一段时间，在该时间内可以继续接收请求;

5、客户端浏览器解析HTML内容
客户端浏览器首先解析状态行，查看表明请求是否成功的状态代码。然后解析每一个响应头，响应头告知以下为若干字节的HTML文档和文档的字符集。客户端浏览器读取响应数据HTML，根据HTML的语法对其进行格式化，并在浏览器窗口中显示。

GET和POST请求：

如果是get请求的话，直接在浏览器里输入就行了，只要在浏览器里面直接能请求到的，都是get请求，如果是post的请求的话，就不行了，就得借助工具来发送。

**GET请求和POST请求的区别：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020101214841.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


1、GET使用URL或Cookie传参。而POST将数据放在BODY中。

2、GET的URL会有长度上的限制，则POST的数据则可以非常大。

3、POST比GET安全，因为数据在地址栏上不可见。

4、一般get请求用来获取数据，Post请求用来发送数据。

2)、http状态码


每发出一个http请求之后，都会有一个响应，http本身会有一个状态码，来标示这个请求是否成功，常见的状态码有以下几种：

1、200 2开头的都表示这个请求发送成功，最常见的就是200，就代表这个请求是ok的，服务器也返回了。

2、300 3开头的代表重定向，最常见的是302，把这个请求重定向到别的地方了，

3、400 400代表客户端发送的请求有语法错误，401代表访问的页面没有授权，403表示没有权限访问这个页面，404代表没有这个页面

4、500 5开头的代表服务器有异常，500代表服务器内部异常，504代表服务器端超时，没返回结果


常见的几种状态码：
 **200：** OK  当您的操作将在响应正文中返回数据时，出现此结果。
**201：** 资源成功创建和更新
**204：**  No Content 当您的操作成功，但不在响应正文中返回数据时，出现此结果。
**301：** 表示要从这个接口重定向到另外的接口（出现较多）
**304：** Not Modified（重定向）  当测试实体自上次检索以来是否被修改时，出现此结果。
**400：** 本来api必须要的参数但没有提供时，会出现 
**401：**  需要登录才能访问的接口，未登录时会报401
**404：**  Not Found（客户端错误） 当资源不存在时，出现此结果。
**405：** Method Not Allowed（客户端错误）由于方法和资源组合不正确而出现此错误。 例如，您不能对一个实体集合使用 DELETE 或 PATCH。
**412**： Precondition Failed  客户端错误
**413**： Payload Too Large（客户端错误） 当请求长度过长时，出现此结果。
**501**： Not Implemented（服务器错误） 当未实施某个请求的操作时，出现此结果。
**503**： Service Unavailable（服务器错误） 当 Web API 服务不可用时，出现此结果。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020094557254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020094821722.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020094845761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020094902209.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020094932863.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102009502419.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095200705.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095230334.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

## 2.增加断言

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095453408.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
一般断言时在http响应体中断言处理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095519944.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095532646.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

## 3.编写一个测试实例
测试目标url：
 [测试目标url](https://www.v2ex.com/api/topics/hot.json)
1.输入网址：
2.增加判断状态码和数据是否是10条的断言
代码：

```java
pm.test("状态码为200", function () {
    pm.response.to.have.status(200);
});
pm.test("返回的数据为10", function () {
    var jsonData = pm.response.json();
    jsonData.length === 10
    
});

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095752241.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
返回的结果：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095815452.png#pic_center)

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020095826275.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 4.sandbox
postman学习文档：https://learning.postman.com/docs/getting-started/introduction/
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020100106735.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 5.请求方法
HTTP/1.1协议中共定义了八种方法（有时也叫“动作”），来表明Request-URL指定的资源不同的操作方式
HTTP1.0定义了三种请求方法： GET, POST 和 HEAD方法。
HTTP1.1新增了五种请求方法：OPTIONS, PUT, DELETE, TRACE 和 CONNECT 方法
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010041557.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
1、OPTIONS
返回服务器针对特定资源所支持的HTTP请求方法，也可以利用向web服务器发送‘*’的请求来测试服务器的功能性
2、HEAD
向服务器索与GET请求相一致的响应，只不过响应体将不会被返回。这一方法可以再不必传输整个响应内容的情况下，就可以获取包含在响应小消息头中的元信息。
3、GET
向特定的资源发出请求。注意：GET方法不应当被用于产生“副作用”的操作中，例如在Web Application中，其中一个原因是GET可能会被网络蜘蛛等随意访问。Loadrunner中对应get请求函数：web_link和web_url
4、POST
向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST请求可能会导致新的资源的建立和/或已有资源的修改。 Loadrunner中对应POST请求函数：web_submit_data,web_submit_form
5、PUT
向指定资源位置上传其最新内容
6、DELETE
请求服务器删除Request-URL所标识的资源
7、TRACE
回显服务器收到的请求，主要用于测试或诊断
8、CONNECT
HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。
注意：
1）方法名称是区分大小写的，当某个请求所针对的资源不支持对应的请求方法的时候，服务器应当返回状态码405（Mothod Not Allowed）；当服务器不认识或者不支持对应的请求方法时，应返回状态码501（Not Implemented）。
2）HTTP服务器至少应该实现GET和HEAD/POST方法，其他方法都是可选的，此外除上述方法，特定的HTTP服务器支持扩展自定义的方法。


## 6.cookie
 Cookie的诞生

由于HTTP协议是无状态的，而服务器端的业务必须是要有状态的。Cookie诞生的最初目的是为了存储web中的状态信息，以方便服务器端使用。比如判断用户是否是第一次访问网站。目前最新的规范是RFC 6265，它是一个由浏览器服务器共同协作实现的规范。
Cookie的处理分为：

 1. 服务器像客户端发送cookie
 2. 浏览器将cookie保存
 3. 之后每次http请求浏览器都会将cookie发送给服务器端
 4. 服务器端的发送与解析
 5. 发送cookie

服务器端像客户端发送Cookie是通过HTTP响应报文实现的，在Set-Cookie中设置需要像客户端发送的cookie，cookie格式如下：

**Set-Cookie:** "name=value;domain=.domain.com;path=/;expires=Sat, 11 Jun 2016 11:29:42 GMT;HttpOnly;secure"
其中name=value是必选项，其它都是可选项。Cookie的主要构成如下：

**name:** 
一个唯一确定的cookie名称。通常来讲cookie的名称是不区分大小写的。
**value:**
存储在cookie中的字符串值。最好为cookie的name和value进行url编码
**domain:**
cookie对于哪个域是有效的。所有向该域发送的请求中都会包含这个cookie信息。这个值可以包含子域(如：
yq.aliyun.com)，也可以不包含它(如：.aliyun.com，则对于aliyun.com的所有子域都有效).
**path:** 
表示这个cookie影响到的路径，浏览器跟会根据这项配置，像指定域中匹配的路径发送cookie。
**expires:**
失效时间，表示cookie何时应该被删除的时间戳(也就是，何时应该停止向服务器发送这个cookie)。如果不设置这个时间戳，浏览器会在页面关闭时即将删除所有cookie；不过也可以自己设置删除时间。这个值是GMT时间格式，如果客户端和服务器端时间不一致，使用expires就会存在偏差。
**max-age:**
 与expires作用相同，用来告诉浏览器此cookie多久过期（单位是秒），而不是一个固定的时间点。正常情况下，max-age的优先级高于expires。
**HttpOnly:**
 告知浏览器不允许通过脚本document.cookie去更改这个值，同样这个值在document.cookie中也不可见。但在http请求张仍然会携带这个cookie。注意这个值虽然在脚本中不可获取，但仍然在浏览器安装目录中以文件形式存在。这项设置通常在服务器端设置。
**secure:** 
安全标志，指定后，只有在使用SSL链接时候才能发送到服务器，如果是http链接则不会传递该信息。就算设置了secure 属性也并不代表他人不能看到你机器本地保存的 cookie 信息，所以不要把重要信息放cookie就对了服务器端设置。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020101954674.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020102011195.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

## 7.鉴权
### （1）什么是鉴权
鉴权（authentication）是指验证用户是否拥有访问系统的权利。传统的鉴权是通过密码来验证的。这种方式的前提是，每个获得密码的用户都已经被授权。在建立用户时，就为此用户分配一个密码，用户的密码可以由管理员指定，也可以由用户自行申请。这种方式的弱点十分明显：一旦密码被偷或用户遗失密码，情况就会十分麻烦，需要管理员对用户密码进行重新修改，而修改密码之前还要人工验证用户的合法身份。
为了克服这种鉴权方式的缺点，需要一个更加可靠的鉴权方式。目前的主流鉴权方式是利用认证授权来验证数字签名的正确与否。
逻辑上，授权发生在鉴权之后，而实际上，这两者常常是一个过程。
### （2）鉴权方式
我们常用的鉴权有四种：
1、HTTP Basic Authentication
2、session-cookie
3、Token 验证
4、OAuth(开放授权)

一般涉及到的都是Token

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020102430269.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
有一些api在访问之前必须进行登录
一般测试人员在测试的时候只需要：
1.获取token（抓包，直接查看）
2.设置headers
    
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010245681.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 8.cllection容器
### 集合概述 

集合：集合是java中提供的一种容器，可以用来存储多个数据。
集合和数组既然都是容器，它们有什么区别呢？

数组的长度是固定的。集合的长度是可变的。
数组中存储的是同一类型的元素，可以存储任意类型数据。集合存储的都是引用数据类型。如果想存储基本类型数据需要存储对应的包装类型。
集合常用类的继承体系

**Collection：**
单列集合类的根接口，用于存储一系列符合某种规则的元素，它有两个重要的子接口，分别是**java.util.List**和**java.util.Set**。其中，List的特点是元素有序、元素可重复。Set的特点是元素不可重复。List接口的主要实现类有java.util.ArrayList和java.util.LinkedList，Set接口的主要实现类有java.util.HashSet和java.util.LinkedHashSet。

 一张图来描述集合常用类的继承体系

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020103340772.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

集合本身是一个工具，它存放在java.util包中。在Collection接口定义着单列集合框架中最最共性的内容。
### Collection 常用API
**Collection是所有单列集合的父接口**，因此在Collection中定义了单列集合(List和Set)通用的一些方法，这些方法可用于操作所有的单列集合。方法如下：
**public boolean add(E e)：** 把给定的对象添加到当前集合中 。
**public void clear():** 清空集合中所有的元素。
**public boolean remove(E e):** 把给定的对象在当前集合中删除。
**public boolean contains(Object obj):** 判断当前集合中是否包含给定的对象。
**public boolean isEmpty()**: 判断当前集合是否为空。
**public int size():** 返回集合中元素的个数。
**public Object[] toArray():** 把集合中的元素，存储到数组中

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104247715.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 9. 变量
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104357776.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010441211.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 10. 环境变量方法1实例
实列：
接口文档：
 [接口文档](https://www.v2ex.com/p/7v9TEc53%20%E6%B5%8B%E8%AF%95%E7%9A%84url%EF%BC%9A)
 [测试url](https://www.v2ex.com/api/nodes/show.json?name=python)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104443234.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
打开postman
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104555449.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
name=python，将name设置为全局变量时爆红，先要设置环境变量
点击
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104613779.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
添加环境变量
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104635586.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
变量改变颜色，编程橘黄色，send后的结果

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104655418.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 11.全局变量方法二实例
环境变量是与 环境相关的
全局变量是独立于环境的
1.先取消环境变量
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104749535.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
点击
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104805921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
出现：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104819168.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
开始编辑
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010483966.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104847634.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
完成
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104905672.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
注意：当环境变量和全局变量中对同一个个变量名进行不同的赋值时，环境变量的值可以覆盖到全局变量的值
## 12.运行collection
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020104948867.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105001260.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010501058.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 13.运行collection实例生成HTML测试报告
创建collection
再创建一个request请求
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105104571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
点击运行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105120227.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
按钮在命令行中运行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105135242.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
跳转到网页：
https://www.npmjs.com/package/newman

安装newman
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105151880.png#pic_center)
npm install -g newman
在命令行中下载newman
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010521217.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
检验newman是否安装成功

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105225286.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
重新回到postman
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105244597.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105258562.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
导出到本地文件：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102010531423.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
 是一打开cmder或者cmd
跳转到导出的目录下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105340108.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
运行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105353513.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 14.postman导出python脚本
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141516134.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141532884.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
首先安装Python（这里已经安装）
查看python版本
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141551574.png#pic_center)
pip下载requests库（之前已经下载过）：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141612566.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
在postman中点击Code
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141630673.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
选择：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141704555.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
**点击右上角复制：**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141737460.png#pic_center)

创建一个py文件在pycharm中打开

 

 

```python
import requests
import unittest

class v2exAPITestCase(unittest.TestCase):
  def test_node_api(self):
    url = "https://www.v2ex.com/api/nodes/show.json?name=python"

    payload = {}
    querystring ={"name" :"python"}
    headers = {
      'Cookie': '__cfduid=d333f7a16684a741d353302599a54b2921603071821'
    }

    response = requests.request("GET", url, headers=headers, data=payload).json()
    self.assertEqual(response['name'], querystring['name'])
    # print(response.text.encode('utf8'))

if __name__ == '__main__':
    unittest.main()
```
 
运行成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020141840294.png#pic_center)
重新修改加入数据驱动
修改后的测试代码为：

```python
import requests
import unittest

class v2exAPITestCase(unittest.TestCase):
  def test_node_api(self):
    url = "https://www.v2ex.com/api/nodes/show.json?name=python"
    payload = {}
    headers = {
      'Cookie': '__cfduid=d333f7a16684a741d353302599a54b2921603071821'
    }
    # querystring ={"name" :"python"}
    for node_name in ['php','python','qna']:
      response = requests.request("GET", url, headers=headers,  params={'name': node_name}).json()
      self.assertEqual(response['name'], node_name)


if __name__ == '__main__':
    unittest.main()
```
运行成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102014192443.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


# 5、postman中断言和抓包
## 1.测试断言
断言：实际结果和期望结果的比对的过程
比对数据：状态码，返回数据，响应头，响应时间
在test中编写js进行断言
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020105937990.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
tm.response是指相应对象
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110107336.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
首先创建一个管理文件夹（集合）
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110123256.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
存放一个项目中的所有接口测试便于管理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110139367.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
在test中编写断言
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110156991.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110207807.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
结果是绿色的表示通过
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110223413.png#pic_center)
结果是红色的表示不通过
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110237728.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
需要保存js代码是Ctrl+S键
输入请求名
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102011025650.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
选择存放接口的管理文件
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110313243.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 2.postman中充当代理进行app抓包
电脑——》postman——》手机
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102011070080.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

如何在postman中设置代理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110754852.png#pic_center)
postman中

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102011080855.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
点击代理显示代理设置：
填写端口号
选择抓取到的包存放在哪个管理文件夹中
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110826324.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
之后在手机上设置
![在这里插入图片描述](https://img-blog.csdnimg.cn/202010201108420.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
端口号一定一致
服务器是电脑的IP 
设置之后在手机端操作会在postman中增加requests
点击雷达代理的图案关闭代理
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201020110900971.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
抓包是为了查看数据

 
# 总结
 参考链接附上
 [postman](https://www.cnblogs.com/ll-gaocheng/p/11051896.html)
  [为什么要进行接口测试](https://www.zhihu.com/question/63685635/answer/1256694015)
 [postman基础 ](https://zhuanlan.zhihu.com/p/50378333)
 [http请求方式](https://www.cnblogs.com/weibanggang/p/9454581.html)
 [cookie](https://blog.csdn.net/zhangquan_zone/article/details/77627899)
 [collection集合](https://baijiahao.baidu.com/s?id=1668989802350553884&wfr=spider&for=pc)


 

