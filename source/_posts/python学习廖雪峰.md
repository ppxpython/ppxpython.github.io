---
title: python学习廖雪峰
abbrlink: 51739
date: 2022-01-05 11:47:31
tags:
---

[使用dict和set - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/1016959663602400/1017104324028448)

用于学习记录，后期便于复习，参考链接

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102447-hmq8gs8.png)

python file

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102545-qqmxrgo.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102644-7ny4t2k.png)

调用脚本时会先载入pyhton解释器，然后运行脚本

rpm：软件管理包

操作符优先级：![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009104337-b66ot2k.png)

条件判断：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009104751-a27qfzb.png)

Python为我们提供了非常完善的基础代码库，覆盖了网络、文件、GUI、数据库、文本等大量内容，被形象地称作“内置电池（batteries included）”。用Python开发，许多功能不必从零编写，直接使用现成的即可。

语言定位：

Python的定位是“优雅”、“明确”、“简单”

Python是解释型语言

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211011172523-7k51l6e.png)

# python

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009110719-7urayjl.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009111236-gd1mcju.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009111303-l3bqira.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009113303-w7qziw5.png)

## 数据类型

### int 整型

long int长整型

int 整型

### float 浮点型

浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时

双精度浮点型 e

浮点型

### String 字符串

字符串是以单引号 `'`或双引号 `"`括起来的任意文本

字符串是以Unicode编码

对于单个字符的编码，Python提供了 `ord()`函数获取字符的整数表示，`chr()`函数把编码转换为对应的字符：

### Bool布尔

True

Flase

### None 空值

None，`None`不能理解为 `0`，因为 `0`是有意义的,

Null无意义

.

<iframe src="http://127.0.0.1:6806/widgets/brython-editor" data-src="http://127.0.0.1:6806/widgets/brython-editor" data-subtype="widget" border="0" frameborder="no" framespacing="0" allowfullscreen="true" style="width: 1341px; height: 276px;"></iframe>

### 变量

变量的概念基本上和初中代数的方程变量是一致的，

变量不仅可以是数字，还可以是任意数据类型。

变量名必须是大小写英文、数字和 `_`的组合，且不能用数字开头，字母或下划线开头

```python
#变量类型
a=1
b='我是变量'
c=True
d=12.2e3
print(a,b,c,d)
print(type(a),type(b),type(c),type(d))

```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009134601-1cuacaj.png)

int a=1 静态语言 此时已经分配的int分区之后不能更改变量类型【不支持，Java】

a=3 动态语言，可以赋值成任意类型

#### 动态定义

#### 静态定义

```python
a = 'ABC'
b = a
a = 'XYZ'
print(b)
```

执行 `a = 'ABC'`，解释器创建了字符串 `'ABC'`和变量 `a`，并把 `a`指向 `'ABC'`：

![py-var-code-1](https://www.liaoxuefeng.com/files/attachments/923791878255456/0)

执行 `b = a`，解释器创建了变量 `b`，并把 `b`指向 `a`指向的字符串 `'ABC'`：

![py-var-code-2](https://www.liaoxuefeng.com/files/attachments/923792058613440/0)

执行 `a = 'XYZ'`，解释器创建了字符串'XYZ'，并把 `a`的指向改为 `'XYZ'`，但 `b`并没有更改：

![py-var-code-3](https://www.liaoxuefeng.com/files/attachments/923792191637760/0)

### 常量

所谓常量就是不能变的变量，通常用全部大写的变量名表示常量：

```python
PI = 3.14159265359
```

## list列表

list是一种有序的集合，可以随时添加和删除其中的元素。

```python
list=['a','b','c']
print(list)
print(len(list))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154856-r9s5yyu.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154907-bofhvvd.png)

### 切分

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155126-p31z8um.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155139-cpsoatf.png)

### append（）追加

str.append('a')

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155556-qrj4a63.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155606-dxihfwr.png)

### insert插入指定位置

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009162557-186v350.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009162609-u00z8m3.png)

### pop（）删除末尾元素

要删除指定位置的元素，用 `pop(i)`方法，其中 `i`是索引位置

替换元素直接赋值即可

列表可以嵌套

```python
 s = ['python', 'java', ['asp', 'php'], 'scheme']
```

类型可以不同

```python
L = ['Apple', 123, True]
```

### 切片

list[:-1]不包含最后一个元素

list[:]全部列表

list[::]全部列表

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161203-1e12zsd.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161212-0lrqjsm.png)

前10个数，每两个取一个

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161428-r6muafj.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161441-eoc8y55.png)

#### 列表生成

list（range（1，11））生成10个数1-10

```python
print([m+n for m in '123' for n in 'yza'])
```

```python
k=[1,1,23,45,56,[1,12,3,467,[2,4,4,3,22]]]
print([x for x in k if x==1 ])
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012190810-l1qtxiv.png)

## tuple元组

tuple一旦初始化就不能修改

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009163638-1vpldee.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009163652-xkas3o0.png)

但元组初始化后就不能进行更改了

```python
b=(1)
#定义的不是tuple，是1这个数！
# 这是因为括号()既可以表示tuple，又可以表示数学公式中的小括号，
# 这就产生了歧义，因此，Python规定，
# 这种情况下，按小括号进行计算，计算结果自然是1
print(b)
print(type(b))
c=(1,)
print(c)
print(type(c))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009164221-xl1husx.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009164244-780v78f.png)

## dict字典

其他语言叫map，使用键-值（key-value）存储，具有极快的查找速度。dict的key必须是**不可变对象**。key计算位置的算法称为哈希算法（Hash）。

### 定义

```python
d={'name':'ruanyifen','age':60,'happy':'write'}
d['add']='Im add'
d['name']='fix'
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135019-kqmsrcg.png)

### 取value

#### dict['key']

#### 'key' in dict

#### dict.get('key')

```python
print(type(d))
print(d['name'])
print('name' in d)#方法一判断是否有这个主键在字典d中
print(d.get('name'))#方法二 取
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135119-sniqpw0.png)

### dict.pop('key')删除一个key

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135429-m36ygpu.png)

### dict.keys返回字典中所有key列表

### dict.update()将a字典新key，value内容加入b字典中

```bash
dicta={"name":'ruan','age':20}
dictb={"name":'ruan2','age':40,'add':'w shi add'}
dictb.update(dicta)
print(dictb)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115242-qazr588.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115348-bb0l147.png)

#### 内建函数使用

type（）

cmp（）

len（）

hash（）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114202-rdvz2pt.png)

内建cmp（）函数比较两个dict时，先比较长度，后比值，输出1或-1

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114401-h4f1qop.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114644-qffksiw.png)

### dict特点

dict有以下几个特点：

1. 查找和插入的速度极快，不会随着key的增加而变慢；
2. 需要占用大量的内存，内存浪费多。

而list相反：

1. 查找和插入的时间随着元素的增加而增加；
2. 占用空间小，浪费内存很少。
   ![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115427-fu3s2zu.png)
   ![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115451-utxi9ct.png)

## set集合

也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

重复元素在set中自动被过滤

### 定义

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135934-u0n1j77.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135953-sqa88s1.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140114-5azj1sa.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140127-ledkv1s.png)

### set.add('key')添加元素

但重复元素不添加，自动去重

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140336-dwf2vgw.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140344-dzsshz2.png)

### set.remove('key')删除元素

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140511-5f9cwm4.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140517-f6iolow.png)

set可以看成数学意义上的无序和无重复元素的集合，

因此，两个set可以做数学意义上的交集、并集等操作：

### & 两个set交集

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140903-1l3we66.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140912-8itf6ek.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022170721-h5hmgxr.png)

### |两个set并集

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140922-5bjlj5g.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140933-edbys90.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022171729-b4k8xhd.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115701-3dt5x4j.png)

### map()的显示

打印map对象可以看到map对象返回的是一个地址，不是真实的数据

```python
print(list(map对象))
print([it for it in map对象])
```

## 数据类型转换

### int（）

### float（）

### str（）

### bool（）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142636-iblnu9y.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142645-gb2u1fg.png)

## 条件判断

### if

if else

```python
a=100
if a>=0:
    print(a)
else:
    print(-a)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165335-jr8xtfq.png)

if

```python
if True:
    print('True')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165309-ymhiihv.png)

if elif elif else

```python
name='zhangsan'
if name=='zhangsan':
    print('我是',name)
elif name=='lisi':
    print('我是', name)
elif name=='wangwu':
    print('我是', name)
else:
    print('我谁的不是')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165511-spws02g.png)

## input（）输入输出

input()返回的数据类型是str

print（）

## 循环 迭代

list，tuple，dict都可循环

Python的 `for`循环本质上就是通过不断调用 `next()`函数实现的,计算是惰性的

dict循环按照value时：for value in dict.values

```python
for value in d.values():
    print(value)
```

### for in

```python
sum=0
for i in range(1,100):
    sum=sum+i
print(sum)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172805-wrb6kr2.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172805-wrb6kr2.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172821-rdyglwd.png)

### while

```python
sum2=0
k=0
while(k<100):
    sum2=sum2+k
    k=k+1
print(sum2)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172821-rdyglwd.png)

### break

如果要提前结束循环，可以用 `break`语句

### continue

通过 `continue`语句，跳过当前的这次循环，直接开始下一次循环

## 生成器

在Python中，这种一边循环一边计算的机制，称为生成器：generator。

包括生成器和带 `yield`的generator function。

```python
 g = (x * x for x in range(10))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012191035-5wbqtm5.png)

访问大文件

yield

## isinstance（）迭代器

直接作用于 `for`循环的对象统称为可迭代对象，都是迭代器 Iterable

`list`、`tuple`、`dict`、`set`、`str`

`list`、`dict`、`str`虽然是 `Iterable`，却不是 `Iterator`。

`list`、`dict`、`str`等 `Iterable`变成 `Iterator`可以使用**iter()**函数

以直接作用于 `for`循环的数据类型有以下几种：

一类是集合数据类型，如 `list`、`tuple`、`dict`、`set`、`str`等；

一类是 `generator`，包括生成器和带 `yield`的generator function。

可以使用**isinstance()**判断一个对象是否是 `Iterable`对象__iter__：

迭代对象

判断是不是可以迭代，用Iterable

```python
from collections import Iterable
isinstance({}, Iterable) --> True
isinstance((), Iterable) --> True
isinstance(100, Iterable) --> False
```

判断是不是迭代器，用Iterator

```python
from collections import Iterator
isinstance({}, Iterator)  --> False
isinstance((), Iterator) --> False
isinstance( (x for x in range(10)), Iterator)  --> True
```

Python中 list，truple，str，dict这些都可以被迭代，但他们并不是迭代器，为什么：：因为和迭代器相比有一个很大的不同，list/truple/map/dict这些数据的大小是确定的，也就是说有多少事可知的。但迭代器不是，迭代器不知道要执行多少次，所以可以理解为不知道有多少个元素，每调用一次next()，就会往下走一步，是惰性的。

## 函数

抽象

将函数抽象成一个函数名称，不看内部结构直接调用方法

返回类型 函数名（输入参数）：

函数体

### 调用函数

要调用一个函数，需要知道函数的名称和参数

绝对值abs

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142010-d503sa9.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142024-cscdoiu.png)

### 定义函数

```python
def myabs(x):
    if x>0:
        return x
    if x<0:
        return -x
print(myabs(-100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144653-0ds9bc4.png)

### 空函数

```python
def nufun():
    pass
```

`pass`可以用来作为占位符

### 函数 参数检查

```python
def my_init_abs(x):
    if not isinstance(x,(int,float)):
        raise TypeError('no no no')
    else:
        if x>0:
            print(x)
        if x<0:
            print(-x)
my_init_abs(-90)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144640-6xnfm9s.png)

### 可返回多个值，函数

```python
def return_much():
    a='返回'
    b='我也返回'
    c='我也要返回'
    return a,b,c
print(return_much())
print(type(return_much()))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144955-kyvotx4.png)

### 函数参数

***args是可变参数，args接收的是一个tuple；**

****kw是关键字参数，kw接收的是一个dict**。

`power(x)`函数，参数 `x`就是一个位置参数，可单个变量，list，set，tuple

`power(*x)`函数，可传入单个变量，list，set，tuple，可以传入任意个参数或0个参数

`power(**kw)`函数,字典dict

可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。

而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个**dict**.

`power(x, n)`，用来计算x^n^

`power(x, n)`函数有两个参数：`x`和 `n`

默认参数，此时age和city为默认参数，可传值改变也可不变【不用传值】

`power(L=None)`函数有None这个不变对象，可用list

```python
def enroll(name, gender, age=6, city='Beijing'):
    print('name:', name)
    print('gender:', gender)
    print('age:', age)
    print('city:', city)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012151610-9n1rxhq.png)

#### 必选参数

```python
def a1(x):
    return x
print(a1(2))
print(a1(12.1))
print(a1('ruan'))
print(a1(True))
print(a1([1,2,3]))
print(a1({1,2,3}))
print(a1({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012153014-r27ykfm.png)

#### =默认参数

```python
def a2(x=9):
    return x
print(a2())
print(a2(2))
print(a2(12.1))
print(a2('ruan'))
print(a2(True))
print(a2([1,2,3]))
print(a2({1,2,3}))
print(a2({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012153014-r27ykfm.png)

#### *可变参数

```python
def a3(*x):
    return x
print(a3())
print(a3(2))
print(a3(12.1))
print(a3('ruan'))
print(a3(True))
print(a3([1,2,3]))
print(a3({1,2,3}))
print(a3({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012154346-2eahz0b.png)

#### **关键字参数

```python
def a3(**kw):
    return kw
print(a3())
print(a3(kw=2))
print(a3(kw=12.1))
print(a3(kw='ruan'))
print(a3(kw=True))
print(a3(kw=[1,2,3]))
print(type(a3(kw=[1,2,3])))
print(a3(kw={1,2,3}))
print(type(a3(kw={1,2,3})))
print(a3(kw={"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012154409-tp9u2z5.png)

### 递归函数

在函数内部，可以调用其他函数。

一个函数在**内部调用自身本身**，这个函数就是**递归函数**。

使用递归函数需要**注意防止栈溢出**

```python
#递归函数
def funmyself(x):
    if x>1:
        return x+funmyself(x-1)
    elif x==1:
        return 1
print(funmyself(3))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012155139-884p9as.png)

解决栈溢出方法：

**尾递归**优化，事实上尾递归和循环的效果是一样的

尾递归是指，在函数返回的时候，**调用自身**本身，并且，**return语句不能包含表达式**

```python
#尾递归
def funmyself2(n):
    return  funmyself2_it(n,1)

def  funmyself2_it(n,pro):
    if n==1:
        return pro
    else:
        return funmyself2(n-1)+n
print(funmyself2(100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012160333-tngb33o.png)

此时funmyself2是尾递归函数

## 转义字符 `\`

转义字符 `\`可以转义很多字符，比如

`\n`表示换行，

`\t`表示制表符，

字符 `\`本身也要转义，所以 `\\`表示的字符就是 `\`

Python还允许用 `r''`表示 `''`内部的字符串默认不转义

## 运算符and、or和not

运算优先级：not>or>and

## 除法 / //

```python
print(10/3)
print(10//3)
```

#### 除法一 / 浮点数

#### 除法二  //  地板除 整数

`/`除法计算结果是浮点数，即使是两个整数恰好整除，结果也是浮点数：

`//`，称为地板除，两个整数的除法仍然是整数：

## 取余 %

```python
print(10%1)
print(10%3)
print(4%7)
print(2%20)
#如果a%b a>b 则结果为a
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009141744-i2nxg58.png)

## 字符编码

`ASCII`编码

8个比特（bit）作为一个字节（byte）

一个字节能表示的最大的整数就是255（二进制11111111=十进制255）

两个字节可以表示的最大整数是 `65535`，4个字节可以表示的最大整数是 `4294967295`

大写字母 `A`的编码是 `65`，二进制的 `01000001`，小写字母 `z`的编码是 `122`

Unicode把所有语言都统一到一套编码里，这样就不会再有乱码问题

ASCII编码是1个字节，而Unicode编码通常是2个字节

**ASCll出现乱码问题引入Unicode编码存储空间多了一倍引入UTF-8编码**

utf-8：将**Unicode字符根据不同的数字大小编码成1-6个字节，常用的英文字母被编码成1个字节，汉字通常是3个字节，**

| 字符 | ASCII    | Unicode           | UTF-8                      |
| ---- | -------- | ----------------- | -------------------------- |
| A    | 01000001 | 00000000 01000001 | 01000001                   |
| 中   | x        | 01001110 00101101 | 11100100 10111000 10101101 |

在计算机内存中，统一使用Unicode编码，当需要保存到硬盘或者需要传输的时候，就转换为UTF-8编码。

用记事本编辑的时候，从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009142650-uopgqob.png)

浏览网页的时候，服务器会把动态生成的Unicode内容转换为UTF-8再传输到浏览器：

![web-utf-8](https://www.liaoxuefeng.com/files/attachments/923923759189600/0)

#### compile() 字符串编译为字节代码

#### 编码转化

#### ord('A') 字母转字符

#### chr(65) 字符转字母

```python
a=ord('A')
b=chr(65)
print(a,b)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009144810-rm45nsz.png)

#### b'str'转为字节类型bytes

`bytes`类型的数据用带 `b`前缀的单引号或双引号表示

```python
x = b'ABC'
```

要注意区分 `'ABC'`和 `b'ABC'`，前者是 `str`，后者虽然内容显示得和前者一样，但 `bytes`的每个字符都只占用一个字节。

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009145112-3dmegln.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150224-kn57ioe.png)

#### str.encode('ascii') `str` 变为 `bytes `

`ASCII`

`UTF-8`

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150118-wy36xea.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150204-81jvyjd.png)

#### str.decode('utf-8')`bytes`变为 `str`

```python
print(type(b'abc'))
print(b'abc'.decode('utf-8'))
print(type(b'abc'.decode('utf-8')))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150844-zvt6jkv.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150746-31uq63m.png)

len（str）计算字符数

函数计算的是 `str`的字符数，如果换成 `bytes`，`len()`函数就计算字节数

```python
print(len('abc'))
print(len(b'abc'))
print(len('中'))
print(len('中'.encode('utf-8')))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009151234-rhao6fv.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009151321-6k73tn8.png)

## 特殊注释

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
```

第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，**Windows系统会忽略这个注释**；

第二行注释是为了告诉Python解释器，**按照UTF-8编码读取源代码**，否则，你在源代码中写的中文输出可能会有乱码。

## 占位符 格式化

### 占位符%s %d %f

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152324-rmac8lz.png)

格式化方式和C语言是一致

` %`运算符就是用来格式化字符串的。

在字符串内部，

`%s`表示用字符串替换，

`%d`表示用整数替换，

有几个 `%?`占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个 `%?`，括号可以省略

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152708-zy7vi8x.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152722-wq5flos.png)

| 占位符 | 替换内容     |
| ------ | ------------ |
| %d     | 整数         |
| %f     | 浮点数       |
| %s     | 字符串       |
| %x     | 十六进制整数 |

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009153422-r1s8f5z.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009153433-1uhb1w3.png)

转义：`%%`来表示一个 `%`

### format（）格式化字符串

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154141-a3v7tnj.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154153-o6u9yd7.png)

### f-string 格式化字符串

`{r}`被变量 `r`的值替换，`{s:.2f}`被变量 `s`的值替换，并且 `:`后面的 `.2f`指定了格式化参数（即保留两位小数），因此，`{s:.2f}`的替换结果是 `19.62`

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154406-qahm3f7.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154432-m2z0xx5.png)

## 函数式编程

函数是Python内建支持的一种封装，通过层层函数进行调用

#面向过程的程序设计#：把复杂任务分解成简单的任务，这种分解可以称之为面向过程的程序设计

函数式和函数的区别：

对比例子：计算和计算器的区别

编程语言，就是越低级的语言，越贴近计算机，抽象程度低，执行效率高，比如C语言；越高级的语言，越贴近计算，抽象程度高，执行效率低，比如Lisp语言

Python不是纯函数式编程语言

函数式编程就是一种抽象程度很高的编程范式，

纯粹的函数式编程语言编写的**函数没有变量**，因此，任意一个函数，**只要输入是确定的，输出就是确定的**

### 函数式编程特点：

1. 纯函数式编程语言函数没有变量，输入输出确定
2. 允许本身作为参数传入另一个函数，允许返回一个函数

## 高阶函数

参数中有函数

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回

### 变量可以指向函数

a=函数

求绝对值的函数 `abs()`为例

```python
print(abs(-10))
print(abs)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019114343-h6egecv.png)

abs（-10）是函数调用，abs是函数本身

```python
k=abs(-20)
print(k)
#函数本身也可以赋值给变量
h=abs
print(h)
print(h(-100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019114757-z778j3c.png)

结论：函数本身也可以赋值给变量，即：#变量可以指向函数。#

### 函数名也是变量

#函数名#：**其实就是指向函数的变量**

a()中a是指向函数a（）的变量

### 传入函数

既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

#高阶函数#：**一个函数就可以接收另一个函数作为参数**

b()

a(b)

x=a

```python
def f(x):
    return abs(int(x))
def a(a,b,f):
    return f(a)+f(b)
if __name__ == '__main__':
    a1=input('a')
    a2=input('b')
    print(a(a1,a2,f))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019115835-q2esytb.png)

此时函数a为高阶函数，需要调用f函数作为参数

## map/reduce 内建函数

内建了 `map()`和 `reduce()`函数 高阶函数

### map（）函数处理生成新Iterator迭代器

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019131933-ut47b16.png)两个参数，函数名【函数本身】，需要处理的编程式iterator

