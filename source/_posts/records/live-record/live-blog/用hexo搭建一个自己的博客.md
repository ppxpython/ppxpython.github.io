---
title: 用hexo搭建一个自己的博客
abbrlink: 16714
date: 2020-10-22 16:51:04
categories:
  - [心得记录,生活记录,个人博客]
tags: 博客搭建
---
# 系列文章目录
 
@[TOC](文章目录) 
# 前言
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022152856330.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
 分享搭建hexo个人博客的过程
 参考文档链接在 总结模块中
# 一、Hexo是什么？

Hexo是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。即把用户的markdown文件，按照指定的主题解析成静态网页。
 


# 二、安装Hexo
安装Hexo钱需要一些环境依赖，接下来我们就来一步一步安装
## 1.安装node.JS
### 1.下载安装包
 Node.js 官方网站下载：https://nodejs.org/en/[node.js官网](https://nodejs.org/en/)
选择操作系统对应的包：

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022155931920.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
下载完成，安装包如下：

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160155165.png#pic_center)

### 2、安装
打开安装，傻瓜式下一步即可：
 

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160202461.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160218388.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

选择安装位置，我这里装在D盘下：

 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160228674.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160240285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160246205.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

 

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160351984.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160358528.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

 
安装成功，文件夹结构如下，并在上面安装过程中已自动配置了环境变量和安装好了npm包，此时可以执行 node -v 和 npm -v 分别查看node和npm的版本号：

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160406245.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

### 3、配置npm在安装全局模块时的路径和缓存cache的路径
因为在执行例如`npm install webpack -g` 等命令全局安装的时候，默认会将模块安装在C:\Users\用户名\AppData\Roaming路径下的npm和npm_cache中，不方便管理且占用C盘空间，如下图所示：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160446689.png#pic_center)

所以这里配置自定义的全局模块安装目录，在node.js安装目录下新建两个文件夹 node_global和node_cache，然后在cmd命令下执行如下两个命令：
`npm config set prefix "D:\Program Files\nodejs\node_global"` 
`npm config set cache "D:\Program Files\nodejs\node_cache"` 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160455508.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

执行成功。然后在环境变量 -> 系统变量中新建一个变量名为

>  “NODE_PATH”

， 值为

> “D:\Program Files\nodejs\node_modules”

，如下图：
  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160550279.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


 
最后编辑用户变量里的Path，将相应npm的路径改为：

> D:\Program Files\nodejs\node_global

，如下：
更改前：
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160557678.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

更改后：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160604671.png#pic_center)

配置完成。

### 4.测试 
安装完成后可以使用cmd（win+r然后输入cmd进入）测试下是否安装成功。
方法：在cmd下输入`node -v`，出现下图版本提示就是完成了NodeJS的安装。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022160956465.png#pic_center)
### 5.安装已完成
常规NodeJS的搭建到现在为止已经完成了。

## 2.npm配置 
6、npm配置
npm作为一个NodeJS的模块管理，很有必要列出一些：
①、模块路径、cache路径
先配置npm的全局模块的存放路径以及cache的路径，
例如希望将以上两个文件夹放在NodeJS的主目录下，便在NodeJs下建立"node_global"及"node_cache"两个文件夹。如下图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022161140713.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


②、使用cmd命令进行配置
启动cmd，输入

```bash
npm config set prefix "H:\nodejs\node_global"
```

```bash
npm config set cache "H:\nodejs\node_cache"
```

如果不进行这一步设置，npm的全局安装包，将不会在node安装文件夹里。
如果这个步骤出现错误，如：operation not permitted, mkdir 'C:\Program Files\nodejs'，请使用管理员身份打开cmd命令行。
③、测试
现在我们来装个模块试试，
在cmd命令行里面，输入“`npm install express -g`”（“-g”这个参数意思是装到global目录下，也就是上面说设置的“H:\nodejs\node_global”里面。）。
④、查看环境变量
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102216120689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022161215478.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

⑤、配置node_path
进入环境变量对话框，在系统变量下新建"NODE_PATH"，输入”`H:\nodejs\node_global\node_modules“`。（ps：这一步相当关键。）
2014.4.19新增：由于改变了module的默认地址，所以上面的用户变量都要跟着改变一下（用户变量"PATH"修改为“H:\nodejs\node_global\”），要不使用module的时候会导致输入命令出现“xxx不是内部或外部命令，也不是可运行的程序或批处理文件”这个错误。

 8、安装淘宝npm（cnpm）
   (1)输入以下命令

