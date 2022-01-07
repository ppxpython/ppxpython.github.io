---
title: Django详细介绍todolist实例
abbrlink: 15712
date: 2022-01-05 10:41:40
tags: Django
categories:
- [计算机科学, Python, Django框架, 零基础学Django框架]
---
## 开发环境

python3.7

django

win10（64位）

## 什么是框架

通俗的说，框架是实现某种功能的半成品，提供了一些常用的工具类和一些基础通用化的组件，可以供开发人员在此基础上，更高效的满足各自的业务需求。

## 为什么要使用框架

一个优秀的的框架，它相当于是一个模板代码库，很多基础性的功能,底层功能操作都已经帮我们实现了，我们只需要专心的实现所需要的业务逻辑就可以了。这样，就大大提高了我们的开发效率，所以技术的发展，多数情况下是为了满足业务的需求。

简单，快捷，高效，响应，兼容

## 什么是django

我们都知道，Django是基于Python的Web开发框架。

百度百科介绍：

Django是一个开放[源代码](https://baike.baidu.com/item/%E6%BA%90%E4%BB%A3%E7%A0%81/3814213)的[Web应用框架](https://baike.baidu.com/item/Web%E5%BA%94%E7%94%A8%E6%A1%86%E6%9E%B6/4262233)，由[Python](https://baike.baidu.com/item/Python/407313)写成。采用了MTV的框架模式，即模型M，视图V和模版T。它最初是被开发来用于管理劳伦斯出版集团旗下的一些以新闻内容为主的网站的，即是CMS（内容管理系统）软件。并于2005年7月在[BSD许可证](https://baike.baidu.com/item/BSD%E8%AE%B8%E5%8F%AF%E8%AF%81/10642412)下发布。

这套框架是以比利时的吉普赛[爵士吉他](https://baike.baidu.com/item/%E7%88%B5%E5%A3%AB%E5%90%89%E4%BB%96/4696201)手Django Reinhardt来命名的。

有一家劳伦斯的出版社，说白了就想新浪。这种网站会涉及到什么问题呢我们来看一下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/c05a55328e394c1da23a9a7f66787826.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

只需进行数据库替换，采用此模板样式不变，那网站的开发速率提高

## django目的和用途

django的主要目的是**简便，快速**的开发**数据库驱动**的网站，他强调代码复用。

多个组件看依方便的以“插件”形式服务整个框架

**所有的web框架的意义都在于：**

1. 搭建框架应用
2. 免去不同web应用相同代码的部分重复编写，只需关心应用核心的业务实现

}}}

}}}

## django的特点

对比Flask框架，Django原生提供了众多的功能组件，让开发更便捷

1. 提供项目工程管理的自动脚手工具（脚手架工具）
2. 数据库ORM支持（对象关系映射）[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-GygyZD04-1632645131208)(assets/image-20210921214755-gc5rj3l.png)]【不会sql语句也可以实现】
3. 模板【replace，可以通过变量将模板和数据打通。使用数据替换模板变量，达到动态展示效果】
4. 表单【表单获取直接转化成对象处理】
5. admin管理站点【自动生成后台】
6. 文件管理
7. 认证权限
8. session机制
9. 缓存