`<br />`创建一个迭代器，使用每个迭代器中的参数计算函数。当最短迭代用尽时停止。

```python
 map(func, *iterables) --> map object
```

```python
def f(x):
    return x*x
r=map(f,[1,2,3,4,4,4,4,4,4,4,4])
print(r)
print(type(r))
print(list(r))
print(type(list(r)))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019133740-kxaifya.png)

运算规则抽象

### reduce（）函数作用在序列上

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019142951-sxqvxp4.png)

两个参数，函数名【函数本身】，需要处理的#序列#： sequence(序列)是一组有顺序的元素的集合

序列基本样式[下限:上限:步长]

`reduce`把结果继续和序列的下一个元素做累积计算

```python
reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```

```python
from functools import reduce
>>> def fn(x, y):
...     return x * 10 + y
...
>>> reduce(fn, [1, 3, 5, 7, 9])
13579
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019142820-4tlrn7x.png)

## filter()过滤序列

参数和map（）相似

`filter()`也接收一个函数和一个序列

## sorted（）排序

高阶函数![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184319-dzvm55o.png)

参数：排序对象，key=函数

```bash
sorted([36, 5, -12, 9, -21], key=abs)
```

排序的核心是比较两个元素的大小

```bash
print(sorted([1,2,353,6,3,234,43,435]))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184421-43dcfax.png)

key指定绝对值大小排序

```bash
print(sorted([1,2,353,6,3,234,43,435,-242,-34,34,35],key=abs))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184629-q7j7zxx.png)

## 返回函数

### 函数作为返回值

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回

```bash
# 如果不需要立刻求和，而是在后面的代码中，
# 根据需要再计算怎么办？可以不返回求和的结果，而是返回求和的函数：
def zary_sum(a):
    def sum():
        sum1=0
        for i in a:
            sum1=sum1+i
        return sum1
    return sum
print(type(zary_sum([1,2,3,4])))
f=zary_sum([1,2,3,4])
print(f())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100621-oot0dd6.png)

调用返回函数时，每次调用都会新生成一个函数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100747-ho01xzp.png)

## 闭包

当一个函数的返回值是另外一个函数，

而返回的那个函数如果调用了其父函数内部的其它变量，如果 **返回的这个函数在外部被执行，就产生了闭包** 。

**返回函数中，返回的函数调用父函数的内部变量**

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100950-gl5liu8.png)

```bash
#返回函数
def count():
    fs=[]
    for i in range(1,4):
        def f():
            return i*i
        fs.append(f)
    return fs
f1,f2,f3=count()
print(f1(),f2(),f3())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021103727-wtd0kdc.png)

返回一个函数时，牢记该函数并未执行，返回函数中不要引用任何可能会变化的变量。

## lambda（）匿名函数

lambda关键字 函数参数：函数表达式

传入函数时，有些时候，不需要显式地定义函数

Python对匿名函数的支持有限，只有一些简单的情况下可以使用匿名函数。

```bash
lambda x:x*x
#等价于
def f(x):
   return x*x
```

关键字 `lambda`表示匿名函数，冒号前面的 `x`表示函数参数，只能一个表达式

不用写 `return`，返回值就是该表达式的结果。

匿名函数也是一个函数对象

```bash
f=lamdba x:x*x
```

判断奇数函数

原函数：

```bash
def is_odd(n):
    return n % 2 == 1

L = list(filter(is_odd, range(1, 20)))
```

采用匿名函数修改

```bash
l=list(filter(lambda x:x%2==1,range(1,20)))
print(l)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021143505-wbqh836.png)

## 装饰器 Decorator

### 本质上，装饰器就是一个返回函数的高阶函数

@log 等价于

```bash
now = log(now)
```

由于函数也是一个对象，而且函数对象可以被赋值给变量，

所以，通过变量也能调用该函数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022101101-ncgju0i.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022101111-tgdwt0q.png)

```bash
def log(func):
    def wrapper(*args,**kwargs):
        print('call %s'% func.__name__)
        return func(*args,**kwargs)
    return wrapper()
#func为参数所以是高阶函数
#return 函数所以是返回函数，
#没有调用父函数中参数，所以不是闭包
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022110733-h27x1zh.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022110058-zyo7xpn.png)

场景注意：

无@装饰器时函数不调用，需要参数才调用

当@时会直接调用装饰器定义函数然后执行函数，不用调用函数

三层时，传入参数

```bash
def log1(text):
    def decorator(func):
        def wapper(*args,**kw):
            print('%s %s'%(text,func.__name__))
            return func(*args,**kw)
        return wapper
    return decorator
@log1('ruan')
def now3():
    print("hhh")
now3()
```

相当于在返回高阶函数上还有一个函数，所以返回时应该还要调用一次

## @wraps 常用装饰器

当装饰器是个闭包时，装饰器调用变量会改变增加@wraps后装饰器内的变量不变

装饰器在装饰一个函数时,，原函数就成了一个新的函数,也

就是说其属性会发生变化,所以为了 **不改变原函数的属性** ,

我们会调用functools中的wraps装饰器来保证原函数的属性不变

#### 不加wraps时

```bash
  @wraps(func)
```

```bash
from functools import wraps
def wrap(func):
   
    def b():
        'b'
        print('decorator:',b.__name__)
        print('funname',func.__name__)
        func()
    return b
@wrap
def a():
    'a'
    print('name',a.__name__)
a()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022115935-kgsz7b2.png)

加装饰器wraps时

```bash
from functools import wraps
def wrap(func):
    @wraps(func)
    def b():
        'b'
        print('decorator:',b.__name__)
        print('funname',func.__name__)
        func()
    return b
@wrap
def a():
    'a'
    print('name',a.__name__)
a()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022115950-2j3i7ht.png)

闭包的概念：调用父函数中的变量的函数，为了保证数据安全。变量作用域只在函数内部，可在闭包中操作数据。

装饰器返回为什么是函数名（函数内存地址）而不直接执行函数?

当有参数传入时，可直接与调用的函数中的值传入参数执行。

（）是运算符f()与f.__call__()等价：将f对象变成变成可调用的对象

## 偏函数（functools模块）

属于functools模块

### 作用：

通过设定参数的默认值，降低函数调用的参数

`int()`函数默认按十进制转换

print(int('100',base=8))

经常调用于是重写一个函数int2

```bash
def int2(x, base=8):
    print(int(x, base))
    return int(x, base)
print(int2('2334'))
```

采用偏函数

```bash
import functools
int3=functools.partial(int,base=8)
print(int3('46'))
print(int())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028103219-mdbldp6.png)

functools.partial的作用是将函数的特定参数固定住（设定为默认值）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028103645-7po81oc.png)

创建偏函数的时候也可以接收，函数对象，*args，**kw

## 模块

python包：作用区分相同名称的模块

模块相当于一个py文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028105055-2xv0z2i.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028105133-tkzgcka.png)

## 作用域

仅仅在模块内部使用。在Python中，是通过 `_`前缀来实现的。

### pubilc公开

正常的函数和变量名是公开的（public）

### private非公开_,__

_xxx和__xxx这样的函数或变量就是非公开的（private）

## 安装第三方模块pip

pip install 模块名

### 模块搜索路径

```bash
import sys
print(sys.path)
```

两种方式：

1. 添加搜索路径
   ```bash
    import sys
   sys.path.append('/Users/michael/my_py_scripts')
   ```
2. 设置环境变量

第二种方法是设置环境变量 `PYTHONPATH`

## 面向对象编程

面向对象编程——Object Oriented Programming，简称OOP，是一种程序设计思想

对象作为程序的基本单元，

一个对象包含了数据和操作数据的函数

数据封装、继承和多态是面向对象的三大特点

## 类和实例

面向对象最重要的概念就是类（Class）和实例（Instance）

类是抽象出来的模板

实例是根据类创建出的对象，每个对象可能有属性和方法

定义类是通过 `class`关键字，类名通常是大写开头的单词

```bash
class Student(object):
    pass
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028113324-1nch2o5.png)

！！！在类中定义函数有一点不同，定义佛如方法第一个参数永远是实例变量本身self

仍然可以用默认参数、可变参数、关键字参数和命名关键字参数

## 数据封装

```bash
class Student(object):
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def get_grade(self):
        if self.score >= 90:
            return 'A'
        elif self.score >= 60:
            return 'B'
        else:
            return 'C'
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028113713-vhhvowi.png)

## 访问限制

### 作用：

**确保了外部代码不能随意修改对象内部的状态**

实例的变量名如果以 `__`开头，就变成了一个私有变量（private）

外部无法访问_name

```bash
class Student(object):
    def __init__(self,name,age):
        self._name=name
        self.age=age
    def print_name(self):
        print(self._name)
        return self.age,self._name
a=Student('ruan',23)
h=a.print_name()
print(h)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028114732-awu2k2m.png)

若是要获取，修改变量增加get，set方式即可

```bash
class Student(object):
    def __init__(self,name,age):
        self._name=name
        self.age=age 
    def get_name(self):
        return self.name
    def set_name(self,name):
        self._name=name
```

Python本身没有任何机制阻止你干坏事，一切全靠自觉。

类外部无法访问

## 继承和多态

### 继承

#### 多态

在继承关系中，如果一个实例的数据类型是某个子类，那它的数据类型也可以被看做是父类。

比如：动物是父类，狗和鱼是子类；鱼是鱼类，鱼是动物都成立。

判断一个变量是否是某个类型可以用 `isinstance()`判断

### 鸭子类型

并不要求严格的继承体，一个对象只要“看起来像鸭子，走起路来像鸭子”，那它就可以被看做是鸭子。

## 获取对象信息

### type（）判断对象类型

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211102183643-gwgjuho.png)

### isinstance()对于继承关系，判断class的类型

### dir（）获取对象的所有属性和方法

#### len（）对象长度

#### lower（）返回小写的字符串

#### getattr（）获取属性a

#### setattr（）设置属性a

#### hasattr（obj,'a'）判断是否有属性a

```bash
getattr(obj, 'z', 404) # 获取属性'z'，如果不存在，返回默认值404
404
```

## 实例属性和类属性

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211102184822-83nvy25.png)

```bash
 class Student(object):
    name='ruan'
   
h=Student()
h.name='hhh'

```

类中的name是类属性，

创建h类对象即实例后赋值的是实例属性name，但由于实例对象的优先级比类属性高，会屏蔽类中的name属性，即h.name的值为hhh

### 总结：

1. 实例属性属于各个实例所有，互不干扰；
2. 类属性属于类所有，所有实例共享一个属性；
3. 不要对实例属性和类属性使用相同的名字，否则将产生难以发现的错误

# 面向对象高级编程

数据封装、继承和多态只是面向对象程序设计中最基础的3个概念

多重继承、定制类、元类

# _slots_使用

可以给创建的实例绑定属性和方法

给一个实例绑定的方法对另外一个实例对象是不起作用的

```bash
class A:
    def run(self):
        print("i im ferther runing....")
sun1=A()
#给实例sun1设置name属性
sun1.name='i im name'
#创建实例对象2
sun2=A()
#实例对象sun1的属性和sun2无关，即sun2没有name属性
#给实例sun1绑定方法，方法和属性同理
#定义方法
def setAll(self,num):
    print(num)
sun1.newfun=MethodType(setAll, sun1)
sun1.newfun(37)
#若所有实例都需要绑定方法则给类绑定方法
A.setAll=setAll
#给类绑定方法后，所有创建的实例的均可调用
```

```
def set_age(self, age): # 定义一个函数作为实例方法
...     self.age = age
...
>>> from types import MethodType
>>> s.set_age = MethodType(set_age, s) # 给实例绑定一个方法
>>> s.set_age(25) # 调用实例方法
```

## 限制实例属性，定义一个特殊的 `__slots__`变量

```python
class Student(object):
    __slots__ = ('name', 'age') # 用tuple定义允许绑定的属性名称
s=Student()
s.name='ruan'
s.firstname='i im firstname'
#输出的时候firstname的属性会报错，
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'firstaname'
```

### 注意：

_slots_使用时要注意，定义的属性只在当前的类的实例中，对于继承的子类是不起作用的

```python
class People(object):
    __slots__ = ('name','age')
    def run(self):
        print('i im run people......')

class Teacher(People):
    def say(self):
        print('i im teacher....')
t=Teacher()
t.tall='shouhua'
print(t.tall)
p=People()
p.tall('shouhuap')
print(p.tall)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103140608-7ezqmvs.png)

只限制父类People的属性，而子类Teacher中不限制

## @property

在绑定属性时，如果我们直接把属性暴露出去,导致可以随意更改.通过get，set来获取更改属性值。

在python中直接调用装饰器将一个方法变成属性调用

```python
class Student(object):
    @property
    #使用get方法是调用装饰器@peoperty，
    # 同时自动创建了另一个装饰器@属性.setter
    def score(self):
        return self.score
    @score.setter
    def score(self,value):
        self._score=value
```

## 总结：

-权限限制只对类对象实际起作用，想要达到方法和属性强制访问权限，需要使用@property装饰器进行get，set方法

属性名与方法名一定要区分开，不然会进入死循环（self._age，def age()）
实例化的对象使用属性时，不是调用属性（meizi._age），而是用的方法名（meizi.age）
@property其实就是实现了getter功能； @xxx.setter实现的是setter功能；还有一个 @xxx.deleter实现删除功能
定义方法的时候 @property必须在 @xxx.setter之前，且二者修饰的方法名相同（age()）
如果只实现了 @property（而没有实现@xxx.setter），那么该属性为 只读属性

```python
#请利用@property给一个Screen对象加上width和height属性，
# 以及一个只读属性resolution：
class Screen(object):
    __slots__ = ('_width','_height','_resolution')

    @property
    def width(self):
        return self._width

    # 方法名称和实例变量均为width:
    @width.setter
    def width(self,widthValue):
        self._width=widthValue

    @property
    def height(self):
        return self._height

    @width.setter
    def height(self, height):
        self._height = height

    @property
    def resolution(self):
        return self._width * self._height
s=Screen()
s.width=23
s.height=12

print(s.resolution)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103150647-dge6za2.png)

```python
s.score = 60 # OK，实际转化为s.set_score(60)
s.score # OK，实际转化为s.get_score()
```

要特别注意：属性的方法名不要和实例变量重名。例如，以下的代码是错误的：

```
class Student(object):

    # 方法名称和实例变量均为birth:
    @property
    def birth(self):
        return self.birth
```

出现递归调用错误

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103151046-5z499ew.png)

之前的例子中width和_width不同所以可以运行

## 多重继承

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103151750-dvwa7qb.png)

python可以支持多继承，即一个子类可以继承多个父类；但java是单继承，只能有一个父类

Tercher（Name，study，teach）即Teacher可以继承多个父类

### MixIn

在设计类的继承关系时，通常，主线都是单一继承下来的，例如，`Teacher`继承自Name。但是，如果需要“混入”额外的功能，通过多重继承就可以实现，比如Teacher除了继承自 `Name`外，再同时继承 `Teach`。这种设计通常称之为MixIn

Python自带了 `TCPServer`和 `UDPServer`这两类网络服务，而要同时服务多个用户就必须使用多进程或多线程模型，这两种模型由 `ForkingMixIn`和 `ThreadingMixIn`提供。

### 多继承

多重继承这个名词一般用来形容继承链条可以很长，多个层次。

### 多重继承

**多继承则指一个类可以有多个基类，相反则是单继承**。任何面向对象编程语言都支持多重继承，但像java这种只能通过接口实现有限程度的多继承

问：多继承 如果多个类有共同得方法名 怎么区分是调得哪个类🤡

答：调用该方法的时候，会调用第一顺位继承父类的方法

### 总结：

1. Python允许使用多重继承，因此，MixIn就是一种常见的设计
2. 只允许单一继承的语言（如Java）不能使用MixIn的设计

## 定制类

Python的class中还有__xxx__有特殊用途的函数，可以帮助我们定制类

### __str__()回用户看到的字符串

将对象 `<__main__.Student object at 0x109afb190>`变成易读的数据

只在调用print时会调用__str__，交互界面时还是现实上方不易读的对象内容，此时用

### __repr__()返回程序开发者看到的字符串

`__str__()`返回用户看到的字符串，而 `__repr__()`返回程序开发者看到的字符串，

也就是说，`__repr__()`是为调试服务的

简写

```python
def __str__(self):
        return 'xxx object (name=%s)' % self.name
__repr__ = __str__
```

### ___iter__()返回一个迭代对象

需要用到for in迭代，需要转化为迭代对象

该方法返回一个迭代对象，然后，Python的for循环就会不断调用该迭代对象的 `__next__()`方法拿到循环的下一个值，直到遇到 `StopIteration`错误时退出循环

例子：

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
a=Fib()
for i in a:
    print(i)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155046-1xs33i9.png)

### __**getitem**__()表现得像list那样按照下标取出元素

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
    def __getitem__(self, item):
        a,b=1,1
        for i in range(item):
            a,b=b,a+b
        return a
a=Fib()
print(a[3])

```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155122-fo5pjxz.png)

以上是传入int，切片功能实现，isinstance判断类型

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
    def __getitem__(self, item):
        if isinstance(item,int):
            a, b = 1, 1
            for i in range(item):
                a, b = b, a + b
            return a
        if isinstance(item,slice):
            start=item.start
            stop=item.stop
            if start is None:
                start=0
            a,b=1,1
            L=[]
            for x in range(stop):
                L.append(a)
                a,b=b,a+b
        return L

a=Fib()
print(a[3:12])
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155838-wdwjies.png)

### __getattr__()动态返回一个属性

调用类属性或方法时，先在__init__()获取后，再从__getattr__()获取，获取不到才报错

### __call__()直接调用实例本身

与直接调用这个函数一样

```python
class People(object):
    def __init__(self,name):
        self.name=name
    def __call__(self, *args, **kwargs):
        print('i im call %s'% self.name)

p=People('ruan')
p()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104150832-d8wkn0m.png)

## 使用枚举类

枚举类：在某些情况下，一个类的 实例对象 的**数量**是 **有限且固定** 的，如季节类，它的实例对象只有春、夏、秋、冬。 在Java中像这种对象实例有限且固定的类被称为枚举类；这样的枚举类型定义一个class类型，然后，每个常量都是class的一个唯一实例。Python提供了 `Enum`类来实现这个功能。

```python
from enum import Enum
M=Enum('a',('sun1','sun2','sun3','sun4'))
print(M.sun1)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104151622-x7yqw9j.png)

自定义枚举类

```python
from enum import Enum,unique
@unique
class Week(Enum):
    sun1=1
    sun2=2
    sun3=3
day2=Week.sun2
print(day2)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104152125-y6nm9vn.png)

```python
from enum import Enum,unique
@unique
class Gender(Enum):
    Male=0
    Female=1
class Student(object):
    def __init__(self,name,gender):
        self.name=name
        self.gender=gender

# 测试:
bart = Student('Bart', Gender.Male)
if bart.gender == Gender.Male:
    print('测试通过!')
else:
    print('测试失败!')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104152731-wmdziil.png)

## 使用元类[创建类]

实例对象是类创建

类是元类创建

创建类的方式

### 方式一：type（）

`type()`函数既可以返回一个对象的类型，又可以创建出新的类型，比如，我们可以通过 `type()`函数创建出 `Hello`类

```python
from class1104 import *
h=Hello()
print(type(h))
print(type(Hello))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104153538-6iulybe.png)

