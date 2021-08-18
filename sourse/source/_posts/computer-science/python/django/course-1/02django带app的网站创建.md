---
title: 02django带app的网站创建
abbrlink: 23961
date: 2020-09-27 16:27:27
tags: Django
categories:
- [计算机科学, Python, Django框架, 零基础学Django框架]
---
[python]{.label}
[前端框架]{.label .primary}
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191006171226655.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70)

```java 标题 mark:1,6-7
import java.util.Scanner;
...
Scanner in = new Scanner (System.in);
// 输入 Scan 之后，按下键盘 Alt + “/” 键，Eclipse 下自动补全。

System.out.println (in.nextLine ());
System.out.println ("Hello" + "world.");
```

```bash command:("[root@localhost] $":1||"[admin@remotehost] #":4-6)
pwd
/usr/home/chris/bin
ls -la
total 2
drwxr-xr-x   2 chris  chris     11 Jan 10 16:48 .
drwxr--r-x  45 chris  chris     92 Feb 14 11:10 ..
-rwxr-xr-x   1 chris  chris    444 Aug 25  2013 backup
-rwxr-xr-x   1 chris  chris    642 Jan 17 14:42 deploy
```

1. 编译时多态主要指运算符重载与函数重载，而运行时多态主要指虚函数。 {.quiz .true}

2. 有基类 `SHAPE`，派生类 `CIRCLE`，声明如下变量：  {.quiz .multi}
    ```cpp
    SHAPE shape1,*p1;
    CIRCLE circle1,*q1;
    ```
    下列哪些项是 “派生类对象替换基类对象”。
    - `p1=&circle1;` {.correct}
    - `q1=&shape1;`
    - `shape1=circle1;` {.correct}
    - `circle1=shape1;`
{.options}
    > - :heavy_check_mark: 令基类对象的指针指向派生类对象
    > - :x: 派生类指针指向基类的引用
    > - :heavy_check_mark: 派生类对象给基类对象赋值
    > - :x: 基类对象给派生类对象赋值
    > {.options}

3. 下列叙述正确的是 []{.gap} 。 {.quiz}
    - 虚函数只能定义成无参函数
    - 虚函数不能有返回值
    - 能定义虚构造函数
    - A、B、C 都不对 {.correct}
{.options}

10. 如果定义 `int e=8; double f=6.4, g=8.9;`，则表达式 `f+int (e/3*int (f+g)/2)%4` 的值为 [9.4]{.gap}。 {.quiz .fill}
    > 注意运算顺序和数据类型
    > [8.4]{.mistake}



:kissing_heart:
:ring:
:notes:


 [python]{.label}
[primary]{.label .primary}
[info]{.label .info}
[:heavy_check_mark:success]{.label .success}
[warning]{.label .warning}
[:broken_heart:danger]{.label .danger} 