![在这里插入图片描述](https://img-blog.csdnimg.cn/757319e9e9534c6fbb7fc517f248c1ea.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_13,color_FFFFFF,t_70,g_se,x_16)

如果Django类似于精装修的房子，自带豪华家具、非常齐全功能强大的家电，什么都有了，拎包入住即可，十分方便。重量级框架，快捷。

![在这里插入图片描述](https://img-blog.csdnimg.cn/5c06637e024842678528696dc46b3345.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_13,color_FFFFFF,t_70,g_se,x_16)

而Flask类似于毛坯房，自己想把房子装修成什么样自己找材料，买家具自己装。材料和家具种类非常丰富，并且都是现成免费的，直接拿过去用即可。轻量级，灵活。

## MVT设计模式

![](https://img-blog.csdnimg.cn/2fb652d4bc814b5789d1f1bd439f3de7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

前端客户端发起请求，请求可能是用户点击浏览器发起的，app，ajax请求或是爬虫程序，

服务器：接受和解析http请求报文，他的服务对象是http请求

框架：后端服务框架，服务器解析成字典格式{”request_path“：request}

视图：定义数据处理方法：index（）然后经处理完的结果变成响应对象，发送给服务器

中间层：装饰器

作用：在不添加源代码的情况下增加功能

#补充知识点#

((20210923102902-68l094i))

WSGI只是一个**PythonWeb服务器网关接口协议**，或者说是一份标准，用来描述Server与Framework之间的通信接口。

这样，一些符合WSGI标准的Framework如Flask、Django、web.py等等就可以与同样符合WSGI标准的Server库进行无缝对接。

只要你的Framework符合WSGi规范，那么在以后有了效率更高的Server的时候，你可以毫不费力地将代码迁移过去。

#场景#：开发了几个应用后，发现每个应用都完成了从监听网络端口到建立连接、解析请求的参数、进行回应、发送Response数据包等等一系列的工作，每次都要在获取请求、解析请求、发送请求这些一成不变的步骤上花费大量时间，不如写个Server模块，把这些功能单独实现，以后再有新的需求，只需要考虑Framework部分即可，这样就可以避免“重复造轮子”了。当自己写好了一套server程序，隔壁老王听说你写了个Server程序很牛掰，想要借用一下你的代码。你本着开源精神将Server模块分享给他，可是，老王拿到代码一看就傻眼了——天啊，你的Server部分的数据接口、函数调用方式和他自己写的Framework完全不搭，改动起来难度颇大，还不如自己再写一个Server来得方便。应该整一套接口规范出来，让老王在编写自己的Framework的时候就按照你设计的规范来写，这样写出来的程序才能够互相“契合”，便于调试和使用。就是WSGI（Python Web Server Gateway）

### **MVC**

程序设计模式：MVC，核心思想**：分工，解耦**，让不同的代码块之间降低耦合，增强代码的可扩展性和可移植性，实现向后兼容
![在这里插入图片描述](https://img-blog.csdnimg.cn/a73b713de951442fba00f3e7b32906c7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

**M**全拼为Model，主要封装对数据库的访问，对数据库中**数据进行增删改查**操作

**V**全拼为View，用于封装结果，**生成页面展示的html**

**C**全拼Controller，用于接收请求，**处理业务逻辑**，与Model和View进行交互，返回结果

### **MVT**

原理就是mvc不过自己将名字改了

![在这里插入图片描述](https://img-blog.csdnimg.cn/327ef1142afe453fbe8800ae1ab8d1bd.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_18,color_FFFFFF,t_70,g_se,x_16)

**M**全拼为Model，与MVC中的**M**功能相同，主要封装对数据库的访问，对数据库中**数据进行增删改查**操作

**V**全拼为View，与MVC中的**C**功能相同，用于接收请求，**处理业务逻辑**，与Model和View进行交互，返回结果

**T**全拼Template，与MVC中的**V**功能相同，用于封装结果，**负责封装构造要返回的htm**l

((20210924115549-5h51jh6))

## 虚拟环境

### 什么场景需要用虚拟环境

![在这里插入图片描述](https://img-blog.csdnimg.cn/246673b637ec44fdb412970e4f387173.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/61c59d045ab1428baa225725f4a81d23.png)

比如两个项目在并行，然后用到的python和django版本不一样

解释器一样包都可能不一样

### 虚拟环境效果

[ ![在这里插入图片描述](https://img-blog.csdnimg.cn/4071780b82744bf1ac2f342e6d32517b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_18,color_FFFFFF,t_70,g_se,x_16)

((20210923111014-udk4aum))

# 实战

## 搭建环境

默认会下载最新版本

`pip install django`
![在这里插入图片描述](https://img-blog.csdnimg.cn/be491549204b49389d43e65bd6feee63.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

## 创建工程

进入**想要创建的项目目录**下

![在这里插入图片描述](https://img-blog.csdnimg.cn/5d6b11a591e64531bd88e10428da796f.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_12,color_FFFFFF,t_70,g_se,x_16)

再命令行中输入

`django-admin startproject todo`

![](https://img-blog.csdnimg.cn/79c5201413144fcaa2111b728ffe957d.png)

查看文件

![ ](https://img-blog.csdnimg.cn/33b77bcecfe44e7994b73c5e160797bc.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_9,color_FFFFFF,t_70,g_se,x_16)

采用pycharm打开项目

然后进入项目中

`cd todo`

![在这里插入图片描述](https://img-blog.csdnimg.cn/a8f201c1ccd84932937b953ae45a42c8.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

尝试启动服务器

在开发阶段，未来能够快速预览到开发效果
django提供了一个纯python编写的轻量级web服务器，仅在开发阶段使用。

` python manage.py runserver`

![在这里插入图片描述](https://img-blog.csdnimg.cn/b46ee99650114e10a5c009e4b629e43a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_18,color_FFFFFF,t_70,g_se,x_16)

![在这里插入图片描述](https://img-blog.csdnimg.cn/fea8ecb71797494388a82374415be90c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

这样这是成功

` python manage.py migrate`

![在这里插入图片描述](https://img-blog.csdnimg.cn/d5f9a09d1695496abe4426475c2a1e46.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_18,color_FFFFFF,t_70,g_se,x_16)

## 创建管理员账号

`python manage.py createsuperuser`

![在这里插入图片描述](https://img-blog.csdnimg.cn/e71995c4f6ae4aa082b7cae285e6abe4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

重新启动服务器：

![在这里插入图片描述](https://img-blog.csdnimg.cn/8763318a678c4f2ca0bde9a353dd45ab.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

登陆刚注册号的账号密码

进入数据管理页面 http://localhost:8000/admin

![在这里插入图片描述](https://img-blog.csdnimg.cn/6ac41ecab9494bc6913c0413faef1536.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

终止服务器，`Ctrl+C`

## 创建子应用

` python manage.py startapp tasks`

![在这里插入图片描述](https://img-blog.csdnimg.cn/8716443073e74fb69c461122a65fb827.png)

查看目录中的结构

![在这里插入图片描述](https://img-blog.csdnimg.cn/9893fc6b9b364286a31e1fac81a8ee97.png)

## 配置app路径

然计算机找到创建的app

在添加

```、
'tasks'
```

查找定位到app的路径

![在这里插入图片描述](https://img-blog.csdnimg.cn/6e1517522c4347709927b6fa6cf2a83e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

跟项目路径：

之前django2.x

```、
BASE_DIR =as.path.dirname(os.path.dirname(os.path.abspath(__file__)))

```

引入path之后

```
BASE_DIR = Path(__file__).resolve().parent.parent
```

C:\Users\yangs\Desktop\新建文件夹\todo\todo\settings.py

## 创建视图函数

再app tasks中创建视图函数 view index

```
from django.shortcuts import render 
from django.http import    HttpResponse 
## Create your views here. 
def index(request):   
    return HttpResponse('hello djangho')
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/515b6f25f89d442cac395ea3c46de68e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

## 创建urls路由

![在这里插入图片描述](https://img-blog.csdnimg.cn/8058ae65f1674bc6800e422b18d878ca.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

## 配置项目urls

![在这里插入图片描述](https://img-blog.csdnimg.cn/2098c7e745784e928ce10d95c3608ea8.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
"""todo URL Configuration  The `urlpatterns` list routes URLs to views. 
For more information please see:     https://docs.djangoproject.com/en/3.2/topics/http/urls/ 
Examples: Function views  
1. Add an import:  from my_app import views   
2. Add a URL to urlpatterns:  path('', views.home, name='home') Class-based views  
1. Add an import:  from other_app.views import Home   
2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home') Including another URLconf   
1. Import the include() function: from django.urls import include, path   
2. Add a URL to urlpatterns:  path('blog/', include('blog.urls')) """ 
from django.contrib import admin 
from django.urls import path,include  
urlpatterns = [
path('admin/', admin.site.urls),   
path('',include('tasks.urls')) ]
```

## 重启服务器

重新启动服务器 ` python manage.py runserver`

![在这里插入图片描述](https://img-blog.csdnimg.cn/e338878352404f65b447d5cf5ec3b627.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

## 创建模板

创建文件夹templates中再创建tasks文件夹中创建list.html

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-Yhxl9wbo-1632645131300)(assets/clipboard-20210921230301-1lv02wo-20210924095934-379n9oy.png)]

```html
<h3>TODO</h3>
```

## 修改视图

修改app tasks 中的views

![在这里插入图片描述](https://img-blog.csdnimg.cn/fbafdc78d7664bdc91d7a9bcb09ecc50.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.shortcuts import render
from django.http import    HttpResponse
# Create your views here.
def index(request):
    return render(request,'tasks/list.html')
```

此时出现

![在这里插入图片描述](https://img-blog.csdnimg.cn/f552b6c933154fa497ca5edda577e676.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

别着急看看错误提示

## 配置模板默认路径

显示找不到list.html文件，所以我们将从配置setting中设置

![在这里插入图片描述](https://img-blog.csdnimg.cn/d8ade6c117db426dac71a67fd7d2d6e4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

```
"""
Django settings for todo project.

Generated by 'django-admin startproject' using Django 3.2.6.

For more information on this file, see
https://docs.djangoproject.com/en/3.2/topics/settings/

For the full list of settings and their values, see
https://docs.djangoproject.com/en/3.2/ref/settings/
"""
import os
from pathlib import Path

# Build paths inside the project like this: BASE_DIR / 'subdir'.
BASE_DIR = Path(__file__).resolve().parent.parent


# Quick-start development settings - unsuitable for production
# See https://docs.djangoproject.com/en/3.2/howto/deployment/checklist/

# SECURITY WARNING: keep the secret key used in production secret!
SECRET_KEY = 'django-insecure-+(9j8^8xt6(5aa79o^bp8g8#t#lpuif3u424yx55bz=yrk@)d%'

# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = True

ALLOWED_HOSTS = []
# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'tasks',
]

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

ROOT_URLCONF = 'todo.urls'

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')], #连接成模板目录
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

WSGI_APPLICATION = 'todo.wsgi.application'


# Database
# https://docs.djangoproject.com/en/3.2/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}


# Password validation
# https://docs.djangoproject.com/en/3.2/ref/settings/#auth-password-validators

AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]


# Internationalization
# https://docs.djangoproject.com/en/3.2/topics/i18n/

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

USE_I18N = True

USE_L10N = True

USE_TZ = True


# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/3.2/howto/static-files/

STATIC_URL = '/static/'

# Default primary key field type
# https://docs.djangoproject.com/en/3.2/ref/settings/#default-auto-field

DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField'
```

此时刷新一下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/94a972ec67a5460fbb958d1565528f10.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_16,color_FFFFFF,t_70,g_se,x_16)

## 创建模型

之后我们来创建model文件

![在这里插入图片描述](https://img-blog.csdnimg.cn/9d5c4dc54f3e46ddae7b54afc6b211da.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.db import models

# Create your models here.

class Task(models.Model):
    title=models.CharField(max_length=200)
    complete=models.BooleanField(default=False)
    create=models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title
```

再命令行中输入：

## 更新数据库

python manage.py makemigrations

![在这里插入图片描述](https://img-blog.csdnimg.cn/c44e88709d274af1a8831890b80809c0.png)

python manage.py migrate

![在这里插入图片描述](https://img-blog.csdnimg.cn/db4bccd56562420c813c8bcfeccfa59b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

将数据库进行更新

## 启动服务器：

python manage.py runserver

![在这里插入图片描述](https://img-blog.csdnimg.cn/305b61c394204d74a168fc5918e91543.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

访问8000:/admin

![<span data-type=](https://img-blog.csdnimg.cn/01fe157ce7d74a23b6f1a1941909257a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)\[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-KLguiQfn-1632645131322)(assets/clipboard-20210921230301-svzfg5q-20210924095934-vw2uo7h.png)\]" />

没有发现新建的model

## 用户和model进行关联

需要将用户和model进行关联

在app tasks中admin中

![在这里插入图片描述](https://img-blog.csdnimg.cn/497a47161e8843a593304e2cf913a9ad.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.contrib import admin
from .models import *
# Register your models here.
admin.site.register(Task)
```

重新刷新页面 ![在这里插入图片描述](https://img-blog.csdnimg.cn/a31bad1777e243c7a863dddba34617f3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

其中新创建的模块

## 添加数据库数据

添加数据并在数据库中查看数据：

![在这里插入图片描述](https://img-blog.csdnimg.cn/1de7e6a02d1a408b9f539fa45434de63.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/00154d7c0c714d40972aad77605565da.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

现在我们想要将数据库中的数据显示在views中

将models中映射的数据放在view中展示出来

## 展示数据

![在这里插入图片描述](https://img-blog.csdnimg.cn/abfc94f318f14fb4b3383dbff559b9c3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

### 修改view

在app tasks中view修改

```
from django.shortcuts import render
from django.http import    HttpResponse
from .models import *

# Create your views here.
def index(request):
    tasks=Task.objects.all()
    context={'tasks',tasks}
    return render(request,'tasks/list.html',context)
```

### 修改html

将数据传入模板当中

list.html

![在这里插入图片描述](https://img-blog.csdnimg.cn/dc5d97b9d81b49058789cd34ac5c0a05.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```html
<h3>TO DO</h3>
{% for task in tasks %}
<p>task.title</p>
{% endfor %}
```

在app tasks中创建form文件

### 创建form

```
from django import forms
from django.forms import ModelForm
from .models import *

class TaskForm(forms.ModelForm):
    class Meta:
        model=Task
        fields='__all__'
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/f33ff9da2cdf4856a874e091eb29ea2d.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

### 修改view

在view中更改：

```
from django.shortcuts import render
from django.http import    HttpResponse
from .models import *
from .forms import *
# Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)
```

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/47aefcae44c847eb965b469acb91a7e3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

### 更改模板文件：

```
<h3>TO DO</h3>
<form>
    {{form}}
    <input type="submit" name="create Task">
</form>
{% for task in tasks %}
<p>{{task.title}}</p>
{% endfor %}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/ff397403c7e34dc4bd6022890b1703d4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

查看页面：

![在这里插入图片描述](https://img-blog.csdnimg.cn/ad8bb0edb98e4963a7d7f3e45bcfbf1a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_16,color_FFFFFF,t_70,g_se,x_16)

## 添加数据

### 修改模板html页面：

```
<h3>TO DO</h3>
<form method="POST" action="/">
    {{form}}
    <input type="submit" name="create Task">
</form>
{% for task in tasks %}
<p>{{task.title}}</p>
{% endfor %}
```

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/56925a483e6d41b791553d3d59bf2ae2.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/14e11bc7a06342dabb153b71940adc9d.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *
# Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')
    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)
```

启动发现：

输入数据点击提交

![在这里插入图片描述](https://img-blog.csdnimg.cn/53553f3f7f0949c39f5f2c54cbb39232.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

此时我们设置一下list,html

### 修改html

```
<h3>TO DO</h3>
<form method="POST" action="/">
    #csrf_token  #数据发送django自带保护机制
    {{form}}
    <input type="submit" name="create Task">
</form>
{% for task in tasks %}
<p>{{task.title}}</p>
{% endfor %}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/2ae75fcef9bf4772ba03bcd79809a260.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

在页面上测试添加

![在这里插入图片描述](https://img-blog.csdnimg.cn/a7d5216c120142898778d82a89d64c62.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_16,color_FFFFFF,t_70,g_se,x_16)

成功，现在我们来编写

## 修改页面

先在模板下创建update_task.html页面

### 修改html

![在这里插入图片描述](https://img-blog.csdnimg.cn/be2db14b4a5d40c99ae5743b66b4a2f3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
<h3>Update Task</h3>
<form>
    <input type="submit" name="Update Task">
</form>
```

### 修改view

在views页面中进行修改：

![在这里插入图片描述](https://img-blog.csdnimg.cn/3c61cee232a8445ca413c0bc5fbdffc4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *
# Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')

    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)
def updateTask(request,pk):
    task=Task.objects.all(id=pk)
    return render(request,'tasks/update_task.html')
```

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/c5a48a4282a9490f902f48528bef972a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

### 修改url

修改app task中的urls

```html
from django.urls import path
from . import views

app_name = 'tasks'
urlpatterns = [
    path('', views.index, name='list'),
    path('update_task/<str:pk>',views.updateTask,name='update_task'),
]
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/1e7c6195ce054c7fadc1c39b45092167.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

![在这里插入图片描述](https://img-blog.csdnimg.cn/849a9c84760c4754b44ef7bdf0be220b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

![这里插入图片](https://img-blog.csdnimg.cn/a98842752aaf4568a25c06ee15b92a60.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

接着我们需要在修改页面写入响应的数据和输入框

![在这里插入图片描述](https://img-blog.csdnimg.cn/e8dc00773f9747cea7b9488478b1076c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *
# Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')

    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)

def updateTask(request,pk):
    task=Task.objects.get(id=pk)
    form=TaskForm(instance=task)
    context={'form':form}
    return render(request,'tasks/update_task.html',context=context)
```

### 修改html

修改模板update_task页面：

![在这里插入图片描述](https://img-blog.csdnimg.cn/bd6a63b2256a46e4b825b76b63d4e379.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```html
<h3>Update Task</h3>
<form>
  
    {{form}}
    <input type="submit" name="Update Task">
</form>
```

页面显示
![在这里插入图片描述](https://img-blog.csdnimg.cn/ca13287a29a44109a081852081ae0180.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/fb497bd0b1094c45a0c657ea8c7bb1cd.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

这里只是显示出来还不能修改

修改页面

![在这里插入图片描述](https://img-blog.csdnimg.cn/1b53e85217b3439a80dddf58d2620cff.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
<h3>Update Task</h3>
<form method="post" action="">
   
    {{form}}
    <input type="submit" name="Update Task">
</form>
```

### **修改view文件：**

![在这里插入图片描述](https://img-blog.csdnimg.cn/8c801893c4004ce8bb6949f76bf1f1b3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *
# Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')

    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)

def updateTask(request,pk):
    task=Task.objects.get(id=pk)
    form=TaskForm(instance=task)
    if request.method=='POST':
        form = TaskForm(request.POST, instance=task)
        if form.is_valid():
            form.save()
            return redirect('/')
    context={'form':form}
    return render(request,'tasks/update_task.html',context=context)
```

`<br />` ![在这里插入图片描述](https://img-blog.csdnimg.cn/b31e74e28bb64627ae8b602a72440052.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

修改功能实现

## 删除功能

开始删除功能

### 新建html

![在这里插入图片描述](https://img-blog.csdnimg.cn/611c026fd0a44cd4ab67cf0b41f43ce5.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

创建删除模板

```
<p>Are you sure want to delete "{{item}}" ?</p>
<a href="`{% url 'tasks:list'%}`">Cancel</a>
```

### 修改views

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *
#Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')

    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)

def updateTask(request,pk):
    task=Task.objects.get(id=pk)
    form=TaskForm(instance=task)
    if request.method=='POST':
        form = TaskForm(request.POST, instance=task)
        if form.is_valid():
            form.save()
            return redirect('/')
    context={'form':form}
    return render(request,'tasks/update_task.html',context=context)
def deleteTask(request,pk):
    return render(request,'tasks/delete.html')
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/b7b56309767749a3863e9bc333a5b42b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

### 修改url文件

![在这里插入图片描述](https://img-blog.csdnimg.cn/c763e1af2ab34a71b332ec5842c54ea3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

```
from django.urls import path
from . import views

app_name = 'tasks'
urlpatterns = [
    path('', views.index, name='list'),
    path('update_task/<str:pk>',views.updateTask,name='update_task'),
    path('delete/<str:pk>', views.deleteTask, name='delete_task'),
]
```

### 再次修改view文件

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *

Create your views here.

def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')

    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)
def updateTask(request,pk):
    task=Task.objects.get(id=pk)
    form=TaskForm(instance=task)
    if request.method=='POST':
        form = TaskForm(request.POST, instance=task)
        if form.is_valid():
            form.save()
            return redirect('/')
    context={'form':form}
    return render(request,'tasks/update_task.html',context=context)

def deleteTask(request,pk):
    item=Task.objects.get(id=pk)
    context={'item':item}
    return render(request,'tasks/delete.html',context)<br />
```

### 查看页面

![在这里插入图片描述](https://img-blog.csdnimg.cn/0d2799bebe374092811a0264cdd42b0d.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_16,color_FFFFFF,t_70,g_se,x_16)

<br />

### 修改html删除页面

```
<p>Are you sure want to delete "{{item}}" ?</p>
<a href="`{% url 'tasks:list' %}`">Cancel</a>
<form method="POST" action="">
  
    <input type="submit" name="Confirm">
</form>
```

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/25e741dd87b64a809b914e04732840a0.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

页面展示

![在这里插入图片描述](https://img-blog.csdnimg.cn/bf97e14b2c5544ff8493b1ee4a01a781.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

### 修改views文件

```
from django.shortcuts import render,redirect
from django.http import    HttpResponse
from .models import *
from .forms import *
# Create your views here.
def index(request):
    tasks=Task.objects.all()
    form=TaskForm()
    if request.method=='POST':
        form=TaskForm(request.POST)
        if form.is_valid():
            form.save()
        return redirect('/')

    context={'tasks':tasks,'form':form}
    return render(request,'tasks/list.html',context)

def updateTask(request,pk):
    task=Task.objects.get(id=pk)
    form=TaskForm(instance=task)
    if request.method=='POST':
        form = TaskForm(request.POST, instance=task)
        if form.is_valid():
            form.save()
            return redirect('/')
    context={'form':form}
    return render(request,'tasks/update_task.html',context=context)


def deleteTask(request,pk):
    item=Task.objects.get(id=pk)
    if request.method=='POST':
        item.delete()
        return redirect('/')
    context={'item':item}
    return render(request,'tasks/delete.html',context=context)
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/44dc60890efd44289014cf5c4c9459f8.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

页面展示可以成功删除：
![在这里插入图片描述](https://img-blog.csdnimg.cn/f7b1dc88b9b1425997b76f6bb206687a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_16,color_FFFFFF,t_70,g_se,x_16)

## 修改一下list的html页面：

```
<h3>TO DO</h3>
<form method="POST" action="/">
  
    {{form}}
    <input type="submit" name="create Task">
</form>
`{% for task in tasks %}`
<div>
    <a href="{% url 'tasks:update_task' task.id %}">Update</a>
    <a href="{% url 'tasks:delete' task.id %}">Delete</a>
    {% if 'task.complete==True' %}
    <strike>{{task}}</strike>
    {% else %}
    <span>{{task}}</span>
    {% endif %}

</div>

`{% endfor %}`
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/d7b27def3b24469ba1624d6c1886a74c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)

## 完成的项目 ![在这里插入图片描述](https://img-blog.csdnimg.cn/10ced2fbc2cd443195c2cbd5d42f33e4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_17,color_FFFFFF,t_70,g_se,x_16)

`<br />` ![在这里插入图片描述](https://img-blog.csdnimg.cn/8656b5cc13eb4b5fbb5773512ddfc2f4.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_19,color_FFFFFF,t_70,g_se,x_16)

<br />

![在这里插入图片描述](https://img-blog.csdnimg.cn/810cc0c5287740b5a8c6c0d4dd6baaa8.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_14,color_FFFFFF,t_70,g_se,x_16)

最终效果

![在这里插入图片描述](https://img-blog.csdnimg.cn/3bb4f446140449e4b58b81942509e2d0.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ0MDU0NzU2,size_20,color_FFFFFF,t_70,g_se,x_16)