```python
 Hello = type('Hello', (object,), dict(hello=fn))
```

要创建一个class对象，`type()`函数依次传入3个参数：

1. class的名称；
2. 继承的父类集合，注意Python支持多重继承，如果只有一个父类，别忘了tuple的单元素写法；
3. class的方法名称与函数绑定，这里我们把函数 `fn`绑定到方法名 `hello`上

### 方式二：元类metaclass

先定义metaclass，然后创建类。

先定义类，然后创建实例。

~~metaclass是Python面向对象里最难理解，也是最难使用的魔术代码。~~

按照默认习惯，metaclass的类名总是以Metaclass结尾，以便清楚地表示这是一个metaclass

```python
# metaclass采用type创建类 ，metaclass是类的模板，所以必须从`type`类型派生
class ListMetaclass(type):
    def __new__(cls, name,bases,attrs):
        attrs['add']=lambda self, value:self.append(value)
        return type.__new__(cls,name,bases,attrs)

class MyList(list,metaclass=ListMetaclass):
    pass
mylist=MyList()
mylist.add(1)
print(mylist)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104155010-cbldtfp.png)

`__new__()`方法接收到的参数依次是：

1. 当前准备创建的类的对象；
2. 类的名字；
3. 类继承的父类集合；
4. 类的方法集合

### 应用场景

ORM全称“Object Relational Mapping”，即对象-关系映射，就是把关系数据库的一行映射为一个对象，也就是一个类对应一个表，这样，写代码更简单，不用直接操作SQL语句。

要编写一个ORM框架，所有的类都只能动态定义，因为只有使用者才能根据表的结构定义出对应的类来。

## 错误处理try

```python
try:
    print('try...')
    r = 10 / 0
    print('result:', r)
except ValueError as e:
    print('ValueError:', e)
except ZeroDivisionError as e:
    print('ZeroDivisionError:', e)e)
finally:
    print('finally...')
print('END')
```

Python的错误其实也是class，所有的错误类型都继承自 `BaseException`

`UnicodeError`是 `ValueError`的子类🤡

[Built-in Exceptions — Python 3.10.0 documentation](https://docs.python.org/3/library/exceptions.html#exception-hierarchy)

## 调用栈

让Python解释器来打印出错误堆栈

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104162726-fird23x.png)

## 记录错误logging

可将logging生成一个txt方便查看

```python
 try:
        xxx
    except Exception as e:
        logging.exception(e)
```

### 抛出错误raise

```python
 except ValueError as e:
        print('ValueError!')
        raise
```

在 `bar()`函数中，我们明明已经捕获了错误，但是，打印一个 `ValueError!`后，又把错误通过 `raise`语句抛出去了，这不有病么？

其实这种错误处理方式不但没病，而且相当常见。捕获错误目的只是记录一下，便于后续追踪。但是，由于当前函数不知道应该怎么处理该错误，所以，最恰当的方式是继续往上抛，让顶层调用者去处理。

## 调试方法

### 1. print（）

### 2. 断言assert

```python
 assert n != 0, 'n is zero!'
```

`assert`的意思是，表达式 `n != 0`应该是 `True`，否则，根据程序运行的逻辑，后面的代码肯定会出错。

采用断言的好处：

启动Python解释器时可以用 `-O`参数来关闭 `assert`：

```python
$ python -O err.py
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104164034-js5sidi.png)

关闭后，你可以把所有的 `assert`语句当成 `pass`来看

### 3. logging

```python
import logging
s = '0'
n = int(s)
logging.info('n = %d' % n)
print(10 / n)
```

### 4.pbd单步执行

启动Python的调试器pdb，让程序以单步方式运行，可以随时查看运行状态。

```python
python -m pdb xxx.py
(Pbd) 1#查看第一行代码，单步执行第一行代码
```

### 5. pdb.set_trace()

这个方法也是用pdb，但是不需要单步执行，我们只需要 `import pdb`，然后，在可能出错的地方放一个 `pdb.set_trace()`，就可以设置一个断点：

```python
import pdb

s = '0'
n = int(s)
pdb.set_trace() # 运行到这里会自动暂停
print(10 / n)
```

可以用命令 `p`查看变量，或者用命令 `c`继续运行：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104164634-anjnpuu.png)

### 6.IDE工具

vscode,pycharm....

## 单元测试

单元测试是用来对一个模块、一个函数或者一个类来进行正确性检验的测试工作。

## 文档测试

doctest非常有用，不但可以用来测试，还可以直接作为示例代码。通过某些文档生成工具，就可以自动把包含doctest的注释提取出来。用户看文档的时候，同时也看到了doctest。

Python内置的“文档测试”（doctest）模块可以直接提取注释中的代码并执行测试.

```python
class Dict(dict):
    """"
      这一段就是文档测试
       Simple dict but also support access as x.y style.

       >>> d1 = Dict()
       >>> d1['x'] = 100
       >>> d1.x
       100
       >>> d1.y = 200
       >>> d1['y']
       200
       >>> d2 = Dict(a=1, b=2, c='3')
       >>> d2.c
       '3'
       >>> d2['empty']
       Traceback (most recent call last):
           ...
       KeyError: 'empty'
       >>> d2.empty
       Traceback (most recent call last):
           ...
       AttributeError: 'Dict' object has no attribute 'empty'
       """

    def __init__(self, **kw):
        super(Dict, self).__init__(**kw)

    def __getattr__(self, key):
        try:
            return self[key]
        except KeyError:
            raise AttributeError(r"'Dict' object has no attribute '%s'" % key)

    def __setattr__(self, key, value):
        self[key] = value

if __name__ == '__main__':
    import doctest
    doctest.testmod()
```

将其中一个函数注释，运行让它报错

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108110503-erlvnk1.png)

## IO编程

程序和运行时的数据在内存中驻留

涉及到数据交换的地方，通常是磁盘、网络等，就需要IO接口

通常，程序完成IO操作会有Input和Output两个数据流

Stream（流）是一个很重要的概念，可以把流想象成一个水管，数据就是水管里的水，但是只能单向流动。

在IO编程中，就存在**速度严重不匹配的问题**。举个例子来说，比如要把100M的数据写入磁盘，CPU输出100M的数据只需要0.01秒，可是磁盘要接收这100M数据可能需要10秒，怎么办呢？有两种办法：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108111749-yobbduz.png)

## 同步IO

第一种是CPU等着，也就是程序暂停执行后续代码，等100M的数据在10秒后写入磁盘，再接着往下执行，这种模式称为同步IO；

## 异步IO

另一种方法是CPU不等待，只是告诉磁盘，“您老慢慢写，不着急，我接着干别的事去了”，于是，后续代码可以立刻接着执行，这种模式称为异步IO。

如果是服务员跑过来找到你，这是回调模式，如果服务员发短信通知你，你就得不停地检查手机，这是轮询模式。总之，异步IO的复杂度远远高于同步IO。

## 文件读写

### 读文件open（）

传入文件名，标示符

参数：'rb' 二进制

encoding='gbk'字符编码

```python
f = open('/Users/michael/test.txt', 'r')
```

### read()一次读取全部内容

```python
 f.read()
'Hello, world!'
```

### f.close（）关闭文件

简化方法

### with open('filepath', 'r') as f:    print(f.read())

Python引入了 `with`语句来自动帮我们调用 `close()`方法，并且不必调用 `f.close()`方法

```python
with open('/path/to/file', 'r') as f:
    print(f.read())
```

如果文件很小，`read()`一次性读取最方便；

如果不能确定文件大小，反复调用 `read(size)`比较保险；

如果是配置文件，调用 `readlines()`最方便

```python
for line in f.readlines():
    print(line.strip()) # 把末尾的'\n'删掉
```

file和缓存时=是file-like Object对象，不要求从特定类继承，只要写个 `read()`方法就行

### f.write()写文件

```python
f = open('/Users/michael/test.txt', 'w')
f.write('Hello, world!')
f.close()
```

或

```python
with open('/Users/michael/test.txt', 'w') as f:
    f.write('Hello, world!')
```

使用 `with`语句操作文件IO是个好习惯

## StringIO和BytesIO

### StringIO

StringIO顾名思义就是在内存中读写str

```python
 from io import StringIO
 f = StringIO()
f.write('hello')
```

`getvalue()`方法用于获得写入后的str

```python
 from io import StringIO
>>> f = StringIO('Hello!\nHi!\nGoodbye!')
>>> while True:
...     s = f.readline()
...     if s == '':
...         break
...     print(s.strip())
```

### BytesIO

操作二进制数据，就需要使用BytesIO

```python
>>> from io import BytesIO
>>> f = BytesIO()
>>> f.write('中文'.encode('utf-8'))
6
>>> print(f.getvalue())
b'\xe4\xb8\xad\xe6\x96\x87'
```

## os模块

### os.name操作系统类型

### os.uname()详细系统信息

### os.enciron环境变量

要获取某个环境变量的值，可以调用 `os.environ.get('key')`

```python
# 查看当前目录的绝对路径:
>>> os.path.abspath('.')
'/Users/michael'
# 在某个目录下创建一个新目录，首先把新目录的完整路径表示出来:
>>> os.path.join('/Users/michael', 'testdir')
'/Users/michael/testdir'
# 然后创建一个目录:
>>> os.mkdir('/Users/michael/testdir')
# 删掉一个目录:
>>> os.rmdir('/Users/michael/testdir')
```

通过 `os.path.join()`函数，这样可以正确处理不同操作系统的路径分隔符

### `os.path.join(`)连接路径

### `os.path.split()`拆分路径

### `os.path.splitext()` 文件扩展名

```python
# 对文件重命名:
>>> os.rename('test.txt', 'test.py')
# 删掉文件:
>>> os.remove('test.py')
```

`shutil`模块提供了 `copyfile()`的函数，它们可以看做是 `os`模块的补充

最后看看如何利用Python的特性来过滤文件。比如我们要列出当前目录下的所有目录，只需要一行代码：

```
>>> [x for x in os.listdir('.') if os.path.isdir(x)]
['.lein', '.local', '.m2', '.npm', '.ssh', '.Trash', '.vim', 'Applications', 'Desktop', ...]
```

要列出所有的 `.py`文件，也只需一行代码：

```
>>> [x for x in os.listdir('.') if os.path.isfile(x) and os.path.splitext(x)[1]=='.py']
['apis.py', 'config.py', 'models.py', 'pymonitor.py', 'test_db.py', 'urls.py', 'wsgiapp.py']
```

## 序列化pickle模块

变量从内存中变成可存储或传输的过程称之为序列化,Python中叫pickling

变量内容从序列化的对象重新读到内存里称之为反序列化，即unpickling

### pickle.dumps()对象-》字节[序列化]

`pickle.dumps()`方法把任意对象序列化成一个 `bytes`

`pickle.dumps()`方法把任意对象序列化成一个 `bytes`,并写入文件中

```python
import pickle
d=dict(name='ruan',age=34,freand='woman')
# print(pickle.dumps(d))
f = open('timezone.txt', 'wb')
pickle.dump(d, f)
f.close()
```

### pickle.load()字节-》对象【反序列化】

```python
import pickle
f=open(r'C:\Users\yangs\PycharmProjects\python_study\fun\timezone.txt','rb')
d=pickle.load(f)
f.close()
print(d)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108132946-rtt8k8p.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108133035-b8gyft4.png)

## json模块

`json`模块的 `dumps()`和 `loads()`函数是定义得非常好的接口的典范。

#### json.dumps(python对象)python对象-》json对象

`dumps()`方法返回一个 `str`，内容就是标准的JSON

#### json.loads(json对象)json对象-》python对象

`json.``dump`(obj, fp, *, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw**)**

### 类变为字典并序列化

```python
json.dumps(s, default=lambda obj: obj.__dict__)
```

## 进程和线程

Python的标准库提供了两个模块：`_thread`和 `threading`，`_thread`是低级模块，`threading`是高级模块

**线程是最小的执行单元，而进程由至少一个线程组成**

操作系统轮流让各个任务交替执行

真正的并行执行多任务只能在多核CPU上实现

对于操作系统来说，一个任务就是一个进程（Process），比如打开一个浏览器就是启动一个浏览器进程

Word，它可以同时进行打字、拼写检查、打印等事情。在一个进程内部，要同时干多件事，就需要同时运行多个“子任务”，我们把进程内的这些“子任务”称为线程（Thread）

* 多进程模式；
* 多线程模式；
* 多进程+多线程模式。

## 多进程

Unix/Linux操作系统提供了一个 `fork()`系统调用，普通的函数调用，调用一次，返回一次，但是 `fork()`调用一次，返回两次，因为操作系统自动把当前进程（称为父进程）复制了一份（称为子进程），然后，分别在父进程和子进程内返回。

创建子进程

```python
from multiprocessing import Process
import os
def run_pro(name):
    print('开始运行子进程%s，%s'%(name,os.getpid()))

if __name__ == '__main__':
    print('开始运行进程%s' % (os.getpid()))
    p=Process(target=run_pro,args=('test',))
    p.start()
    p.join()
    print('end')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211111131512-zqm80if.png)

### 启动大量子进程pool

进程池

```python
import time, threading

# 新线程执行的代码:
def loop():
    print('thread %s is running...' % threading.current_thread().name)
    n = 0
    while n < 5:
        n = n + 1
        print('thread %s >>> %s' % (threading.current_thread().name, n))
        time.sleep(1)
    print('thread %s ended.' % threading.current_thread().name)

print('thread %s is running...' % threading.current_thread().name)
t = threading.Thread(target=loop, name='LoopThread')
t.start()
t.join()
print('thread %s ended.' % threading.current_thread().name)
```

# 模块总结

## doctest文档测试

## os.path文件路径

## pickle序列化

## json

[使用dict和set - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/1016959663602400/1017104324028448)

用于学习记录，后期便于复习，参考链接

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102447-hmq8gs8.png)

python file

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102545-qqmxrgo.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102644-7ny4t2k.png)

调用脚本时会先载入pyhton解释器，然后运行脚本

rpm：软件管理包

操作符优先级：![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009104337-b66ot2k.png)

条件判断：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009104751-a27qfzb.png)

Python为我们提供了非常完善的基础代码库，覆盖了网络、文件、GUI、数据库、文本等大量内容，被形象地称作“内置电池（batteries included）”。用Python开发，许多功能不必从零编写，直接使用现成的即可。

语言定位：

Python的定位是“优雅”、“明确”、“简单”

Python是解释型语言

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211011172523-7k51l6e.png)

# python

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009110719-7urayjl.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009111236-gd1mcju.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009111303-l3bqira.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009113303-w7qziw5.png)

## 数据类型

### int 整型

long int长整型

int 整型

### float 浮点型

浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时

双精度浮点型 e

浮点型

### String 字符串

字符串是以单引号 `'`或双引号 `"`括起来的任意文本

字符串是以Unicode编码

对于单个字符的编码，Python提供了 `ord()`函数获取字符的整数表示，`chr()`函数把编码转换为对应的字符：

### Bool布尔

True

Flase

### None 空值

None，`None`不能理解为 `0`，因为 `0`是有意义的,

Null无意义

.

<iframe src="http://127.0.0.1:6806/widgets/brython-editor" data-src="http://127.0.0.1:6806/widgets/brython-editor" data-subtype="widget" border="0" frameborder="no" framespacing="0" allowfullscreen="true" style="width: 1341px; height: 276px;"></iframe>

### 变量

变量的概念基本上和初中代数的方程变量是一致的，

变量不仅可以是数字，还可以是任意数据类型。

变量名必须是大小写英文、数字和 `_`的组合，且不能用数字开头，字母或下划线开头

```python
#变量类型
a=1
b='我是变量'
c=True
d=12.2e3
print(a,b,c,d)
print(type(a),type(b),type(c),type(d))

```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009134601-1cuacaj.png)

int a=1 静态语言 此时已经分配的int分区之后不能更改变量类型【不支持，Java】

a=3 动态语言，可以赋值成任意类型

#### 动态定义

#### 静态定义

```python
a = 'ABC'
b = a
a = 'XYZ'
print(b)
```

执行 `a = 'ABC'`，解释器创建了字符串 `'ABC'`和变量 `a`，并把 `a`指向 `'ABC'`：

![py-var-code-1](https://www.liaoxuefeng.com/files/attachments/923791878255456/0)

执行 `b = a`，解释器创建了变量 `b`，并把 `b`指向 `a`指向的字符串 `'ABC'`：

![py-var-code-2](https://www.liaoxuefeng.com/files/attachments/923792058613440/0)

执行 `a = 'XYZ'`，解释器创建了字符串'XYZ'，并把 `a`的指向改为 `'XYZ'`，但 `b`并没有更改：

![py-var-code-3](https://www.liaoxuefeng.com/files/attachments/923792191637760/0)

### 常量

所谓常量就是不能变的变量，通常用全部大写的变量名表示常量：

```python
PI = 3.14159265359
```

## list列表

list是一种有序的集合，可以随时添加和删除其中的元素。

```python
list=['a','b','c']
print(list)
print(len(list))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154856-r9s5yyu.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154907-bofhvvd.png)

### 切分

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155126-p31z8um.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155139-cpsoatf.png)

### append（）追加

str.append('a')

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155556-qrj4a63.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155606-dxihfwr.png)

### insert插入指定位置

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009162557-186v350.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009162609-u00z8m3.png)

### pop（）删除末尾元素

要删除指定位置的元素，用 `pop(i)`方法，其中 `i`是索引位置

替换元素直接赋值即可

列表可以嵌套

```python
 s = ['python', 'java', ['asp', 'php'], 'scheme']
```

类型可以不同

```python
L = ['Apple', 123, True]
```

### 切片

list[:-1]不包含最后一个元素

list[:]全部列表

list[::]全部列表

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161203-1e12zsd.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161212-0lrqjsm.png)

前10个数，每两个取一个

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161428-r6muafj.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161441-eoc8y55.png)

#### 列表生成

list（range（1，11））生成10个数1-10

```python
print([m+n for m in '123' for n in 'yza'])
```

```python
k=[1,1,23,45,56,[1,12,3,467,[2,4,4,3,22]]]
print([x for x in k if x==1 ])
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012190810-l1qtxiv.png)

## tuple元组

tuple一旦初始化就不能修改

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009163638-1vpldee.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009163652-xkas3o0.png)

但元组初始化后就不能进行更改了

```python
b=(1)
#定义的不是tuple，是1这个数！
# 这是因为括号()既可以表示tuple，又可以表示数学公式中的小括号，
# 这就产生了歧义，因此，Python规定，
# 这种情况下，按小括号进行计算，计算结果自然是1
print(b)
print(type(b))
c=(1,)
print(c)
print(type(c))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009164221-xl1husx.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009164244-780v78f.png)

## dict字典

其他语言叫map，使用键-值（key-value）存储，具有极快的查找速度。dict的key必须是**不可变对象**。key计算位置的算法称为哈希算法（Hash）。

### 定义

```python
d={'name':'ruanyifen','age':60,'happy':'write'}
d['add']='Im add'
d['name']='fix'
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135019-kqmsrcg.png)

### 取value

#### dict['key']

#### 'key' in dict

#### dict.get('key')

```python
print(type(d))
print(d['name'])
print('name' in d)#方法一判断是否有这个主键在字典d中
print(d.get('name'))#方法二 取
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135119-sniqpw0.png)

### dict.pop('key')删除一个key

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135429-m36ygpu.png)

### dict.keys返回字典中所有key列表

### dict.update()将a字典新key，value内容加入b字典中

```bash
dicta={"name":'ruan','age':20}
dictb={"name":'ruan2','age':40,'add':'w shi add'}
dictb.update(dicta)
print(dictb)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115242-qazr588.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115348-bb0l147.png)

#### 内建函数使用

type（）

cmp（）

len（）

hash（）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114202-rdvz2pt.png)

内建cmp（）函数比较两个dict时，先比较长度，后比值，输出1或-1

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114401-h4f1qop.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114644-qffksiw.png)

### dict特点

dict有以下几个特点：

1. 查找和插入的速度极快，不会随着key的增加而变慢；
2. 需要占用大量的内存，内存浪费多。

而list相反：

1. 查找和插入的时间随着元素的增加而增加；
2. 占用空间小，浪费内存很少。
   ![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115427-fu3s2zu.png)
   ![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115451-utxi9ct.png)

## set集合

也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

重复元素在set中自动被过滤

### 定义

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135934-u0n1j77.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135953-sqa88s1.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140114-5azj1sa.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140127-ledkv1s.png)