```bash
npm install -g cnpm --registry = https：//registry.npm.taobao.org
```

   (2)添加系统变量path的内容
　　因为cnpm会被安装到H:nodejs\node_global下，而系统变量path并未包含该路径。在系统变量path下添加该路径即可正常使用cnpm。
  (3)输入`cnpm -v`命令，查看结果

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022161344956.png#pic_center)
 测试cnpm

```bash
cnpm -v
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102216190448.png#pic_center)
# 三、开始搭建Hexo
## 1.创建本地hexo博客
```bash
cnpm install -g hexo-cli
```

全局安装框架
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162222991.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

验证

```bash
hexo -v
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162237645.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

安装完成、
创建项目目录空文件夹testblog
初始化hexo

```bash
hexo init
```

需要等待一段时间
初始化成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/202010221622502.png#pic_center)

```bash
dir
```

查看生成的文件
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162257710.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

启动hexo

```bash
hexo s
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162319529.png#pic_center)

启动成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162325796.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

先断开
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162332362.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162337591.png#pic_center)
创建我的第一篇博客文章：

```bash
hexo n "我的第一篇博客文章"
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162452107.png#pic_center)

查看文章

```bash
cd source/_posts/
```

```bash
dir
```
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102216260614.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


编写博客内容
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162613918.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


回退目录

```bash
cd..
```

```bash
cd..
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162633584.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


清理博客

```bash
hexo clean
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162710893.png#pic_center)
 

生成博客

```bash
hexo g
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162721268.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

重新启动

```bash
hexo s
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162734122.png#pic_center)

新文章生成：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162742689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 2.github中博客
github
创建一个仓库


![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162912392.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162918660.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


用户名.github.io一定要是这样的格式否则会报错
 **config.yml**
中修改

```bash
deploy:
  type: 'git' 
  repo: https://github.com/ppxpython/ppxpython.github.io.git 
  branch: master  
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022162958121.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


```bash
hexo clean
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163010929.png#pic_center)

```bash
hexo g
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163020688.png#pic_center)

```bash
hexo d
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163037507.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

刷新查看仓库
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163043727.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

打开网址：
https://ppxpython.github.io/

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163051921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

## 3.gitee中博客
在gitee上创建一个仓库

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163300166.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

安装工具

```bash
cnpm install --save hexo-deployer-git
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163316359.png#pic_center)

```bash
dir
```

查看
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163327454.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


需要设置**config.yml**文件
打开文件到最下面更改

```bash
# Deployment
## Docs: https://hexo.io/docs/one-command-deployment
deploy:
  type: 'git' 
  repo: https://gitee.com/ppxpython/testblog.git 
  bronch: master 
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163413621.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

没有引号都没关系
部署远端

```bash
hexo d
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163428812.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

成功

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163436449.png#pic_center)

刷新gitee显示代码：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163445215.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

点击：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163452430.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

显示：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102216345846.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


启动成功：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163504245.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


网页：

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020102216351173.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

发现没有样式，不要着急，更改配置文件：

```bash
url: https://ppxpython.gitee.io/testblog
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/202010221635425.png#pic_center)

```bash
hexo clean
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163547650.png#pic_center)

```bash
hexo d
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163555372.png#pic_center)

在gitee上查看更新
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163608279.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

# 3.更改主题
下载主题：
选择自己喜欢的主题

```bash
git clone https://github.com/ShanaMaid/hexo-theme-shana.git themes/ShanaMaid
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163753909.png#pic_center)

修改配置文件
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163805787.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


```bash
hexo clean
```
本地查看
hexo s
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163823260.png#pic_center)


 效果：

```bash
http://localhost:4000/easyblog/
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163845843.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

```bash
hexo d
```

部署上去
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163909953.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)



在gitee上更新一下
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201022163919206.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


部署成功，点击网址，查看我的博客
最后附上 [我的博客](https://ppxpython.github.io/)：
 https://ppxpython.github.io/


# 总结
参照的链接这里附上：
[Node.js安装链接](https://blog.csdn.net/antma/article/details/86104068)