### set.add('key')添加元素

但重复元素不添加，自动去重

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140336-dwf2vgw.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140344-dzsshz2.png)

### set.remove('key')删除元素

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140511-5f9cwm4.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140517-f6iolow.png)

set可以看成数学意义上的无序和无重复元素的集合，

因此，两个set可以做数学意义上的交集、并集等操作：

### & 两个set交集

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140903-1l3we66.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140912-8itf6ek.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022170721-h5hmgxr.png)

### |两个set并集

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140922-5bjlj5g.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140933-edbys90.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022171729-b4k8xhd.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115701-3dt5x4j.png)

### map()的显示

打印map对象可以看到map对象返回的是一个地址，不是真实的数据

```python
print(list(map对象))
print([it for it in map对象])
```

## 数据类型转换

### int（）

### float（）

### str（）

### bool（）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142636-iblnu9y.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142645-gb2u1fg.png)

## 条件判断

### if

if else

```python
a=100
if a>=0:
    print(a)
else:
    print(-a)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165335-jr8xtfq.png)

if

```python
if True:
    print('True')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165309-ymhiihv.png)

if elif elif else

```python
name='zhangsan'
if name=='zhangsan':
    print('我是',name)
elif name=='lisi':
    print('我是', name)
elif name=='wangwu':
    print('我是', name)
else:
    print('我谁的不是')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165511-spws02g.png)

## input（）输入输出

input()返回的数据类型是str

print（）

## 循环 迭代

list，tuple，dict都可循环

Python的 `for`循环本质上就是通过不断调用 `next()`函数实现的,计算是惰性的

dict循环按照value时：for value in dict.values

```python
for value in d.values():
    print(value)
```

### for in

```python
sum=0
for i in range(1,100):
    sum=sum+i
print(sum)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172805-wrb6kr2.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172805-wrb6kr2.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172821-rdyglwd.png)

### while

```python
sum2=0
k=0
while(k<100):
    sum2=sum2+k
    k=k+1
print(sum2)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172821-rdyglwd.png)

### break

如果要提前结束循环，可以用 `break`语句

### continue

通过 `continue`语句，跳过当前的这次循环，直接开始下一次循环

## 生成器

在Python中，这种一边循环一边计算的机制，称为生成器：generator。

包括生成器和带 `yield`的generator function。

```python
 g = (x * x for x in range(10))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012191035-5wbqtm5.png)

访问大文件

yield

## isinstance（）迭代器

直接作用于 `for`循环的对象统称为可迭代对象，都是迭代器 Iterable

`list`、`tuple`、`dict`、`set`、`str`

`list`、`dict`、`str`虽然是 `Iterable`，却不是 `Iterator`。

`list`、`dict`、`str`等 `Iterable`变成 `Iterator`可以使用**iter()**函数

以直接作用于 `for`循环的数据类型有以下几种：

一类是集合数据类型，如 `list`、`tuple`、`dict`、`set`、`str`等；

一类是 `generator`，包括生成器和带 `yield`的generator function。

可以使用**isinstance()**判断一个对象是否是 `Iterable`对象__iter__：

迭代对象

判断是不是可以迭代，用Iterable

```python
from collections import Iterable
isinstance({}, Iterable) --> True
isinstance((), Iterable) --> True
isinstance(100, Iterable) --> False
```

判断是不是迭代器，用Iterator

```python
from collections import Iterator
isinstance({}, Iterator)  --> False
isinstance((), Iterator) --> False
isinstance( (x for x in range(10)), Iterator)  --> True
```

Python中 list，truple，str，dict这些都可以被迭代，但他们并不是迭代器，为什么：：因为和迭代器相比有一个很大的不同，list/truple/map/dict这些数据的大小是确定的，也就是说有多少事可知的。但迭代器不是，迭代器不知道要执行多少次，所以可以理解为不知道有多少个元素，每调用一次next()，就会往下走一步，是惰性的。

## 函数

抽象

将函数抽象成一个函数名称，不看内部结构直接调用方法

返回类型 函数名（输入参数）：

函数体

### 调用函数

要调用一个函数，需要知道函数的名称和参数

绝对值abs

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142010-d503sa9.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142024-cscdoiu.png)

### 定义函数

```python
def myabs(x):
    if x>0:
        return x
    if x<0:
        return -x
print(myabs(-100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144653-0ds9bc4.png)

### 空函数

```python
def nufun():
    pass
```

`pass`可以用来作为占位符

### 函数 参数检查

```python
def my_init_abs(x):
    if not isinstance(x,(int,float)):
        raise TypeError('no no no')
    else:
        if x>0:
            print(x)
        if x<0:
            print(-x)
my_init_abs(-90)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144640-6xnfm9s.png)

### 可返回多个值，函数

```python
def return_much():
    a='返回'
    b='我也返回'
    c='我也要返回'
    return a,b,c
print(return_much())
print(type(return_much()))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144955-kyvotx4.png)

### 函数参数

***args是可变参数，args接收的是一个tuple；**

****kw是关键字参数，kw接收的是一个dict**。

`power(x)`函数，参数 `x`就是一个位置参数，可单个变量，list，set，tuple

`power(*x)`函数，可传入单个变量，list，set，tuple，可以传入任意个参数或0个参数

`power(**kw)`函数,字典dict

可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。

而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个**dict**.

`power(x, n)`，用来计算x^n^

`power(x, n)`函数有两个参数：`x`和 `n`

默认参数，此时age和city为默认参数，可传值改变也可不变【不用传值】

`power(L=None)`函数有None这个不变对象，可用list

```python
def enroll(name, gender, age=6, city='Beijing'):
    print('name:', name)
    print('gender:', gender)
    print('age:', age)
    print('city:', city)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012151610-9n1rxhq.png)

#### 必选参数

```python
def a1(x):
    return x
print(a1(2))
print(a1(12.1))
print(a1('ruan'))
print(a1(True))
print(a1([1,2,3]))
print(a1({1,2,3}))
print(a1({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012153014-r27ykfm.png)

#### =默认参数

```python
def a2(x=9):
    return x
print(a2())
print(a2(2))
print(a2(12.1))
print(a2('ruan'))
print(a2(True))
print(a2([1,2,3]))
print(a2({1,2,3}))
print(a2({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012153014-r27ykfm.png)

#### *可变参数

```python
def a3(*x):
    return x
print(a3())
print(a3(2))
print(a3(12.1))
print(a3('ruan'))
print(a3(True))
print(a3([1,2,3]))
print(a3({1,2,3}))
print(a3({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012154346-2eahz0b.png)

#### **关键字参数

```python
def a3(**kw):
    return kw
print(a3())
print(a3(kw=2))
print(a3(kw=12.1))
print(a3(kw='ruan'))
print(a3(kw=True))
print(a3(kw=[1,2,3]))
print(type(a3(kw=[1,2,3])))
print(a3(kw={1,2,3}))
print(type(a3(kw={1,2,3})))
print(a3(kw={"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012154409-tp9u2z5.png)

### 递归函数

在函数内部，可以调用其他函数。

一个函数在**内部调用自身本身**，这个函数就是**递归函数**。

使用递归函数需要**注意防止栈溢出**

```python
#递归函数
def funmyself(x):
    if x>1:
        return x+funmyself(x-1)
    elif x==1:
        return 1
print(funmyself(3))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012155139-884p9as.png)

解决栈溢出方法：

**尾递归**优化，事实上尾递归和循环的效果是一样的

尾递归是指，在函数返回的时候，**调用自身**本身，并且，**return语句不能包含表达式**

```python
#尾递归
def funmyself2(n):
    return  funmyself2_it(n,1)

def  funmyself2_it(n,pro):
    if n==1:
        return pro
    else:
        return funmyself2(n-1)+n
print(funmyself2(100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012160333-tngb33o.png)

此时funmyself2是尾递归函数

## 转义字符 `\`

转义字符 `\`可以转义很多字符，比如

`\n`表示换行，

`\t`表示制表符，

字符 `\`本身也要转义，所以 `\\`表示的字符就是 `\`

Python还允许用 `r''`表示 `''`内部的字符串默认不转义

## 运算符and、or和not

运算优先级：not>or>and

## 除法 / //

```python
print(10/3)
print(10//3)
```

#### 除法一 / 浮点数

#### 除法二  //  地板除 整数

`/`除法计算结果是浮点数，即使是两个整数恰好整除，结果也是浮点数：

`//`，称为地板除，两个整数的除法仍然是整数：

## 取余 %

```python
print(10%1)
print(10%3)
print(4%7)
print(2%20)
#如果a%b a>b 则结果为a
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009141744-i2nxg58.png)

## 字符编码

`ASCII`编码

8个比特（bit）作为一个字节（byte）

一个字节能表示的最大的整数就是255（二进制11111111=十进制255）

两个字节可以表示的最大整数是 `65535`，4个字节可以表示的最大整数是 `4294967295`

大写字母 `A`的编码是 `65`，二进制的 `01000001`，小写字母 `z`的编码是 `122`

Unicode把所有语言都统一到一套编码里，这样就不会再有乱码问题

ASCII编码是1个字节，而Unicode编码通常是2个字节

**ASCll出现乱码问题引入Unicode编码存储空间多了一倍引入UTF-8编码**

utf-8：将**Unicode字符根据不同的数字大小编码成1-6个字节，常用的英文字母被编码成1个字节，汉字通常是3个字节，**

| 字符 | ASCII    | Unicode           | UTF-8                      |
| ---- | -------- | ----------------- | -------------------------- |
| A    | 01000001 | 00000000 01000001 | 01000001                   |
| 中   | x        | 01001110 00101101 | 11100100 10111000 10101101 |

在计算机内存中，统一使用Unicode编码，当需要保存到硬盘或者需要传输的时候，就转换为UTF-8编码。

用记事本编辑的时候，从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009142650-uopgqob.png)

浏览网页的时候，服务器会把动态生成的Unicode内容转换为UTF-8再传输到浏览器：

![web-utf-8](https://www.liaoxuefeng.com/files/attachments/923923759189600/0)

#### compile() 字符串编译为字节代码

#### 编码转化

#### ord('A') 字母转字符

#### chr(65) 字符转字母

```python
a=ord('A')
b=chr(65)
print(a,b)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009144810-rm45nsz.png)

#### b'str'转为字节类型bytes

`bytes`类型的数据用带 `b`前缀的单引号或双引号表示

```python
x = b'ABC'
```

要注意区分 `'ABC'`和 `b'ABC'`，前者是 `str`，后者虽然内容显示得和前者一样，但 `bytes`的每个字符都只占用一个字节。

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009145112-3dmegln.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150224-kn57ioe.png)

#### str.encode('ascii') `str` 变为 `bytes `

`ASCII`

`UTF-8`

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150118-wy36xea.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150204-81jvyjd.png)

#### str.decode('utf-8')`bytes`变为 `str`

```python
print(type(b'abc'))
print(b'abc'.decode('utf-8'))
print(type(b'abc'.decode('utf-8')))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150844-zvt6jkv.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150746-31uq63m.png)

len（str）计算字符数

函数计算的是 `str`的字符数，如果换成 `bytes`，`len()`函数就计算字节数

```python
print(len('abc'))
print(len(b'abc'))
print(len('中'))
print(len('中'.encode('utf-8')))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009151234-rhao6fv.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009151321-6k73tn8.png)

## 特殊注释

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
```

第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，**Windows系统会忽略这个注释**；

第二行注释是为了告诉Python解释器，**按照UTF-8编码读取源代码**，否则，你在源代码中写的中文输出可能会有乱码。

## 占位符 格式化

### 占位符%s %d %f

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152324-rmac8lz.png)

格式化方式和C语言是一致

` %`运算符就是用来格式化字符串的。

在字符串内部，

`%s`表示用字符串替换，

`%d`表示用整数替换，

有几个 `%?`占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个 `%?`，括号可以省略

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152708-zy7vi8x.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152722-wq5flos.png)

| 占位符 | 替换内容     |
| ------ | ------------ |
| %d     | 整数         |
| %f     | 浮点数       |
| %s     | 字符串       |
| %x     | 十六进制整数 |

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009153422-r1s8f5z.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009153433-1uhb1w3.png)

转义：`%%`来表示一个 `%`

### format（）格式化字符串

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154141-a3v7tnj.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154153-o6u9yd7.png)

### f-string 格式化字符串

`{r}`被变量 `r`的值替换，`{s:.2f}`被变量 `s`的值替换，并且 `:`后面的 `.2f`指定了格式化参数（即保留两位小数），因此，`{s:.2f}`的替换结果是 `19.62`

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154406-qahm3f7.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154432-m2z0xx5.png)

## 函数式编程

函数是Python内建支持的一种封装，通过层层函数进行调用

#面向过程的程序设计#：把复杂任务分解成简单的任务，这种分解可以称之为面向过程的程序设计

函数式和函数的区别：

对比例子：计算和计算器的区别

编程语言，就是越低级的语言，越贴近计算机，抽象程度低，执行效率高，比如C语言；越高级的语言，越贴近计算，抽象程度高，执行效率低，比如Lisp语言

Python不是纯函数式编程语言

函数式编程就是一种抽象程度很高的编程范式，

纯粹的函数式编程语言编写的**函数没有变量**，因此，任意一个函数，**只要输入是确定的，输出就是确定的**

### 函数式编程特点：

1. 纯函数式编程语言函数没有变量，输入输出确定
2. 允许本身作为参数传入另一个函数，允许返回一个函数

## 高阶函数

参数中有函数

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回

### 变量可以指向函数

a=函数

求绝对值的函数 `abs()`为例

```python
print(abs(-10))
print(abs)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019114343-h6egecv.png)

abs（-10）是函数调用，abs是函数本身

```python
k=abs(-20)
print(k)
#函数本身也可以赋值给变量
h=abs
print(h)
print(h(-100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019114757-z778j3c.png)

结论：函数本身也可以赋值给变量，即：#变量可以指向函数。#

### 函数名也是变量

#函数名#：**其实就是指向函数的变量**

a()中a是指向函数a（）的变量

### 传入函数

既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

#高阶函数#：**一个函数就可以接收另一个函数作为参数**

b()

a(b)

x=a

```python
def f(x):
    return abs(int(x))
def a(a,b,f):
    return f(a)+f(b)
if __name__ == '__main__':
    a1=input('a')
    a2=input('b')
    print(a(a1,a2,f))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019115835-q2esytb.png)

此时函数a为高阶函数，需要调用f函数作为参数

## map/reduce 内建函数

内建了 `map()`和 `reduce()`函数 高阶函数

### map（）函数处理生成新Iterator迭代器

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019131933-ut47b16.png)两个参数，函数名【函数本身】，需要处理的编程式iterator

`<br />`创建一个迭代器，使用每个迭代器中的参数计算函数。当最短迭代用尽时停止。

```python
 map(func, *iterables) --> map object
```

```python
def f(x):
    return x*x
r=map(f,[1,2,3,4,4,4,4,4,4,4,4])
print(r)
print(type(r))
print(list(r))
print(type(list(r)))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019133740-kxaifya.png)

运算规则抽象

### reduce（）函数作用在序列上

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019142951-sxqvxp4.png)

两个参数，函数名【函数本身】，需要处理的#序列#： sequence(序列)是一组有顺序的元素的集合

序列基本样式[下限:上限:步长]

`reduce`把结果继续和序列的下一个元素做累积计算

```python
reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```

```python
from functools import reduce
>>> def fn(x, y):
...     return x * 10 + y
...
>>> reduce(fn, [1, 3, 5, 7, 9])
13579
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019142820-4tlrn7x.png)

## filter()过滤序列

参数和map（）相似

`filter()`也接收一个函数和一个序列

## sorted（）排序

高阶函数![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184319-dzvm55o.png)

参数：排序对象，key=函数

```bash
sorted([36, 5, -12, 9, -21], key=abs)
```

排序的核心是比较两个元素的大小

```bash
print(sorted([1,2,353,6,3,234,43,435]))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184421-43dcfax.png)

key指定绝对值大小排序

```bash
print(sorted([1,2,353,6,3,234,43,435,-242,-34,34,35],key=abs))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184629-q7j7zxx.png)

## 返回函数

### 函数作为返回值

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回

```bash
# 如果不需要立刻求和，而是在后面的代码中，
# 根据需要再计算怎么办？可以不返回求和的结果，而是返回求和的函数：
def zary_sum(a):
    def sum():
        sum1=0
        for i in a:
            sum1=sum1+i
        return sum1
    return sum
print(type(zary_sum([1,2,3,4])))
f=zary_sum([1,2,3,4])
print(f())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100621-oot0dd6.png)

调用返回函数时，每次调用都会新生成一个函数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100747-ho01xzp.png)

## 闭包

当一个函数的返回值是另外一个函数，

而返回的那个函数如果调用了其父函数内部的其它变量，如果 **返回的这个函数在外部被执行，就产生了闭包** 。

**返回函数中，返回的函数调用父函数的内部变量**

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100950-gl5liu8.png)

```bash
#返回函数
def count():
    fs=[]
    for i in range(1,4):
        def f():
            return i*i
        fs.append(f)
    return fs
f1,f2,f3=count()
print(f1(),f2(),f3())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021103727-wtd0kdc.png)

返回一个函数时，牢记该函数并未执行，返回函数中不要引用任何可能会变化的变量。

## lambda（）匿名函数

lambda关键字 函数参数：函数表达式

传入函数时，有些时候，不需要显式地定义函数

Python对匿名函数的支持有限，只有一些简单的情况下可以使用匿名函数。

```bash
lambda x:x*x
#等价于
def f(x):
   return x*x
```

关键字 `lambda`表示匿名函数，冒号前面的 `x`表示函数参数，只能一个表达式

不用写 `return`，返回值就是该表达式的结果。

匿名函数也是一个函数对象

```bash
f=lamdba x:x*x
```

判断奇数函数

原函数：

```bash
def is_odd(n):
    return n % 2 == 1

L = list(filter(is_odd, range(1, 20)))
```

采用匿名函数修改

```bash
l=list(filter(lambda x:x%2==1,range(1,20)))
print(l)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021143505-wbqh836.png)

## 装饰器 Decorator

### 本质上，装饰器就是一个返回函数的高阶函数

@log 等价于

```bash
now = log(now)
```

由于函数也是一个对象，而且函数对象可以被赋值给变量，

所以，通过变量也能调用该函数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022101101-ncgju0i.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022101111-tgdwt0q.png)

```bash
def log(func):
    def wrapper(*args,**kwargs):
        print('call %s'% func.__name__)
        return func(*args,**kwargs)
    return wrapper()
#func为参数所以是高阶函数
#return 函数所以是返回函数，
#没有调用父函数中参数，所以不是闭包
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022110733-h27x1zh.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022110058-zyo7xpn.png)

场景注意：

无@装饰器时函数不调用，需要参数才调用

当@时会直接调用装饰器定义函数然后执行函数，不用调用函数

三层时，传入参数

```bash
def log1(text):
    def decorator(func):
        def wapper(*args,**kw):
            print('%s %s'%(text,func.__name__))
            return func(*args,**kw)
        return wapper
    return decorator
@log1('ruan')
def now3():
    print("hhh")
now3()
```

相当于在返回高阶函数上还有一个函数，所以返回时应该还要调用一次

## @wraps 常用装饰器

当装饰器是个闭包时，装饰器调用变量会改变增加@wraps后装饰器内的变量不变

装饰器在装饰一个函数时,，原函数就成了一个新的函数,也

就是说其属性会发生变化,所以为了 **不改变原函数的属性** ,

我们会调用functools中的wraps装饰器来保证原函数的属性不变

#### 不加wraps时

```bash
  @wraps(func)
```

```bash
from functools import wraps
def wrap(func):
   
    def b():
        'b'
        print('decorator:',b.__name__)
        print('funname',func.__name__)
        func()
    return b
@wrap
def a():
    'a'
    print('name',a.__name__)
a()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022115935-kgsz7b2.png)

加装饰器wraps时

```bash
from functools import wraps
def wrap(func):
    @wraps(func)
    def b():
        'b'
        print('decorator:',b.__name__)
        print('funname',func.__name__)
        func()
    return b
@wrap
def a():
    'a'
    print('name',a.__name__)
a()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022115950-2j3i7ht.png)

闭包的概念：调用父函数中的变量的函数，为了保证数据安全。变量作用域只在函数内部，可在闭包中操作数据。

装饰器返回为什么是函数名（函数内存地址）而不直接执行函数?

当有参数传入时，可直接与调用的函数中的值传入参数执行。

（）是运算符f()与f.__call__()等价：将f对象变成变成可调用的对象

## 偏函数（functools模块）

属于functools模块

### 作用：

通过设定参数的默认值，降低函数调用的参数

`int()`函数默认按十进制转换

print(int('100',base=8))

经常调用于是重写一个函数int2

```bash
def int2(x, base=8):
    print(int(x, base))
    return int(x, base)
print(int2('2334'))
```

采用偏函数

```bash
import functools
int3=functools.partial(int,base=8)
print(int3('46'))
print(int())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028103219-mdbldp6.png)

functools.partial的作用是将函数的特定参数固定住（设定为默认值）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028103645-7po81oc.png)

创建偏函数的时候也可以接收，函数对象，*args，**kw

## 模块

python包：作用区分相同名称的模块

模块相当于一个py文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028105055-2xv0z2i.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028105133-tkzgcka.png)

## 作用域

仅仅在模块内部使用。在Python中，是通过 `_`前缀来实现的。

### pubilc公开

正常的函数和变量名是公开的（public）

### private非公开_,__

_xxx和__xxx这样的函数或变量就是非公开的（private）

## 安装第三方模块pip

pip install 模块名

### 模块搜索路径

```bash
import sys
print(sys.path)
```

两种方式：

1. 添加搜索路径
   ```bash
    import sys
   sys.path.append('/Users/michael/my_py_scripts')
   ```
2. 设置环境变量

第二种方法是设置环境变量 `PYTHONPATH`

## 面向对象编程

面向对象编程——Object Oriented Programming，简称OOP，是一种程序设计思想

对象作为程序的基本单元，

一个对象包含了数据和操作数据的函数

数据封装、继承和多态是面向对象的三大特点

## 类和实例

面向对象最重要的概念就是类（Class）和实例（Instance）

类是抽象出来的模板

实例是根据类创建出的对象，每个对象可能有属性和方法

定义类是通过 `class`关键字，类名通常是大写开头的单词

```bash
class Student(object):
    pass
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028113324-1nch2o5.png)

！！！在类中定义函数有一点不同，定义佛如方法第一个参数永远是实例变量本身self

仍然可以用默认参数、可变参数、关键字参数和命名关键字参数

## 数据封装

```bash
class Student(object):
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def get_grade(self):
        if self.score >= 90:
            return 'A'
        elif self.score >= 60:
            return 'B'
        else:
            return 'C'
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028113713-vhhvowi.png)

## 访问限制

### 作用：

**确保了外部代码不能随意修改对象内部的状态**

实例的变量名如果以 `__`开头，就变成了一个私有变量（private）

外部无法访问_name

```bash
class Student(object):
    def __init__(self,name,age):
        self._name=name
        self.age=age
    def print_name(self):
        print(self._name)
        return self.age,self._name
a=Student('ruan',23)
h=a.print_name()
print(h)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028114732-awu2k2m.png)

若是要获取，修改变量增加get，set方式即可

```bash
class Student(object):
    def __init__(self,name,age):
        self._name=name
        self.age=age 
    def get_name(self):
        return self.name
    def set_name(self,name):
        self._name=name
```

Python本身没有任何机制阻止你干坏事，一切全靠自觉。

类外部无法访问

## 继承和多态

### 继承

#### 多态

在继承关系中，如果一个实例的数据类型是某个子类，那它的数据类型也可以被看做是父类。

比如：动物是父类，狗和鱼是子类；鱼是鱼类，鱼是动物都成立。

判断一个变量是否是某个类型可以用 `isinstance()`判断

### 鸭子类型

并不要求严格的继承体，一个对象只要“看起来像鸭子，走起路来像鸭子”，那它就可以被看做是鸭子。

## 获取对象信息

### type（）判断对象类型

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211102183643-gwgjuho.png)

### isinstance()对于继承关系，判断class的类型

### dir（）获取对象的所有属性和方法

#### len（）对象长度

#### lower（）返回小写的字符串

#### getattr（）获取属性a

#### setattr（）设置属性a

#### hasattr（obj,'a'）判断是否有属性a

```bash
getattr(obj, 'z', 404) # 获取属性'z'，如果不存在，返回默认值404
404
```

## 实例属性和类属性

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211102184822-83nvy25.png)

```bash
 class Student(object):
    name='ruan'
   
h=Student()
h.name='hhh'

```

类中的name是类属性，

创建h类对象即实例后赋值的是实例属性name，但由于实例对象的优先级比类属性高，会屏蔽类中的name属性，即h.name的值为hhh

### 总结：

1. 实例属性属于各个实例所有，互不干扰；
2. 类属性属于类所有，所有实例共享一个属性；
3. 不要对实例属性和类属性使用相同的名字，否则将产生难以发现的错误

# 面向对象高级编程

数据封装、继承和多态只是面向对象程序设计中最基础的3个概念

多重继承、定制类、元类

# _slots_使用

可以给创建的实例绑定属性和方法

给一个实例绑定的方法对另外一个实例对象是不起作用的

```bash
class A:
    def run(self):
        print("i im ferther runing....")
sun1=A()
#给实例sun1设置name属性
sun1.name='i im name'
#创建实例对象2
sun2=A()
#实例对象sun1的属性和sun2无关，即sun2没有name属性
#给实例sun1绑定方法，方法和属性同理
#定义方法
def setAll(self,num):
    print(num)
sun1.newfun=MethodType(setAll, sun1)
sun1.newfun(37)
#若所有实例都需要绑定方法则给类绑定方法
A.setAll=setAll
#给类绑定方法后，所有创建的实例的均可调用
```

```
def set_age(self, age): # 定义一个函数作为实例方法
...     self.age = age
...
>>> from types import MethodType
>>> s.set_age = MethodType(set_age, s) # 给实例绑定一个方法
>>> s.set_age(25) # 调用实例方法
```

## 限制实例属性，定义一个特殊的 `__slots__`变量

```python
class Student(object):
    __slots__ = ('name', 'age') # 用tuple定义允许绑定的属性名称
s=Student()
s.name='ruan'
s.firstname='i im firstname'
#输出的时候firstname的属性会报错，
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'firstaname'
```

### 注意：

_slots_使用时要注意，定义的属性只在当前的类的实例中，对于继承的子类是不起作用的

```python
class People(object):
    __slots__ = ('name','age')
    def run(self):
        print('i im run people......')

class Teacher(People):
    def say(self):
        print('i im teacher....')
t=Teacher()
t.tall='shouhua'
print(t.tall)
p=People()
p.tall('shouhuap')
print(p.tall)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103140608-7ezqmvs.png)

只限制父类People的属性，而子类Teacher中不限制

## @property

在绑定属性时，如果我们直接把属性暴露出去,导致可以随意更改.通过get，set来获取更改属性值。

在python中直接调用装饰器将一个方法变成属性调用

```python
class Student(object):
    @property
    #使用get方法是调用装饰器@peoperty，
    # 同时自动创建了另一个装饰器@属性.setter
    def score(self):
        return self.score
    @score.setter
    def score(self,value):
        self._score=value
```

## 总结：

-权限限制只对类对象实际起作用，想要达到方法和属性强制访问权限，需要使用@property装饰器进行get，set方法

属性名与方法名一定要区分开，不然会进入死循环（self._age，def age()）
实例化的对象使用属性时，不是调用属性（meizi._age），而是用的方法名（meizi.age）
@property其实就是实现了getter功能； @xxx.setter实现的是setter功能；还有一个 @xxx.deleter实现删除功能
定义方法的时候 @property必须在 @xxx.setter之前，且二者修饰的方法名相同（age()）
如果只实现了 @property（而没有实现@xxx.setter），那么该属性为 只读属性

```python
#请利用@property给一个Screen对象加上width和height属性，
# 以及一个只读属性resolution：
class Screen(object):
    __slots__ = ('_width','_height','_resolution')

    @property
    def width(self):
        return self._width

    # 方法名称和实例变量均为width:
    @width.setter
    def width(self,widthValue):
        self._width=widthValue

    @property
    def height(self):
        return self._height

    @width.setter
    def height(self, height):
        self._height = height

    @property
    def resolution(self):
        return self._width * self._height
s=Screen()
s.width=23
s.height=12

print(s.resolution)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103150647-dge6za2.png)

```python
s.score = 60 # OK，实际转化为s.set_score(60)
s.score # OK，实际转化为s.get_score()
```

要特别注意：属性的方法名不要和实例变量重名。例如，以下的代码是错误的：

```
class Student(object):

    # 方法名称和实例变量均为birth:
    @property
    def birth(self):
        return self.birth
```

出现递归调用错误

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103151046-5z499ew.png)

之前的例子中width和_width不同所以可以运行

## 多重继承

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103151750-dvwa7qb.png)

python可以支持多继承，即一个子类可以继承多个父类；但java是单继承，只能有一个父类

Tercher（Name，study，teach）即Teacher可以继承多个父类

### MixIn

在设计类的继承关系时，通常，主线都是单一继承下来的，例如，`Teacher`继承自Name。但是，如果需要“混入”额外的功能，通过多重继承就可以实现，比如Teacher除了继承自 `Name`外，再同时继承 `Teach`。这种设计通常称之为MixIn

Python自带了 `TCPServer`和 `UDPServer`这两类网络服务，而要同时服务多个用户就必须使用多进程或多线程模型，这两种模型由 `ForkingMixIn`和 `ThreadingMixIn`提供。

### 多继承

多重继承这个名词一般用来形容继承链条可以很长，多个层次。

### 多重继承

**多继承则指一个类可以有多个基类，相反则是单继承**。任何面向对象编程语言都支持多重继承，但像java这种只能通过接口实现有限程度的多继承

问：多继承 如果多个类有共同得方法名 怎么区分是调得哪个类🤡

答：调用该方法的时候，会调用第一顺位继承父类的方法

### 总结：

1. Python允许使用多重继承，因此，MixIn就是一种常见的设计
2. 只允许单一继承的语言（如Java）不能使用MixIn的设计

## 定制类

Python的class中还有__xxx__有特殊用途的函数，可以帮助我们定制类

### __str__()回用户看到的字符串

将对象 `<__main__.Student object at 0x109afb190>`变成易读的数据

只在调用print时会调用__str__，交互界面时还是现实上方不易读的对象内容，此时用

### __repr__()返回程序开发者看到的字符串

`__str__()`返回用户看到的字符串，而 `__repr__()`返回程序开发者看到的字符串，

也就是说，`__repr__()`是为调试服务的

简写

```python
def __str__(self):
        return 'xxx object (name=%s)' % self.name
__repr__ = __str__
```

### ___iter__()返回一个迭代对象

需要用到for in迭代，需要转化为迭代对象

该方法返回一个迭代对象，然后，Python的for循环就会不断调用该迭代对象的 `__next__()`方法拿到循环的下一个值，直到遇到 `StopIteration`错误时退出循环

例子：

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
a=Fib()
for i in a:
    print(i)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155046-1xs33i9.png)

### __**getitem**__()表现得像list那样按照下标取出元素

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
    def __getitem__(self, item):
        a,b=1,1
        for i in range(item):
            a,b=b,a+b
        return a
a=Fib()
print(a[3])

```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155122-fo5pjxz.png)

以上是传入int，切片功能实现，isinstance判断类型

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
    def __getitem__(self, item):
        if isinstance(item,int):
            a, b = 1, 1
            for i in range(item):
                a, b = b, a + b
            return a
        if isinstance(item,slice):
            start=item.start
            stop=item.stop
            if start is None:
                start=0
            a,b=1,1
            L=[]
            for x in range(stop):
                L.append(a)
                a,b=b,a+b
        return L

a=Fib()
print(a[3:12])
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155838-wdwjies.png)

### __getattr__()动态返回一个属性

调用类属性或方法时，先在__init__()获取后，再从__getattr__()获取，获取不到才报错

### __call__()直接调用实例本身

与直接调用这个函数一样

```python
class People(object):
    def __init__(self,name):
        self.name=name
    def __call__(self, *args, **kwargs):
        print('i im call %s'% self.name)

p=People('ruan')
p()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104150832-d8wkn0m.png)

## 使用枚举类

枚举类：在某些情况下，一个类的 实例对象 的**数量**是 **有限且固定** 的，如季节类，它的实例对象只有春、夏、秋、冬。 在Java中像这种对象实例有限且固定的类被称为枚举类；这样的枚举类型定义一个class类型，然后，每个常量都是class的一个唯一实例。Python提供了 `Enum`类来实现这个功能。

```python
from enum import Enum
M=Enum('a',('sun1','sun2','sun3','sun4'))
print(M.sun1)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104151622-x7yqw9j.png)

自定义枚举类

```python
from enum import Enum,unique
@unique
class Week(Enum):
    sun1=1
    sun2=2
    sun3=3
day2=Week.sun2
print(day2)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104152125-y6nm9vn.png)

```python
from enum import Enum,unique
@unique
class Gender(Enum):
    Male=0
    Female=1
class Student(object):
    def __init__(self,name,gender):
        self.name=name
        self.gender=gender

# 测试:
bart = Student('Bart', Gender.Male)
if bart.gender == Gender.Male:
    print('测试通过!')
else:
    print('测试失败!')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104152731-wmdziil.png)

## 使用元类[创建类]

实例对象是类创建

类是元类创建

创建类的方式

### 方式一：type（）

`type()`函数既可以返回一个对象的类型，又可以创建出新的类型，比如，我们可以通过 `type()`函数创建出 `Hello`类

```python
from class1104 import *
h=Hello()
print(type(h))
print(type(Hello))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104153538-6iulybe.png)

```python
 Hello = type('Hello', (object,), dict(hello=fn))
```

要创建一个class对象，`type()`函数依次传入3个参数：

1. class的名称；
2. 继承的父类集合，注意Python支持多重继承，如果只有一个父类，别忘了tuple的单元素写法；
3. class的方法名称与函数绑定，这里我们把函数 `fn`绑定到方法名 `hello`上

### 方式二：元类metaclass

先定义metaclass，然后创建类。

先定义类，然后创建实例。

~~metaclass是Python面向对象里最难理解，也是最难使用的魔术代码。~~

按照默认习惯，metaclass的类名总是以Metaclass结尾，以便清楚地表示这是一个metaclass

```python
# metaclass采用type创建类 ，metaclass是类的模板，所以必须从`type`类型派生
class ListMetaclass(type):
    def __new__(cls, name,bases,attrs):
        attrs['add']=lambda self, value:self.append(value)
        return type.__new__(cls,name,bases,attrs)

class MyList(list,metaclass=ListMetaclass):
    pass
mylist=MyList()
mylist.add(1)
print(mylist)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104155010-cbldtfp.png)

`__new__()`方法接收到的参数依次是：

1. 当前准备创建的类的对象；
2. 类的名字；
3. 类继承的父类集合；
4. 类的方法集合

### 应用场景

ORM全称“Object Relational Mapping”，即对象-关系映射，就是把关系数据库的一行映射为一个对象，也就是一个类对应一个表，这样，写代码更简单，不用直接操作SQL语句。

要编写一个ORM框架，所有的类都只能动态定义，因为只有使用者才能根据表的结构定义出对应的类来。

## 错误处理try

```python
try:
    print('try...')
    r = 10 / 0
    print('result:', r)
except ValueError as e:
    print('ValueError:', e)
except ZeroDivisionError as e:
    print('ZeroDivisionError:', e)e)
finally:
    print('finally...')
print('END')
```

Python的错误其实也是class，所有的错误类型都继承自 `BaseException`

`UnicodeError`是 `ValueError`的子类🤡

[Built-in Exceptions — Python 3.10.0 documentation](https://docs.python.org/3/library/exceptions.html#exception-hierarchy)

## 调用栈

让Python解释器来打印出错误堆栈

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104162726-fird23x.png)

## 记录错误logging

可将logging生成一个txt方便查看

```python
 try:
        xxx
    except Exception as e:
        logging.exception(e)
```

### 抛出错误raise

```python
 except ValueError as e:
        print('ValueError!')
        raise
```

在 `bar()`函数中，我们明明已经捕获了错误，但是，打印一个 `ValueError!`后，又把错误通过 `raise`语句抛出去了，这不有病么？

其实这种错误处理方式不但没病，而且相当常见。捕获错误目的只是记录一下，便于后续追踪。但是，由于当前函数不知道应该怎么处理该错误，所以，最恰当的方式是继续往上抛，让顶层调用者去处理。

## 调试方法

### 1. print（）

### 2. 断言assert

```python
 assert n != 0, 'n is zero!'
```

`assert`的意思是，表达式 `n != 0`应该是 `True`，否则，根据程序运行的逻辑，后面的代码肯定会出错。

采用断言的好处：

启动Python解释器时可以用 `-O`参数来关闭 `assert`：

```python
$ python -O err.py
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104164034-js5sidi.png)

关闭后，你可以把所有的 `assert`语句当成 `pass`来看

### 3. logging

```python
import logging
s = '0'
n = int(s)
logging.info('n = %d' % n)
print(10 / n)
```

### 4.pbd单步执行

启动Python的调试器pdb，让程序以单步方式运行，可以随时查看运行状态。

```python
python -m pdb xxx.py
(Pbd) 1#查看第一行代码，单步执行第一行代码
```

### 5. pdb.set_trace()

这个方法也是用pdb，但是不需要单步执行，我们只需要 `import pdb`，然后，在可能出错的地方放一个 `pdb.set_trace()`，就可以设置一个断点：

```python
import pdb

s = '0'
n = int(s)
pdb.set_trace() # 运行到这里会自动暂停
print(10 / n)
```

可以用命令 `p`查看变量，或者用命令 `c`继续运行：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104164634-anjnpuu.png)

### 6.IDE工具

vscode,pycharm....

## 单元测试

单元测试是用来对一个模块、一个函数或者一个类来进行正确性检验的测试工作。

## 文档测试

doctest非常有用，不但可以用来测试，还可以直接作为示例代码。通过某些文档生成工具，就可以自动把包含doctest的注释提取出来。用户看文档的时候，同时也看到了doctest。

Python内置的“文档测试”（doctest）模块可以直接提取注释中的代码并执行测试.

```python
class Dict(dict):
    """"
      这一段就是文档测试
       Simple dict but also support access as x.y style.

       >>> d1 = Dict()
       >>> d1['x'] = 100
       >>> d1.x
       100
       >>> d1.y = 200
       >>> d1['y']
       200
       >>> d2 = Dict(a=1, b=2, c='3')
       >>> d2.c
       '3'
       >>> d2['empty']
       Traceback (most recent call last):
           ...
       KeyError: 'empty'
       >>> d2.empty
       Traceback (most recent call last):
           ...
       AttributeError: 'Dict' object has no attribute 'empty'
       """

    def __init__(self, **kw):
        super(Dict, self).__init__(**kw)

    def __getattr__(self, key):
        try:
            return self[key]
        except KeyError:
            raise AttributeError(r"'Dict' object has no attribute '%s'" % key)

    def __setattr__(self, key, value):
        self[key] = value

if __name__ == '__main__':
    import doctest
    doctest.testmod()
```

将其中一个函数注释，运行让它报错

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108110503-erlvnk1.png)

## IO编程

程序和运行时的数据在内存中驻留

涉及到数据交换的地方，通常是磁盘、网络等，就需要IO接口

通常，程序完成IO操作会有Input和Output两个数据流

Stream（流）是一个很重要的概念，可以把流想象成一个水管，数据就是水管里的水，但是只能单向流动。

在IO编程中，就存在**速度严重不匹配的问题**。举个例子来说，比如要把100M的数据写入磁盘，CPU输出100M的数据只需要0.01秒，可是磁盘要接收这100M数据可能需要10秒，怎么办呢？有两种办法：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108111749-yobbduz.png)

## 同步IO

第一种是CPU等着，也就是程序暂停执行后续代码，等100M的数据在10秒后写入磁盘，再接着往下执行，这种模式称为同步IO；

## 异步IO

另一种方法是CPU不等待，只是告诉磁盘，“您老慢慢写，不着急，我接着干别的事去了”，于是，后续代码可以立刻接着执行，这种模式称为异步IO。

如果是服务员跑过来找到你，这是回调模式，如果服务员发短信通知你，你就得不停地检查手机，这是轮询模式。总之，异步IO的复杂度远远高于同步IO。

## 文件读写

### 读文件open（）

传入文件名，标示符

参数：'rb' 二进制

encoding='gbk'字符编码

```python
f = open('/Users/michael/test.txt', 'r')
```

### read()一次读取全部内容

```python
 f.read()
'Hello, world!'
```

### f.close（）关闭文件

简化方法

### with open('filepath', 'r') as f:    print(f.read())

Python引入了 `with`语句来自动帮我们调用 `close()`方法，并且不必调用 `f.close()`方法

```python
with open('/path/to/file', 'r') as f:
    print(f.read())
```

如果文件很小，`read()`一次性读取最方便；

如果不能确定文件大小，反复调用 `read(size)`比较保险；

如果是配置文件，调用 `readlines()`最方便

```python
for line in f.readlines():
    print(line.strip()) # 把末尾的'\n'删掉
```

file和缓存时=是file-like Object对象，不要求从特定类继承，只要写个 `read()`方法就行

### f.write()写文件

```python
f = open('/Users/michael/test.txt', 'w')
f.write('Hello, world!')
f.close()
```

或

```python
with open('/Users/michael/test.txt', 'w') as f:
    f.write('Hello, world!')
```

使用 `with`语句操作文件IO是个好习惯

## StringIO和BytesIO

### StringIO

StringIO顾名思义就是在内存中读写str

```python
 from io import StringIO
 f = StringIO()
f.write('hello')
```

`getvalue()`方法用于获得写入后的str

```python
 from io import StringIO
>>> f = StringIO('Hello!\nHi!\nGoodbye!')
>>> while True:
...     s = f.readline()
...     if s == '':
...         break
...     print(s.strip())
```

### BytesIO

操作二进制数据，就需要使用BytesIO

```python
>>> from io import BytesIO
>>> f = BytesIO()
>>> f.write('中文'.encode('utf-8'))
6
>>> print(f.getvalue())
b'\xe4\xb8\xad\xe6\x96\x87'
```

## os模块

### os.name操作系统类型

### os.uname()详细系统信息

### os.enciron环境变量

要获取某个环境变量的值，可以调用 `os.environ.get('key')`

```python
# 查看当前目录的绝对路径:
>>> os.path.abspath('.')
'/Users/michael'
# 在某个目录下创建一个新目录，首先把新目录的完整路径表示出来:
>>> os.path.join('/Users/michael', 'testdir')
'/Users/michael/testdir'
# 然后创建一个目录:
>>> os.mkdir('/Users/michael/testdir')
# 删掉一个目录:
>>> os.rmdir('/Users/michael/testdir')
```

通过 `os.path.join()`函数，这样可以正确处理不同操作系统的路径分隔符

### `os.path.join(`)连接路径

### `os.path.split()`拆分路径

### `os.path.splitext()` 文件扩展名

```python
# 对文件重命名:
>>> os.rename('test.txt', 'test.py')
# 删掉文件:
>>> os.remove('test.py')
```

`shutil`模块提供了 `copyfile()`的函数，它们可以看做是 `os`模块的补充

最后看看如何利用Python的特性来过滤文件。比如我们要列出当前目录下的所有目录，只需要一行代码：

```
>>> [x for x in os.listdir('.') if os.path.isdir(x)]
['.lein', '.local', '.m2', '.npm', '.ssh', '.Trash', '.vim', 'Applications', 'Desktop', ...]
```

要列出所有的 `.py`文件，也只需一行代码：

```
>>> [x for x in os.listdir('.') if os.path.isfile(x) and os.path.splitext(x)[1]=='.py']
['apis.py', 'config.py', 'models.py', 'pymonitor.py', 'test_db.py', 'urls.py', 'wsgiapp.py']
```

## 序列化pickle模块

变量从内存中变成可存储或传输的过程称之为序列化,Python中叫pickling

变量内容从序列化的对象重新读到内存里称之为反序列化，即unpickling

### pickle.dumps()对象-》字节[序列化]

`pickle.dumps()`方法把任意对象序列化成一个 `bytes`

`pickle.dumps()`方法把任意对象序列化成一个 `bytes`,并写入文件中

```python
import pickle
d=dict(name='ruan',age=34,freand='woman')
# print(pickle.dumps(d))
f = open('timezone.txt', 'wb')
pickle.dump(d, f)
f.close()
```

### pickle.load()字节-》对象【反序列化】

```python
import pickle
f=open(r'C:\Users\yangs\PycharmProjects\python_study\fun\timezone.txt','rb')
d=pickle.load(f)
f.close()
print(d)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108132946-rtt8k8p.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108133035-b8gyft4.png)

## json模块

`json`模块的 `dumps()`和 `loads()`函数是定义得非常好的接口的典范。

#### json.dumps(python对象)python对象-》json对象

`dumps()`方法返回一个 `str`，内容就是标准的JSON

#### json.loads(json对象)json对象-》python对象

`json.``dump`(obj, fp, *, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw**)**

### 类变为字典并序列化

```python
json.dumps(s, default=lambda obj: obj.__dict__)
```

## 进程和线程

Python的标准库提供了两个模块：`_thread`和 `threading`，`_thread`是低级模块，`threading`是高级模块

**线程是最小的执行单元，而进程由至少一个线程组成**

操作系统轮流让各个任务交替执行

真正的并行执行多任务只能在多核CPU上实现

对于操作系统来说，一个任务就是一个进程（Process），比如打开一个浏览器就是启动一个浏览器进程

Word，它可以同时进行打字、拼写检查、打印等事情。在一个进程内部，要同时干多件事，就需要同时运行多个“子任务”，我们把进程内的这些“子任务”称为线程（Thread）

* 多进程模式；
* 多线程模式；
* 多进程+多线程模式。

## 多进程

Unix/Linux操作系统提供了一个 `fork()`系统调用，普通的函数调用，调用一次，返回一次，但是 `fork()`调用一次，返回两次，因为操作系统自动把当前进程（称为父进程）复制了一份（称为子进程），然后，分别在父进程和子进程内返回。

创建子进程

```python
from multiprocessing import Process
import os
def run_pro(name):
    print('开始运行子进程%s，%s'%(name,os.getpid()))

if __name__ == '__main__':
    print('开始运行进程%s' % (os.getpid()))
    p=Process(target=run_pro,args=('test',))
    p.start()
    p.join()
    print('end')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211111131512-zqm80if.png)

### 启动大量子进程pool

进程池

```python
import time, threading

# 新线程执行的代码:
def loop():
    print('thread %s is running...' % threading.current_thread().name)
    n = 0
    while n < 5:
        n = n + 1
        print('thread %s >>> %s' % (threading.current_thread().name, n))
        time.sleep(1)
    print('thread %s ended.' % threading.current_thread().name)

print('thread %s is running...' % threading.current_thread().name)
t = threading.Thread(target=loop, name='LoopThread')
t.start()
t.join()
print('thread %s ended.' % threading.current_thread().name)
```

# 模块总结

## doctest文档测试

## os.path文件路径

## pickle序列化

## json

[使用dict和set - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/1016959663602400/1017104324028448)

用于学习记录，后期便于复习，参考链接

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102447-hmq8gs8.png)

python file

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102545-qqmxrgo.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009102644-7ny4t2k.png)

调用脚本时会先载入pyhton解释器，然后运行脚本

rpm：软件管理包

操作符优先级：![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009104337-b66ot2k.png)

条件判断：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009104751-a27qfzb.png)

Python为我们提供了非常完善的基础代码库，覆盖了网络、文件、GUI、数据库、文本等大量内容，被形象地称作“内置电池（batteries included）”。用Python开发，许多功能不必从零编写，直接使用现成的即可。

语言定位：

Python的定位是“优雅”、“明确”、“简单”

Python是解释型语言

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211011172523-7k51l6e.png)

# python

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009110719-7urayjl.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009111236-gd1mcju.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009111303-l3bqira.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009113303-w7qziw5.png)

## 数据类型

### int 整型

long int长整型

int 整型

### float 浮点型

浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时

双精度浮点型 e

浮点型

### String 字符串

字符串是以单引号 `'`或双引号 `"`括起来的任意文本

字符串是以Unicode编码

对于单个字符的编码，Python提供了 `ord()`函数获取字符的整数表示，`chr()`函数把编码转换为对应的字符：

### Bool布尔

True

Flase

### None 空值

None，`None`不能理解为 `0`，因为 `0`是有意义的,

Null无意义

.

<iframe src="http://127.0.0.1:6806/widgets/brython-editor" data-src="http://127.0.0.1:6806/widgets/brython-editor" data-subtype="widget" border="0" frameborder="no" framespacing="0" allowfullscreen="true" style="width: 1341px; height: 276px;"></iframe>

### 变量

变量的概念基本上和初中代数的方程变量是一致的，

变量不仅可以是数字，还可以是任意数据类型。

变量名必须是大小写英文、数字和 `_`的组合，且不能用数字开头，字母或下划线开头

```python
#变量类型
a=1
b='我是变量'
c=True
d=12.2e3
print(a,b,c,d)
print(type(a),type(b),type(c),type(d))

```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009134601-1cuacaj.png)

int a=1 静态语言 此时已经分配的int分区之后不能更改变量类型【不支持，Java】

a=3 动态语言，可以赋值成任意类型

#### 动态定义

#### 静态定义

```python
a = 'ABC'
b = a
a = 'XYZ'
print(b)
```

执行 `a = 'ABC'`，解释器创建了字符串 `'ABC'`和变量 `a`，并把 `a`指向 `'ABC'`：

![py-var-code-1](https://www.liaoxuefeng.com/files/attachments/923791878255456/0)

执行 `b = a`，解释器创建了变量 `b`，并把 `b`指向 `a`指向的字符串 `'ABC'`：

![py-var-code-2](https://www.liaoxuefeng.com/files/attachments/923792058613440/0)

执行 `a = 'XYZ'`，解释器创建了字符串'XYZ'，并把 `a`的指向改为 `'XYZ'`，但 `b`并没有更改：

![py-var-code-3](https://www.liaoxuefeng.com/files/attachments/923792191637760/0)

### 常量

所谓常量就是不能变的变量，通常用全部大写的变量名表示常量：

```python
PI = 3.14159265359
```

## list列表

list是一种有序的集合，可以随时添加和删除其中的元素。

```python
list=['a','b','c']
print(list)
print(len(list))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154856-r9s5yyu.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154907-bofhvvd.png)

### 切分

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155126-p31z8um.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155139-cpsoatf.png)

### append（）追加

str.append('a')

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155556-qrj4a63.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009155606-dxihfwr.png)

### insert插入指定位置

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009162557-186v350.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009162609-u00z8m3.png)

### pop（）删除末尾元素

要删除指定位置的元素，用 `pop(i)`方法，其中 `i`是索引位置

替换元素直接赋值即可

列表可以嵌套

```python
 s = ['python', 'java', ['asp', 'php'], 'scheme']
```

类型可以不同

```python
L = ['Apple', 123, True]
```

### 切片

list[:-1]不包含最后一个元素

list[:]全部列表

list[::]全部列表

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161203-1e12zsd.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161212-0lrqjsm.png)

前10个数，每两个取一个

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161428-r6muafj.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012161441-eoc8y55.png)

#### 列表生成

list（range（1，11））生成10个数1-10

```python
print([m+n for m in '123' for n in 'yza'])
```

```python
k=[1,1,23,45,56,[1,12,3,467,[2,4,4,3,22]]]
print([x for x in k if x==1 ])
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012190810-l1qtxiv.png)

## tuple元组

tuple一旦初始化就不能修改

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009163638-1vpldee.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009163652-xkas3o0.png)

但元组初始化后就不能进行更改了

```python
b=(1)
#定义的不是tuple，是1这个数！
# 这是因为括号()既可以表示tuple，又可以表示数学公式中的小括号，
# 这就产生了歧义，因此，Python规定，
# 这种情况下，按小括号进行计算，计算结果自然是1
print(b)
print(type(b))
c=(1,)
print(c)
print(type(c))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009164221-xl1husx.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009164244-780v78f.png)

## dict字典

其他语言叫map，使用键-值（key-value）存储，具有极快的查找速度。dict的key必须是**不可变对象**。key计算位置的算法称为哈希算法（Hash）。

### 定义

```python
d={'name':'ruanyifen','age':60,'happy':'write'}
d['add']='Im add'
d['name']='fix'
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135019-kqmsrcg.png)

### 取value

#### dict['key']

#### 'key' in dict

#### dict.get('key')

```python
print(type(d))
print(d['name'])
print('name' in d)#方法一判断是否有这个主键在字典d中
print(d.get('name'))#方法二 取
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135119-sniqpw0.png)

### dict.pop('key')删除一个key

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135429-m36ygpu.png)

### dict.keys返回字典中所有key列表

### dict.update()将a字典新key，value内容加入b字典中

```bash
dicta={"name":'ruan','age':20}
dictb={"name":'ruan2','age':40,'add':'w shi add'}
dictb.update(dicta)
print(dictb)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115242-qazr588.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115348-bb0l147.png)

#### 内建函数使用

type（）

cmp（）

len（）

hash（）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114202-rdvz2pt.png)

内建cmp（）函数比较两个dict时，先比较长度，后比值，输出1或-1

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114401-h4f1qop.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101114644-qffksiw.png)

### dict特点

dict有以下几个特点：

1. 查找和插入的速度极快，不会随着key的增加而变慢；
2. 需要占用大量的内存，内存浪费多。

而list相反：

1. 查找和插入的时间随着元素的增加而增加；
2. 占用空间小，浪费内存很少。
   ![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115427-fu3s2zu.png)
   ![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115451-utxi9ct.png)

## set集合

也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

重复元素在set中自动被过滤

### 定义

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135934-u0n1j77.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012135953-sqa88s1.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140114-5azj1sa.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140127-ledkv1s.png)

### set.add('key')添加元素

但重复元素不添加，自动去重

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140336-dwf2vgw.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140344-dzsshz2.png)

### set.remove('key')删除元素

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140511-5f9cwm4.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140517-f6iolow.png)

set可以看成数学意义上的无序和无重复元素的集合，

因此，两个set可以做数学意义上的交集、并集等操作：

### & 两个set交集

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140903-1l3we66.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140912-8itf6ek.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022170721-h5hmgxr.png)

### |两个set并集

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140922-5bjlj5g.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012140933-edbys90.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022171729-b4k8xhd.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211101115701-3dt5x4j.png)

### map()的显示

打印map对象可以看到map对象返回的是一个地址，不是真实的数据

```python
print(list(map对象))
print([it for it in map对象])
```

## 数据类型转换

### int（）

### float（）

### str（）

### bool（）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142636-iblnu9y.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142645-gb2u1fg.png)

## 条件判断

### if

if else

```python
a=100
if a>=0:
    print(a)
else:
    print(-a)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165335-jr8xtfq.png)

if

```python
if True:
    print('True')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165309-ymhiihv.png)

if elif elif else

```python
name='zhangsan'
if name=='zhangsan':
    print('我是',name)
elif name=='lisi':
    print('我是', name)
elif name=='wangwu':
    print('我是', name)
else:
    print('我谁的不是')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009165511-spws02g.png)

## input（）输入输出

input()返回的数据类型是str

print（）

## 循环 迭代

list，tuple，dict都可循环

Python的 `for`循环本质上就是通过不断调用 `next()`函数实现的,计算是惰性的

dict循环按照value时：for value in dict.values

```python
for value in d.values():
    print(value)
```

### for in

```python
sum=0
for i in range(1,100):
    sum=sum+i
print(sum)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172805-wrb6kr2.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172805-wrb6kr2.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172821-rdyglwd.png)

### while

```python
sum2=0
k=0
while(k<100):
    sum2=sum2+k
    k=k+1
print(sum2)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009172821-rdyglwd.png)

### break

如果要提前结束循环，可以用 `break`语句

### continue

通过 `continue`语句，跳过当前的这次循环，直接开始下一次循环

## 生成器

在Python中，这种一边循环一边计算的机制，称为生成器：generator。

包括生成器和带 `yield`的generator function。

```python
 g = (x * x for x in range(10))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012191035-5wbqtm5.png)

访问大文件

yield

## isinstance（）迭代器

直接作用于 `for`循环的对象统称为可迭代对象，都是迭代器 Iterable

`list`、`tuple`、`dict`、`set`、`str`

`list`、`dict`、`str`虽然是 `Iterable`，却不是 `Iterator`。

`list`、`dict`、`str`等 `Iterable`变成 `Iterator`可以使用**iter()**函数

以直接作用于 `for`循环的数据类型有以下几种：

一类是集合数据类型，如 `list`、`tuple`、`dict`、`set`、`str`等；

一类是 `generator`，包括生成器和带 `yield`的generator function。

可以使用**isinstance()**判断一个对象是否是 `Iterable`对象__iter__：

迭代对象

判断是不是可以迭代，用Iterable

```python
from collections import Iterable
isinstance({}, Iterable) --> True
isinstance((), Iterable) --> True
isinstance(100, Iterable) --> False
```

判断是不是迭代器，用Iterator

```python
from collections import Iterator
isinstance({}, Iterator)  --> False
isinstance((), Iterator) --> False
isinstance( (x for x in range(10)), Iterator)  --> True
```

Python中 list，truple，str，dict这些都可以被迭代，但他们并不是迭代器，为什么：：因为和迭代器相比有一个很大的不同，list/truple/map/dict这些数据的大小是确定的，也就是说有多少事可知的。但迭代器不是，迭代器不知道要执行多少次，所以可以理解为不知道有多少个元素，每调用一次next()，就会往下走一步，是惰性的。

## 函数

抽象

将函数抽象成一个函数名称，不看内部结构直接调用方法

返回类型 函数名（输入参数）：

函数体

### 调用函数

要调用一个函数，需要知道函数的名称和参数

绝对值abs

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142010-d503sa9.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012142024-cscdoiu.png)

### 定义函数

```python
def myabs(x):
    if x>0:
        return x
    if x<0:
        return -x
print(myabs(-100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144653-0ds9bc4.png)

### 空函数

```python
def nufun():
    pass
```

`pass`可以用来作为占位符

### 函数 参数检查

```python
def my_init_abs(x):
    if not isinstance(x,(int,float)):
        raise TypeError('no no no')
    else:
        if x>0:
            print(x)
        if x<0:
            print(-x)
my_init_abs(-90)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144640-6xnfm9s.png)

### 可返回多个值，函数

```python
def return_much():
    a='返回'
    b='我也返回'
    c='我也要返回'
    return a,b,c
print(return_much())
print(type(return_much()))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012144955-kyvotx4.png)

### 函数参数

***args是可变参数，args接收的是一个tuple；**

****kw是关键字参数，kw接收的是一个dict**。

`power(x)`函数，参数 `x`就是一个位置参数，可单个变量，list，set，tuple

`power(*x)`函数，可传入单个变量，list，set，tuple，可以传入任意个参数或0个参数

`power(**kw)`函数,字典dict

可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。

而关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个**dict**.

`power(x, n)`，用来计算x^n^

`power(x, n)`函数有两个参数：`x`和 `n`

默认参数，此时age和city为默认参数，可传值改变也可不变【不用传值】

`power(L=None)`函数有None这个不变对象，可用list

```python
def enroll(name, gender, age=6, city='Beijing'):
    print('name:', name)
    print('gender:', gender)
    print('age:', age)
    print('city:', city)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012151610-9n1rxhq.png)

#### 必选参数

```python
def a1(x):
    return x
print(a1(2))
print(a1(12.1))
print(a1('ruan'))
print(a1(True))
print(a1([1,2,3]))
print(a1({1,2,3}))
print(a1({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012153014-r27ykfm.png)

#### =默认参数

```python
def a2(x=9):
    return x
print(a2())
print(a2(2))
print(a2(12.1))
print(a2('ruan'))
print(a2(True))
print(a2([1,2,3]))
print(a2({1,2,3}))
print(a2({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012153014-r27ykfm.png)

#### *可变参数

```python
def a3(*x):
    return x
print(a3())
print(a3(2))
print(a3(12.1))
print(a3('ruan'))
print(a3(True))
print(a3([1,2,3]))
print(a3({1,2,3}))
print(a3({"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012154346-2eahz0b.png)

#### **关键字参数

```python
def a3(**kw):
    return kw
print(a3())
print(a3(kw=2))
print(a3(kw=12.1))
print(a3(kw='ruan'))
print(a3(kw=True))
print(a3(kw=[1,2,3]))
print(type(a3(kw=[1,2,3])))
print(a3(kw={1,2,3}))
print(type(a3(kw={1,2,3})))
print(a3(kw={"key":"vleaue",'name':'ruan','mun':23}))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012154409-tp9u2z5.png)

### 递归函数

在函数内部，可以调用其他函数。

一个函数在**内部调用自身本身**，这个函数就是**递归函数**。

使用递归函数需要**注意防止栈溢出**

```python
#递归函数
def funmyself(x):
    if x>1:
        return x+funmyself(x-1)
    elif x==1:
        return 1
print(funmyself(3))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012155139-884p9as.png)

解决栈溢出方法：

**尾递归**优化，事实上尾递归和循环的效果是一样的

尾递归是指，在函数返回的时候，**调用自身**本身，并且，**return语句不能包含表达式**

```python
#尾递归
def funmyself2(n):
    return  funmyself2_it(n,1)

def  funmyself2_it(n,pro):
    if n==1:
        return pro
    else:
        return funmyself2(n-1)+n
print(funmyself2(100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211012160333-tngb33o.png)

此时funmyself2是尾递归函数

## 转义字符 `\`

转义字符 `\`可以转义很多字符，比如

`\n`表示换行，

`\t`表示制表符，

字符 `\`本身也要转义，所以 `\\`表示的字符就是 `\`

Python还允许用 `r''`表示 `''`内部的字符串默认不转义

## 运算符and、or和not

运算优先级：not>or>and

## 除法 / //

```python
print(10/3)
print(10//3)
```

#### 除法一 / 浮点数

#### 除法二  //  地板除 整数

`/`除法计算结果是浮点数，即使是两个整数恰好整除，结果也是浮点数：

`//`，称为地板除，两个整数的除法仍然是整数：

## 取余 %

```python
print(10%1)
print(10%3)
print(4%7)
print(2%20)
#如果a%b a>b 则结果为a
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009141744-i2nxg58.png)

## 字符编码

`ASCII`编码

8个比特（bit）作为一个字节（byte）

一个字节能表示的最大的整数就是255（二进制11111111=十进制255）

两个字节可以表示的最大整数是 `65535`，4个字节可以表示的最大整数是 `4294967295`

大写字母 `A`的编码是 `65`，二进制的 `01000001`，小写字母 `z`的编码是 `122`

Unicode把所有语言都统一到一套编码里，这样就不会再有乱码问题

ASCII编码是1个字节，而Unicode编码通常是2个字节

**ASCll出现乱码问题引入Unicode编码存储空间多了一倍引入UTF-8编码**

utf-8：将**Unicode字符根据不同的数字大小编码成1-6个字节，常用的英文字母被编码成1个字节，汉字通常是3个字节，**

| 字符 | ASCII    | Unicode           | UTF-8                      |
| ---- | -------- | ----------------- | -------------------------- |
| A    | 01000001 | 00000000 01000001 | 01000001                   |
| 中   | x        | 01001110 00101101 | 11100100 10111000 10101101 |

在计算机内存中，统一使用Unicode编码，当需要保存到硬盘或者需要传输的时候，就转换为UTF-8编码。

用记事本编辑的时候，从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009142650-uopgqob.png)

浏览网页的时候，服务器会把动态生成的Unicode内容转换为UTF-8再传输到浏览器：

![web-utf-8](https://www.liaoxuefeng.com/files/attachments/923923759189600/0)

#### compile() 字符串编译为字节代码

#### 编码转化

#### ord('A') 字母转字符

#### chr(65) 字符转字母

```python
a=ord('A')
b=chr(65)
print(a,b)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009144810-rm45nsz.png)

#### b'str'转为字节类型bytes

`bytes`类型的数据用带 `b`前缀的单引号或双引号表示

```python
x = b'ABC'
```

要注意区分 `'ABC'`和 `b'ABC'`，前者是 `str`，后者虽然内容显示得和前者一样，但 `bytes`的每个字符都只占用一个字节。

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009145112-3dmegln.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150224-kn57ioe.png)

#### str.encode('ascii') `str` 变为 `bytes `

`ASCII`

`UTF-8`

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150118-wy36xea.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150204-81jvyjd.png)

#### str.decode('utf-8')`bytes`变为 `str`

```python
print(type(b'abc'))
print(b'abc'.decode('utf-8'))
print(type(b'abc'.decode('utf-8')))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150844-zvt6jkv.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009150746-31uq63m.png)

len（str）计算字符数

函数计算的是 `str`的字符数，如果换成 `bytes`，`len()`函数就计算字节数

```python
print(len('abc'))
print(len(b'abc'))
print(len('中'))
print(len('中'.encode('utf-8')))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009151234-rhao6fv.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009151321-6k73tn8.png)

## 特殊注释

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
```

第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，**Windows系统会忽略这个注释**；

第二行注释是为了告诉Python解释器，**按照UTF-8编码读取源代码**，否则，你在源代码中写的中文输出可能会有乱码。

## 占位符 格式化

### 占位符%s %d %f

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152324-rmac8lz.png)

格式化方式和C语言是一致

` %`运算符就是用来格式化字符串的。

在字符串内部，

`%s`表示用字符串替换，

`%d`表示用整数替换，

有几个 `%?`占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个 `%?`，括号可以省略

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152708-zy7vi8x.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009152722-wq5flos.png)

| 占位符 | 替换内容     |
| ------ | ------------ |
| %d     | 整数         |
| %f     | 浮点数       |
| %s     | 字符串       |
| %x     | 十六进制整数 |

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009153422-r1s8f5z.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009153433-1uhb1w3.png)

转义：`%%`来表示一个 `%`

### format（）格式化字符串

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154141-a3v7tnj.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154153-o6u9yd7.png)

### f-string 格式化字符串

`{r}`被变量 `r`的值替换，`{s:.2f}`被变量 `s`的值替换，并且 `:`后面的 `.2f`指定了格式化参数（即保留两位小数），因此，`{s:.2f}`的替换结果是 `19.62`

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154406-qahm3f7.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211009154432-m2z0xx5.png)

## 函数式编程

函数是Python内建支持的一种封装，通过层层函数进行调用

#面向过程的程序设计#：把复杂任务分解成简单的任务，这种分解可以称之为面向过程的程序设计

函数式和函数的区别：

对比例子：计算和计算器的区别

编程语言，就是越低级的语言，越贴近计算机，抽象程度低，执行效率高，比如C语言；越高级的语言，越贴近计算，抽象程度高，执行效率低，比如Lisp语言

Python不是纯函数式编程语言

函数式编程就是一种抽象程度很高的编程范式，

纯粹的函数式编程语言编写的**函数没有变量**，因此，任意一个函数，**只要输入是确定的，输出就是确定的**

### 函数式编程特点：

1. 纯函数式编程语言函数没有变量，输入输出确定
2. 允许本身作为参数传入另一个函数，允许返回一个函数

## 高阶函数

参数中有函数

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回

### 变量可以指向函数

a=函数

求绝对值的函数 `abs()`为例

```python
print(abs(-10))
print(abs)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019114343-h6egecv.png)

abs（-10）是函数调用，abs是函数本身

```python
k=abs(-20)
print(k)
#函数本身也可以赋值给变量
h=abs
print(h)
print(h(-100))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019114757-z778j3c.png)

结论：函数本身也可以赋值给变量，即：#变量可以指向函数。#

### 函数名也是变量

#函数名#：**其实就是指向函数的变量**

a()中a是指向函数a（）的变量

### 传入函数

既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

#高阶函数#：**一个函数就可以接收另一个函数作为参数**

b()

a(b)

x=a

```python
def f(x):
    return abs(int(x))
def a(a,b,f):
    return f(a)+f(b)
if __name__ == '__main__':
    a1=input('a')
    a2=input('b')
    print(a(a1,a2,f))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019115835-q2esytb.png)

此时函数a为高阶函数，需要调用f函数作为参数

## map/reduce 内建函数

内建了 `map()`和 `reduce()`函数 高阶函数

### map（）函数处理生成新Iterator迭代器

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019131933-ut47b16.png)两个参数，函数名【函数本身】，需要处理的编程式iterator

`<br />`创建一个迭代器，使用每个迭代器中的参数计算函数。当最短迭代用尽时停止。

```python
 map(func, *iterables) --> map object
```

```python
def f(x):
    return x*x
r=map(f,[1,2,3,4,4,4,4,4,4,4,4])
print(r)
print(type(r))
print(list(r))
print(type(list(r)))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019133740-kxaifya.png)

运算规则抽象

### reduce（）函数作用在序列上

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019142951-sxqvxp4.png)

两个参数，函数名【函数本身】，需要处理的#序列#： sequence(序列)是一组有顺序的元素的集合

序列基本样式[下限:上限:步长]

`reduce`把结果继续和序列的下一个元素做累积计算

```python
reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```

```python
from functools import reduce
>>> def fn(x, y):
...     return x * 10 + y
...
>>> reduce(fn, [1, 3, 5, 7, 9])
13579
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211019142820-4tlrn7x.png)

## filter()过滤序列

参数和map（）相似

`filter()`也接收一个函数和一个序列

## sorted（）排序

高阶函数![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184319-dzvm55o.png)

参数：排序对象，key=函数

```bash
sorted([36, 5, -12, 9, -21], key=abs)
```

排序的核心是比较两个元素的大小

```bash
print(sorted([1,2,353,6,3,234,43,435]))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184421-43dcfax.png)

key指定绝对值大小排序

```bash
print(sorted([1,2,353,6,3,234,43,435,-242,-34,34,35],key=abs))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211020184629-q7j7zxx.png)

## 返回函数

### 函数作为返回值

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回

```bash
# 如果不需要立刻求和，而是在后面的代码中，
# 根据需要再计算怎么办？可以不返回求和的结果，而是返回求和的函数：
def zary_sum(a):
    def sum():
        sum1=0
        for i in a:
            sum1=sum1+i
        return sum1
    return sum
print(type(zary_sum([1,2,3,4])))
f=zary_sum([1,2,3,4])
print(f())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100621-oot0dd6.png)

调用返回函数时，每次调用都会新生成一个函数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100747-ho01xzp.png)

## 闭包

当一个函数的返回值是另外一个函数，

而返回的那个函数如果调用了其父函数内部的其它变量，如果 **返回的这个函数在外部被执行，就产生了闭包** 。

**返回函数中，返回的函数调用父函数的内部变量**

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021100950-gl5liu8.png)

```bash
#返回函数
def count():
    fs=[]
    for i in range(1,4):
        def f():
            return i*i
        fs.append(f)
    return fs
f1,f2,f3=count()
print(f1(),f2(),f3())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021103727-wtd0kdc.png)

返回一个函数时，牢记该函数并未执行，返回函数中不要引用任何可能会变化的变量。

## lambda（）匿名函数

lambda关键字 函数参数：函数表达式

传入函数时，有些时候，不需要显式地定义函数

Python对匿名函数的支持有限，只有一些简单的情况下可以使用匿名函数。

```bash
lambda x:x*x
#等价于
def f(x):
   return x*x
```

关键字 `lambda`表示匿名函数，冒号前面的 `x`表示函数参数，只能一个表达式

不用写 `return`，返回值就是该表达式的结果。

匿名函数也是一个函数对象

```bash
f=lamdba x:x*x
```

判断奇数函数

原函数：

```bash
def is_odd(n):
    return n % 2 == 1

L = list(filter(is_odd, range(1, 20)))
```

采用匿名函数修改

```bash
l=list(filter(lambda x:x%2==1,range(1,20)))
print(l)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211021143505-wbqh836.png)

## 装饰器 Decorator

### 本质上，装饰器就是一个返回函数的高阶函数

@log 等价于

```bash
now = log(now)
```

由于函数也是一个对象，而且函数对象可以被赋值给变量，

所以，通过变量也能调用该函数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022101101-ncgju0i.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022101111-tgdwt0q.png)

```bash
def log(func):
    def wrapper(*args,**kwargs):
        print('call %s'% func.__name__)
        return func(*args,**kwargs)
    return wrapper()
#func为参数所以是高阶函数
#return 函数所以是返回函数，
#没有调用父函数中参数，所以不是闭包
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022110733-h27x1zh.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022110058-zyo7xpn.png)

场景注意：

无@装饰器时函数不调用，需要参数才调用

当@时会直接调用装饰器定义函数然后执行函数，不用调用函数

三层时，传入参数

```bash
def log1(text):
    def decorator(func):
        def wapper(*args,**kw):
            print('%s %s'%(text,func.__name__))
            return func(*args,**kw)
        return wapper
    return decorator
@log1('ruan')
def now3():
    print("hhh")
now3()
```

相当于在返回高阶函数上还有一个函数，所以返回时应该还要调用一次

## @wraps 常用装饰器

当装饰器是个闭包时，装饰器调用变量会改变增加@wraps后装饰器内的变量不变

装饰器在装饰一个函数时,，原函数就成了一个新的函数,也

就是说其属性会发生变化,所以为了 **不改变原函数的属性** ,

我们会调用functools中的wraps装饰器来保证原函数的属性不变

#### 不加wraps时

```bash
  @wraps(func)
```

```bash
from functools import wraps
def wrap(func):
   
    def b():
        'b'
        print('decorator:',b.__name__)
        print('funname',func.__name__)
        func()
    return b
@wrap
def a():
    'a'
    print('name',a.__name__)
a()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022115935-kgsz7b2.png)

加装饰器wraps时

```bash
from functools import wraps
def wrap(func):
    @wraps(func)
    def b():
        'b'
        print('decorator:',b.__name__)
        print('funname',func.__name__)
        func()
    return b
@wrap
def a():
    'a'
    print('name',a.__name__)
a()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211022115950-2j3i7ht.png)

闭包的概念：调用父函数中的变量的函数，为了保证数据安全。变量作用域只在函数内部，可在闭包中操作数据。

装饰器返回为什么是函数名（函数内存地址）而不直接执行函数?

当有参数传入时，可直接与调用的函数中的值传入参数执行。

（）是运算符f()与f.__call__()等价：将f对象变成变成可调用的对象

## 偏函数（functools模块）

属于functools模块

### 作用：

通过设定参数的默认值，降低函数调用的参数

`int()`函数默认按十进制转换

print(int('100',base=8))

经常调用于是重写一个函数int2

```bash
def int2(x, base=8):
    print(int(x, base))
    return int(x, base)
print(int2('2334'))
```

采用偏函数

```bash
import functools
int3=functools.partial(int,base=8)
print(int3('46'))
print(int())
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028103219-mdbldp6.png)

functools.partial的作用是将函数的特定参数固定住（设定为默认值）

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028103645-7po81oc.png)

创建偏函数的时候也可以接收，函数对象，*args，**kw

## 模块

python包：作用区分相同名称的模块

模块相当于一个py文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028105055-2xv0z2i.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028105133-tkzgcka.png)

## 作用域

仅仅在模块内部使用。在Python中，是通过 `_`前缀来实现的。

### pubilc公开

正常的函数和变量名是公开的（public）

### private非公开_,__

_xxx和__xxx这样的函数或变量就是非公开的（private）

## 安装第三方模块pip

pip install 模块名

### 模块搜索路径

```bash
import sys
print(sys.path)
```

两种方式：

1. 添加搜索路径
   ```bash
    import sys
   sys.path.append('/Users/michael/my_py_scripts')
   ```
2. 设置环境变量

第二种方法是设置环境变量 `PYTHONPATH`

## 面向对象编程

面向对象编程——Object Oriented Programming，简称OOP，是一种程序设计思想

对象作为程序的基本单元，

一个对象包含了数据和操作数据的函数

数据封装、继承和多态是面向对象的三大特点

## 类和实例

面向对象最重要的概念就是类（Class）和实例（Instance）

类是抽象出来的模板

实例是根据类创建出的对象，每个对象可能有属性和方法

定义类是通过 `class`关键字，类名通常是大写开头的单词

```bash
class Student(object):
    pass
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028113324-1nch2o5.png)

！！！在类中定义函数有一点不同，定义佛如方法第一个参数永远是实例变量本身self

仍然可以用默认参数、可变参数、关键字参数和命名关键字参数

## 数据封装

```bash
class Student(object):
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def get_grade(self):
        if self.score >= 90:
            return 'A'
        elif self.score >= 60:
            return 'B'
        else:
            return 'C'
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028113713-vhhvowi.png)

## 访问限制

### 作用：

**确保了外部代码不能随意修改对象内部的状态**

实例的变量名如果以 `__`开头，就变成了一个私有变量（private）

外部无法访问_name

```bash
class Student(object):
    def __init__(self,name,age):
        self._name=name
        self.age=age
    def print_name(self):
        print(self._name)
        return self.age,self._name
a=Student('ruan',23)
h=a.print_name()
print(h)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211028114732-awu2k2m.png)

若是要获取，修改变量增加get，set方式即可

```bash
class Student(object):
    def __init__(self,name,age):
        self._name=name
        self.age=age 
    def get_name(self):
        return self.name
    def set_name(self,name):
        self._name=name
```

Python本身没有任何机制阻止你干坏事，一切全靠自觉。

类外部无法访问

## 继承和多态

### 继承

#### 多态

在继承关系中，如果一个实例的数据类型是某个子类，那它的数据类型也可以被看做是父类。

比如：动物是父类，狗和鱼是子类；鱼是鱼类，鱼是动物都成立。

判断一个变量是否是某个类型可以用 `isinstance()`判断

### 鸭子类型

并不要求严格的继承体，一个对象只要“看起来像鸭子，走起路来像鸭子”，那它就可以被看做是鸭子。

## 获取对象信息

### type（）判断对象类型

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211102183643-gwgjuho.png)

### isinstance()对于继承关系，判断class的类型

### dir（）获取对象的所有属性和方法

#### len（）对象长度

#### lower（）返回小写的字符串

#### getattr（）获取属性a

#### setattr（）设置属性a

#### hasattr（obj,'a'）判断是否有属性a

```bash
getattr(obj, 'z', 404) # 获取属性'z'，如果不存在，返回默认值404
404
```

## 实例属性和类属性

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211102184822-83nvy25.png)

```bash
 class Student(object):
    name='ruan'
   
h=Student()
h.name='hhh'

```

类中的name是类属性，

创建h类对象即实例后赋值的是实例属性name，但由于实例对象的优先级比类属性高，会屏蔽类中的name属性，即h.name的值为hhh

### 总结：

1. 实例属性属于各个实例所有，互不干扰；
2. 类属性属于类所有，所有实例共享一个属性；
3. 不要对实例属性和类属性使用相同的名字，否则将产生难以发现的错误

# 面向对象高级编程

数据封装、继承和多态只是面向对象程序设计中最基础的3个概念

多重继承、定制类、元类

# _slots_使用

可以给创建的实例绑定属性和方法

给一个实例绑定的方法对另外一个实例对象是不起作用的

```bash
class A:
    def run(self):
        print("i im ferther runing....")
sun1=A()
#给实例sun1设置name属性
sun1.name='i im name'
#创建实例对象2
sun2=A()
#实例对象sun1的属性和sun2无关，即sun2没有name属性
#给实例sun1绑定方法，方法和属性同理
#定义方法
def setAll(self,num):
    print(num)
sun1.newfun=MethodType(setAll, sun1)
sun1.newfun(37)
#若所有实例都需要绑定方法则给类绑定方法
A.setAll=setAll
#给类绑定方法后，所有创建的实例的均可调用
```

```
def set_age(self, age): # 定义一个函数作为实例方法
...     self.age = age
...
>>> from types import MethodType
>>> s.set_age = MethodType(set_age, s) # 给实例绑定一个方法
>>> s.set_age(25) # 调用实例方法
```

## 限制实例属性，定义一个特殊的 `__slots__`变量

```python
class Student(object):
    __slots__ = ('name', 'age') # 用tuple定义允许绑定的属性名称
s=Student()
s.name='ruan'
s.firstname='i im firstname'
#输出的时候firstname的属性会报错，
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Student' object has no attribute 'firstaname'
```

### 注意：

_slots_使用时要注意，定义的属性只在当前的类的实例中，对于继承的子类是不起作用的

```python
class People(object):
    __slots__ = ('name','age')
    def run(self):
        print('i im run people......')

class Teacher(People):
    def say(self):
        print('i im teacher....')
t=Teacher()
t.tall='shouhua'
print(t.tall)
p=People()
p.tall('shouhuap')
print(p.tall)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103140608-7ezqmvs.png)

只限制父类People的属性，而子类Teacher中不限制

## @property

在绑定属性时，如果我们直接把属性暴露出去,导致可以随意更改.通过get，set来获取更改属性值。

在python中直接调用装饰器将一个方法变成属性调用

```python
class Student(object):
    @property
    #使用get方法是调用装饰器@peoperty，
    # 同时自动创建了另一个装饰器@属性.setter
    def score(self):
        return self.score
    @score.setter
    def score(self,value):
        self._score=value
```

## 总结：

-权限限制只对类对象实际起作用，想要达到方法和属性强制访问权限，需要使用@property装饰器进行get，set方法

属性名与方法名一定要区分开，不然会进入死循环（self._age，def age()）
实例化的对象使用属性时，不是调用属性（meizi._age），而是用的方法名（meizi.age）
@property其实就是实现了getter功能； @xxx.setter实现的是setter功能；还有一个 @xxx.deleter实现删除功能
定义方法的时候 @property必须在 @xxx.setter之前，且二者修饰的方法名相同（age()）
如果只实现了 @property（而没有实现@xxx.setter），那么该属性为 只读属性

```python
#请利用@property给一个Screen对象加上width和height属性，
# 以及一个只读属性resolution：
class Screen(object):
    __slots__ = ('_width','_height','_resolution')

    @property
    def width(self):
        return self._width

    # 方法名称和实例变量均为width:
    @width.setter
    def width(self,widthValue):
        self._width=widthValue

    @property
    def height(self):
        return self._height

    @width.setter
    def height(self, height):
        self._height = height

    @property
    def resolution(self):
        return self._width * self._height
s=Screen()
s.width=23
s.height=12

print(s.resolution)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103150647-dge6za2.png)

```python
s.score = 60 # OK，实际转化为s.set_score(60)
s.score # OK，实际转化为s.get_score()
```

要特别注意：属性的方法名不要和实例变量重名。例如，以下的代码是错误的：

```
class Student(object):

    # 方法名称和实例变量均为birth:
    @property
    def birth(self):
        return self.birth
```

出现递归调用错误

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103151046-5z499ew.png)

之前的例子中width和_width不同所以可以运行

## 多重继承

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103151750-dvwa7qb.png)

python可以支持多继承，即一个子类可以继承多个父类；但java是单继承，只能有一个父类

Tercher（Name，study，teach）即Teacher可以继承多个父类

### MixIn

在设计类的继承关系时，通常，主线都是单一继承下来的，例如，`Teacher`继承自Name。但是，如果需要“混入”额外的功能，通过多重继承就可以实现，比如Teacher除了继承自 `Name`外，再同时继承 `Teach`。这种设计通常称之为MixIn

Python自带了 `TCPServer`和 `UDPServer`这两类网络服务，而要同时服务多个用户就必须使用多进程或多线程模型，这两种模型由 `ForkingMixIn`和 `ThreadingMixIn`提供。

### 多继承

多重继承这个名词一般用来形容继承链条可以很长，多个层次。

### 多重继承

**多继承则指一个类可以有多个基类，相反则是单继承**。任何面向对象编程语言都支持多重继承，但像java这种只能通过接口实现有限程度的多继承

问：多继承 如果多个类有共同得方法名 怎么区分是调得哪个类🤡

答：调用该方法的时候，会调用第一顺位继承父类的方法

### 总结：

1. Python允许使用多重继承，因此，MixIn就是一种常见的设计
2. 只允许单一继承的语言（如Java）不能使用MixIn的设计

## 定制类

Python的class中还有__xxx__有特殊用途的函数，可以帮助我们定制类

### __str__()回用户看到的字符串

将对象 `<__main__.Student object at 0x109afb190>`变成易读的数据

只在调用print时会调用__str__，交互界面时还是现实上方不易读的对象内容，此时用

### __repr__()返回程序开发者看到的字符串

`__str__()`返回用户看到的字符串，而 `__repr__()`返回程序开发者看到的字符串，

也就是说，`__repr__()`是为调试服务的

简写

```python
def __str__(self):
        return 'xxx object (name=%s)' % self.name
__repr__ = __str__
```

### ___iter__()返回一个迭代对象

需要用到for in迭代，需要转化为迭代对象

该方法返回一个迭代对象，然后，Python的for循环就会不断调用该迭代对象的 `__next__()`方法拿到循环的下一个值，直到遇到 `StopIteration`错误时退出循环

例子：

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
a=Fib()
for i in a:
    print(i)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155046-1xs33i9.png)

### __**getitem**__()表现得像list那样按照下标取出元素

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
    def __getitem__(self, item):
        a,b=1,1
        for i in range(item):
            a,b=b,a+b
        return a
a=Fib()
print(a[3])

```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155122-fo5pjxz.png)

以上是传入int，切片功能实现，isinstance判断类型

```python
class Fib(object):
    def __init__(self):
        self.a,self.b=0,1
    def __iter__(self):
        return self
    def __next__(self):
        self.a,self.b=self.b,self.a+self.b
        if self.a>1000:
            raise  StopIteration
        return self.a
    def __getitem__(self, item):
        if isinstance(item,int):
            a, b = 1, 1
            for i in range(item):
                a, b = b, a + b
            return a
        if isinstance(item,slice):
            start=item.start
            stop=item.stop
            if start is None:
                start=0
            a,b=1,1
            L=[]
            for x in range(stop):
                L.append(a)
                a,b=b,a+b
        return L

a=Fib()
print(a[3:12])
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211103155838-wdwjies.png)

### __getattr__()动态返回一个属性

调用类属性或方法时，先在__init__()获取后，再从__getattr__()获取，获取不到才报错

### __call__()直接调用实例本身

与直接调用这个函数一样

```python
class People(object):
    def __init__(self,name):
        self.name=name
    def __call__(self, *args, **kwargs):
        print('i im call %s'% self.name)

p=People('ruan')
p()
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104150832-d8wkn0m.png)

## 使用枚举类

枚举类：在某些情况下，一个类的 实例对象 的**数量**是 **有限且固定** 的，如季节类，它的实例对象只有春、夏、秋、冬。 在Java中像这种对象实例有限且固定的类被称为枚举类；这样的枚举类型定义一个class类型，然后，每个常量都是class的一个唯一实例。Python提供了 `Enum`类来实现这个功能。

```python
from enum import Enum
M=Enum('a',('sun1','sun2','sun3','sun4'))
print(M.sun1)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104151622-x7yqw9j.png)

自定义枚举类

```python
from enum import Enum,unique
@unique
class Week(Enum):
    sun1=1
    sun2=2
    sun3=3
day2=Week.sun2
print(day2)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104152125-y6nm9vn.png)

```python
from enum import Enum,unique
@unique
class Gender(Enum):
    Male=0
    Female=1
class Student(object):
    def __init__(self,name,gender):
        self.name=name
        self.gender=gender

# 测试:
bart = Student('Bart', Gender.Male)
if bart.gender == Gender.Male:
    print('测试通过!')
else:
    print('测试失败!')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104152731-wmdziil.png)

## 使用元类[创建类]

实例对象是类创建

类是元类创建

创建类的方式

### 方式一：type（）

`type()`函数既可以返回一个对象的类型，又可以创建出新的类型，比如，我们可以通过 `type()`函数创建出 `Hello`类

```python
from class1104 import *
h=Hello()
print(type(h))
print(type(Hello))
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104153538-6iulybe.png)

```python
 Hello = type('Hello', (object,), dict(hello=fn))
```

要创建一个class对象，`type()`函数依次传入3个参数：

1. class的名称；
2. 继承的父类集合，注意Python支持多重继承，如果只有一个父类，别忘了tuple的单元素写法；
3. class的方法名称与函数绑定，这里我们把函数 `fn`绑定到方法名 `hello`上

### 方式二：元类metaclass

先定义metaclass，然后创建类。

先定义类，然后创建实例。

~~metaclass是Python面向对象里最难理解，也是最难使用的魔术代码。~~

按照默认习惯，metaclass的类名总是以Metaclass结尾，以便清楚地表示这是一个metaclass

```python
# metaclass采用type创建类 ，metaclass是类的模板，所以必须从`type`类型派生
class ListMetaclass(type):
    def __new__(cls, name,bases,attrs):
        attrs['add']=lambda self, value:self.append(value)
        return type.__new__(cls,name,bases,attrs)

class MyList(list,metaclass=ListMetaclass):
    pass
mylist=MyList()
mylist.add(1)
print(mylist)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104155010-cbldtfp.png)

`__new__()`方法接收到的参数依次是：

1. 当前准备创建的类的对象；
2. 类的名字；
3. 类继承的父类集合；
4. 类的方法集合

### 应用场景

ORM全称“Object Relational Mapping”，即对象-关系映射，就是把关系数据库的一行映射为一个对象，也就是一个类对应一个表，这样，写代码更简单，不用直接操作SQL语句。

要编写一个ORM框架，所有的类都只能动态定义，因为只有使用者才能根据表的结构定义出对应的类来。

## 错误处理try

```python
try:
    print('try...')
    r = 10 / 0
    print('result:', r)
except ValueError as e:
    print('ValueError:', e)
except ZeroDivisionError as e:
    print('ZeroDivisionError:', e)e)
finally:
    print('finally...')
print('END')
```

Python的错误其实也是class，所有的错误类型都继承自 `BaseException`

`UnicodeError`是 `ValueError`的子类🤡

[Built-in Exceptions — Python 3.10.0 documentation](https://docs.python.org/3/library/exceptions.html#exception-hierarchy)

## 调用栈

让Python解释器来打印出错误堆栈

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104162726-fird23x.png)

## 记录错误logging

可将logging生成一个txt方便查看

```python
 try:
        xxx
    except Exception as e:
        logging.exception(e)
```

### 抛出错误raise

```python
 except ValueError as e:
        print('ValueError!')
        raise
```

在 `bar()`函数中，我们明明已经捕获了错误，但是，打印一个 `ValueError!`后，又把错误通过 `raise`语句抛出去了，这不有病么？

其实这种错误处理方式不但没病，而且相当常见。捕获错误目的只是记录一下，便于后续追踪。但是，由于当前函数不知道应该怎么处理该错误，所以，最恰当的方式是继续往上抛，让顶层调用者去处理。

## 调试方法

### 1. print（）

### 2. 断言assert

```python
 assert n != 0, 'n is zero!'
```

`assert`的意思是，表达式 `n != 0`应该是 `True`，否则，根据程序运行的逻辑，后面的代码肯定会出错。

采用断言的好处：

启动Python解释器时可以用 `-O`参数来关闭 `assert`：

```python
$ python -O err.py
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104164034-js5sidi.png)

关闭后，你可以把所有的 `assert`语句当成 `pass`来看

### 3. logging

```python
import logging
s = '0'
n = int(s)
logging.info('n = %d' % n)
print(10 / n)
```

### 4.pbd单步执行

启动Python的调试器pdb，让程序以单步方式运行，可以随时查看运行状态。

```python
python -m pdb xxx.py
(Pbd) 1#查看第一行代码，单步执行第一行代码
```

### 5. pdb.set_trace()

这个方法也是用pdb，但是不需要单步执行，我们只需要 `import pdb`，然后，在可能出错的地方放一个 `pdb.set_trace()`，就可以设置一个断点：

```python
import pdb

s = '0'
n = int(s)
pdb.set_trace() # 运行到这里会自动暂停
print(10 / n)
```

可以用命令 `p`查看变量，或者用命令 `c`继续运行：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211104164634-anjnpuu.png)

### 6.IDE工具

vscode,pycharm....

## 单元测试

单元测试是用来对一个模块、一个函数或者一个类来进行正确性检验的测试工作。

## 文档测试

doctest非常有用，不但可以用来测试，还可以直接作为示例代码。通过某些文档生成工具，就可以自动把包含doctest的注释提取出来。用户看文档的时候，同时也看到了doctest。

Python内置的“文档测试”（doctest）模块可以直接提取注释中的代码并执行测试.

```python
class Dict(dict):
    """"
      这一段就是文档测试
       Simple dict but also support access as x.y style.

       >>> d1 = Dict()
       >>> d1['x'] = 100
       >>> d1.x
       100
       >>> d1.y = 200
       >>> d1['y']
       200
       >>> d2 = Dict(a=1, b=2, c='3')
       >>> d2.c
       '3'
       >>> d2['empty']
       Traceback (most recent call last):
           ...
       KeyError: 'empty'
       >>> d2.empty
       Traceback (most recent call last):
           ...
       AttributeError: 'Dict' object has no attribute 'empty'
       """

    def __init__(self, **kw):
        super(Dict, self).__init__(**kw)

    def __getattr__(self, key):
        try:
            return self[key]
        except KeyError:
            raise AttributeError(r"'Dict' object has no attribute '%s'" % key)

    def __setattr__(self, key, value):
        self[key] = value

if __name__ == '__main__':
    import doctest
    doctest.testmod()
```

将其中一个函数注释，运行让它报错

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108110503-erlvnk1.png)

## IO编程

程序和运行时的数据在内存中驻留

涉及到数据交换的地方，通常是磁盘、网络等，就需要IO接口

通常，程序完成IO操作会有Input和Output两个数据流

Stream（流）是一个很重要的概念，可以把流想象成一个水管，数据就是水管里的水，但是只能单向流动。

在IO编程中，就存在**速度严重不匹配的问题**。举个例子来说，比如要把100M的数据写入磁盘，CPU输出100M的数据只需要0.01秒，可是磁盘要接收这100M数据可能需要10秒，怎么办呢？有两种办法：

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108111749-yobbduz.png)

## 同步IO

第一种是CPU等着，也就是程序暂停执行后续代码，等100M的数据在10秒后写入磁盘，再接着往下执行，这种模式称为同步IO；

## 异步IO

另一种方法是CPU不等待，只是告诉磁盘，“您老慢慢写，不着急，我接着干别的事去了”，于是，后续代码可以立刻接着执行，这种模式称为异步IO。

如果是服务员跑过来找到你，这是回调模式，如果服务员发短信通知你，你就得不停地检查手机，这是轮询模式。总之，异步IO的复杂度远远高于同步IO。

## 文件读写

### 读文件open（）

传入文件名，标示符

参数：'rb' 二进制

encoding='gbk'字符编码

```python
f = open('/Users/michael/test.txt', 'r')
```

### read()一次读取全部内容

```python
 f.read()
'Hello, world!'
```

### f.close（）关闭文件

简化方法

### with open('filepath', 'r') as f:    print(f.read())

Python引入了 `with`语句来自动帮我们调用 `close()`方法，并且不必调用 `f.close()`方法

```python
with open('/path/to/file', 'r') as f:
    print(f.read())
```

如果文件很小，`read()`一次性读取最方便；

如果不能确定文件大小，反复调用 `read(size)`比较保险；

如果是配置文件，调用 `readlines()`最方便

```python
for line in f.readlines():
    print(line.strip()) # 把末尾的'\n'删掉
```

file和缓存时=是file-like Object对象，不要求从特定类继承，只要写个 `read()`方法就行

### f.write()写文件

```python
f = open('/Users/michael/test.txt', 'w')
f.write('Hello, world!')
f.close()
```

或

```python
with open('/Users/michael/test.txt', 'w') as f:
    f.write('Hello, world!')
```

使用 `with`语句操作文件IO是个好习惯

## StringIO和BytesIO

### StringIO

StringIO顾名思义就是在内存中读写str

```python
 from io import StringIO
 f = StringIO()
f.write('hello')
```

`getvalue()`方法用于获得写入后的str

```python
 from io import StringIO
>>> f = StringIO('Hello!\nHi!\nGoodbye!')
>>> while True:
...     s = f.readline()
...     if s == '':
...         break
...     print(s.strip())
```

### BytesIO

操作二进制数据，就需要使用BytesIO

```python
>>> from io import BytesIO
>>> f = BytesIO()
>>> f.write('中文'.encode('utf-8'))
6
>>> print(f.getvalue())
b'\xe4\xb8\xad\xe6\x96\x87'
```

## os模块

### os.name操作系统类型

### os.uname()详细系统信息

### os.enciron环境变量

要获取某个环境变量的值，可以调用 `os.environ.get('key')`

```python
# 查看当前目录的绝对路径:
>>> os.path.abspath('.')
'/Users/michael'
# 在某个目录下创建一个新目录，首先把新目录的完整路径表示出来:
>>> os.path.join('/Users/michael', 'testdir')
'/Users/michael/testdir'
# 然后创建一个目录:
>>> os.mkdir('/Users/michael/testdir')
# 删掉一个目录:
>>> os.rmdir('/Users/michael/testdir')
```

通过 `os.path.join()`函数，这样可以正确处理不同操作系统的路径分隔符

### `os.path.join(`)连接路径

### `os.path.split()`拆分路径

### `os.path.splitext()` 文件扩展名

```python
# 对文件重命名:
>>> os.rename('test.txt', 'test.py')
# 删掉文件:
>>> os.remove('test.py')
```

`shutil`模块提供了 `copyfile()`的函数，它们可以看做是 `os`模块的补充

最后看看如何利用Python的特性来过滤文件。比如我们要列出当前目录下的所有目录，只需要一行代码：

```
>>> [x for x in os.listdir('.') if os.path.isdir(x)]
['.lein', '.local', '.m2', '.npm', '.ssh', '.Trash', '.vim', 'Applications', 'Desktop', ...]
```

要列出所有的 `.py`文件，也只需一行代码：

```
>>> [x for x in os.listdir('.') if os.path.isfile(x) and os.path.splitext(x)[1]=='.py']
['apis.py', 'config.py', 'models.py', 'pymonitor.py', 'test_db.py', 'urls.py', 'wsgiapp.py']
```

## 序列化pickle模块

变量从内存中变成可存储或传输的过程称之为序列化,Python中叫pickling

变量内容从序列化的对象重新读到内存里称之为反序列化，即unpickling

### pickle.dumps()对象-》字节[序列化]

`pickle.dumps()`方法把任意对象序列化成一个 `bytes`

`pickle.dumps()`方法把任意对象序列化成一个 `bytes`,并写入文件中

```python
import pickle
d=dict(name='ruan',age=34,freand='woman')
# print(pickle.dumps(d))
f = open('timezone.txt', 'wb')
pickle.dump(d, f)
f.close()
```

### pickle.load()字节-》对象【反序列化】

```python
import pickle
f=open(r'C:\Users\yangs\PycharmProjects\python_study\fun\timezone.txt','rb')
d=pickle.load(f)
f.close()
print(d)
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108132946-rtt8k8p.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211108133035-b8gyft4.png)

## json模块

`json`模块的 `dumps()`和 `loads()`函数是定义得非常好的接口的典范。

#### json.dumps(python对象)python对象-》json对象

`dumps()`方法返回一个 `str`，内容就是标准的JSON

#### json.loads(json对象)json对象-》python对象

`json.``dump`(obj, fp, *, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw**)**

### 类变为字典并序列化

```python
json.dumps(s, default=lambda obj: obj.__dict__)
```

## 进程和线程

Python的标准库提供了两个模块：`_thread`和 `threading`，`_thread`是低级模块，`threading`是高级模块

**线程是最小的执行单元，而进程由至少一个线程组成**

操作系统轮流让各个任务交替执行

真正的并行执行多任务只能在多核CPU上实现

对于操作系统来说，一个任务就是一个进程（Process），比如打开一个浏览器就是启动一个浏览器进程

Word，它可以同时进行打字、拼写检查、打印等事情。在一个进程内部，要同时干多件事，就需要同时运行多个“子任务”，我们把进程内的这些“子任务”称为线程（Thread）

* 多进程模式；
* 多线程模式；
* 多进程+多线程模式。

## 多进程

Unix/Linux操作系统提供了一个 `fork()`系统调用，普通的函数调用，调用一次，返回一次，但是 `fork()`调用一次，返回两次，因为操作系统自动把当前进程（称为父进程）复制了一份（称为子进程），然后，分别在父进程和子进程内返回。

创建子进程

```python
from multiprocessing import Process
import os
def run_pro(name):
    print('开始运行子进程%s，%s'%(name,os.getpid()))

if __name__ == '__main__':
    print('开始运行进程%s' % (os.getpid()))
    p=Process(target=run_pro,args=('test',))
    p.start()
    p.join()
    print('end')
```

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211111131512-zqm80if.png)

### 启动大量子进程pool

进程池

```python
import time, threading

# 新线程执行的代码:
def loop():
    print('thread %s is running...' % threading.current_thread().name)
    n = 0
    while n < 5:
        n = n + 1
        print('thread %s >>> %s' % (threading.current_thread().name, n))
        time.sleep(1)
    print('thread %s ended.' % threading.current_thread().name)

print('thread %s is running...' % threading.current_thread().name)
t = threading.Thread(target=loop, name='LoopThread')
t.start()
t.join()
print('thread %s ended.' % threading.current_thread().name)
```

# 模块总结

## doctest文档测试

## os.path文件路径

## pickle序列化

## json
