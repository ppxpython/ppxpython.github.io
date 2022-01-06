---
title: shell学习
abbrlink: 17072
date: 2022-01-05 17:12:55
tags:
---

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211014133312-i7zm4n6.png)![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928111346-aejqj42.png)

# linux基础

## 冯诺依曼体系结构

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211014133312-i7zm4n6.png)

硬件,软件体系

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928111740-b3rbv58.png)

### 运算器

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112216-izk7m4h.png)

### 控制器

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112201-v384csi.png)

### 存储器

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112134-3r5a08d.png)

### 输入设备

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112106-pmidawi.png)

### 输出设备

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112116-6pblg43.png)

内存:容量小,效率高,运行效率快,快速集成数据

硬盘:容量大,运行速度慢

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112630-n8uqrc4.png)

## 硬盘的分类

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112719-hk2pjns.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928112736-thpwus2.png)

所有的形式都是以二进制存取的

## 读取方式

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928113142-sqqecy5.png)

1个扇区4kb,等大

# shell

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928114002-rvbwpsq.png)

注意:

参数之间用空格隔开

区分大小写

## 常见命令:

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928114054-40tlgz1.png)

## 特殊字符

### .指向y隐藏文件,当前目录

### .. 上一层目录

### $ 变量

* 通配符,所有

### ~家目录

超级管理员root/

### /目录

### -参数 --参数

-简写

--单词

## 文件系统

因为每个用户项目分区不一样

没有盘符:采用树

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928115539-ihpgu1e.png)

当存储空间不够的时候采用文件挂载增加内存,理论值:可挂在65536个硬盘

扩容

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928120013-zx4rfer.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928131621-49xo3te.png)mount挂载

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928132850-0z9e7ce.png)

bin 可执行文件,脚本

boot 引导分区

dev 设备信息

etc 配置文件

home 家

lib 内库

lib64

media 多媒体

mnt 硬盘挂载 U盘

opt 默认安装目录

proc 进程信息

root 管理员家目录

run 运行时的系统常量,变量

sbin 管理员可执行的权限和命令

srv  服务启动之后需要提取额数据

sys 系统内核信息

tmp 临时存放信息,变量,重启后可能会清除

usr 共享文件

var临时存放信息,变量,重启不清除 eg:日志

### cd 改变文件路径

### ll显示目录

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928133231-hwbcnch.png)

### ls显示目录

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928133250-q8n540z.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928133330-4dni3cv.png)

中

-开头表示文件

d开头表示文件夹

l开头表示链接[win中叫快捷方式]

### mkdir创建目录

-p 创建多级目录 mkdir -p a

mkdir -p haoduo{test1,test2,test3}创建多个文件夹

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928134135-t044sr2.png)

{}:类似java中数组的含义

### rmdir删除目录

rmdir要求文件时空文件夹

### cp复制文件

cp 源文件 目标文件

-r 文件夹,目录时

### mv文件和目录移动和改名

文件和目录

### rm 删除

-f 强制删除

-r文件夹

### touch创建文件

### stat查看文件信息

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928140246-btdll99.png)

### ln链接

快捷方式

-s软链接

### cat查看内容

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928141624-ks158n1.png)

### tac查看内容倒序

### more,less查看内容分页

### head查看取前几行

显示某一行

head -8 | tail -1

### tail查看取后几行

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928142146-aiqelcg.png)

-f -F 显示追加内容,监控到数据变动

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928143318-30ut1q2.png)

### find 搜索文件

find / 表示全局搜索

-name 文件名

用法
find    [命令选项]     [路径]     [表达式选项]
选项
选项	用法
-empty	查找空白文件或目录
-group	按组查找
-name	按文档名称查找
-iname	按文档名称查找，且不区分大小写
-mtime	按修改时间查找
-size	按容量大小查找
-type	按文档类型查找，文件（f）、目录(d)、设备(b，c)、链接(l)等
-user	按用户查找
-exec	对找到的档案执行特定的命令
-a	并且
-o	或者
举例
查找当前目录下名称为hello.txt的文档

[root@test ~]# find -name hello.txt
1
查找/root 目录下所有名称以.log结尾的文件

[root@test ~]# find  /var/log/  -name  "*.log"
1
不区分大小写查找文件 test

[root@test ~]# find  -iname  "test"
1
查找系统中所有的空白文件

[root@test ~]# find   /   -empty
1
查找系统中所属组为tom的文件

[root@test ~]# find  /  -group  tom
1
查找系统中所有3天内被修改过的文件

[root@test ~]# find  /  -mtime  -3
1
查找系统中所有4天前被修改过的文件

[root@test ~]# find  /  -mtime  +4
1
查找系统中2天前的当天被修改过的文件

[root@test ~]# find  /  -mtime   2
1
查找当前目录下大于10MB的文件

[root@test ~]# find  ./  -size   +10M
1
查找当前目录下的所有普通文件

[root@test ~]# find  ./  -type   f
1
查找计算中tom所拥有的所有文件

[root@test ~]# find  /  -user  tom
1
查找当前目录下大于1MB的文件后列出文件的详细信息

[root@test ~]# find  ./  -size  +1M  -exec ls -l {} \;
1
查找计算机中所有大于1MB的文件

[root@test ~]# find   /  -size   +1M  -a  -type  f
1

### sort 排序文件列表输出

语法：sort(选项)(参数)
1
选项：

-b：忽略每行前面开始出的空格字符；
-c：检查文件是否已经按照顺序排序；
-d：排序时，处理英文字母、数字及空格字符外，忽略其他的字符；
-f：排序时，将小写字母视为大写字母；
-i：排序时，除了040至176之间的ASCII字符外，忽略其他的字符；
-m：将几个排序号的文件进行合并；
-M：将前面3个字母依照月份的缩写进行排序；
-n：依照数值的大小排序；
-o<输出文件>：将排序后的结果存入制定的文件；
-r：以相反的顺序来排序；
-t<分隔字符>：指定排序时所用的栏位分隔字符；
+<起始栏位>-<结束栏位>：以指定的栏位来排序，范围由起始栏位到结束栏位的前一栏位。

-u 去重

### vi编辑

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928143730-uas6kpc.png)

#### 打开文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928143847-f9i7y6z.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928144507-v3wo5zv.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928144552-5s8cvbg.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928145045-0z40uen.png)

##### 编辑模式

常用的

15gg:进入第15行

shift+G 最后一行

dd 删除一行

3dd删除3行

w光标单词移动

dw将后面的单词删除

3dw 删除后面3个单词

yy复制

pp粘贴

yw复制一个单词

yp粘贴一个单词

u撤销

shift+6行首

shift+4行尾

shift ZZ

r替换

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928150309-fpg3e7x.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928150324-nmgcex3.png)

##### 末行模式

wq保存并退出

wq!

w保存

q退出

q!不保存退出

**set nu 显示行数**

/关键字 查找

s/关键字/替换字/g 加了g后当前行全部替换

g/关键字/替换字/g

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928151139-ewakaar.png)

vi编写时间经常出现🧐

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928151616-t2e954g.png)

直接删除

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928151629-3thpu7r.png)

## 计算机间数据传输

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928151755-37h8doa.png)

### rz上传

### sz下载

创建虚拟机后如何修改🧐

root登录

hostname 名字 修改主机名

vi /etc/hostname          主机名

vi /etc/sysconfig/network-scripts/ifcfg-eth0 中修改IPADDR=172.17.20.145IP地址

systemtcl restart  重启

### scp传递文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928153822-kxh168x.png)

### df分区信息

-h  包含单位

### du指定文件大小

du -h --max-depth=1 /

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928154729-ls21wo2.png)

### tar解压和压缩

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928155138-fxi7zul.png)

tar -zxvf Python-3.7.1

zx解压

zc压缩

v过程

f文件

tar -zcf 目标文件名 需要压缩文件 dir.tar.gz dir

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928155835-e4mc2b0.png)

### zip压缩

zip -r dir.zip dir

### unzip解压

unzip dir.zip

## 网络相关

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928160636-fo1me6s.png)

### ifconfig网卡配置信息

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928161212-ug0093j.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928161332-bzxvlf2.png)

### netstat网络状态

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928161625-w3um1l3.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928161757-14n0awy.png)

端口22:默认ssh访问接口

-anp

-r核心路由表=命令route

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928162000-cs6kudy.png)

### ping地址连通

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928162126-6a8zwod.png)

### telnet端口联通

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928162200-e1962ue.png)

### curl获取信息

curl -X GET http://www.baidu.com

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928162734-lyicdjd.png)

## 防火墙

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928162904-ij8u60y.png)

发现centos 使用 service 命令替代systemctl

如启动服务

service httpd start

查看httpd服务状态

service httpd status

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928163951-4ososok.png)

## 日期和时间

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928164040-ywkqiqu.png)

### date 查看当前时间

集群时间同步策略ntp

### ntpdate  集群同步时间

cn.ntp.org.cn

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928165157-08l6gy7.png)

## 用户-组-权限

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928165307-mv1p75w.png)

### useradd添加用户

### passwd修改用户密码

### userdel 删除用户

-r

### su 切换用户

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928165950-drz5m8n.png)

### groupadd创建组

### groups查看组

### groupdel删除组

### groupmod -n 修改组

## 权限

r读

x执行

w写

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928170406-dl1sh0f.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928170418-t1p2wma.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928170457-yxpuy60.png)

3组  所属用户 所属组 其他

修改权限

chown 用户 文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928171140-1huxem1.png)

## 管道 |

ps

netstat -anp | grep 22

### | 管道

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928171508-0q9okvj.png)

## A重定向

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928171724-cmq0aie.png)

### >替换

### 012文件描述符

* 1 是标准输出（stdout）
* 2 是标准错误输出（stderr）
* 0 是标准输入（stdin）
  1> 两个符号连着一起，而且呢，1和>符号之间不能有空格

### >>追加

## 进程

ps -ef

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928172320-7us6puc.png)

uid:用户id

pid:进程id

ppid:副进程id

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928172732-srz0943.png)

### ps -ef查看进程

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20211015110240-qynqhjk.png)

linux上进程有5种状态:

1. 运行(正在运行或在运行队列中等待)
2. 中断(休眠中, 受阻, 在等待某个条件的形成或接受到信号)
3. 不可中断(收到信号不唤醒和不可运行, 进程必须等待直到有中断发生)
4. 僵死(进程已终止, 但进程描述符存在, 直到父进程调用wait4()系统调用后释放)
5. 停止(进程收到SIGSTOP, SIGSTP, SIGTIN, SIGTOU信号后停止运行运行)

1）ps a 显示现行终端机下的所有程序，包括其他用户的程序。

2）ps -A 显示所有程序。

3）ps c 列出程序时，显示每个程序真正的指令名称，而不包含路径，参数或常驻服务的标示。

4）ps -e 此参数的效果和指定"A"参数相同。

5）ps e 列出程序时，显示每个程序所使用的环境变量。

6）ps f 用ASCII字符显示树状结构，表达程序间的相互关系。

7）ps -H 显示树状结构，表示程序间的相互关系。

8）ps -N 显示所有的程序，除了执行ps指令终端机下的程序之外。

9）ps s 采用程序信号的格式显示程序状况。

10）ps S 列出程序时，包括已中断的子程序资料。

11）ps -t <终端机编号> 　指定终端机编号，并列出属于该终端机的程序的状况。

12）ps u 　 以用户为主的格式来显示程序状况。

13）ps x 　 显示所有程序，不以终端机来区分。

14）ps -l 較長,較詳細的顯示該PID的信息

### jobs -l查看后台进程

### nohup防止进程被挂起

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928173042-1y4ymd0.png)

### kill杀死进程

## 环境变量

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928173423-5y1pbxk.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928173550-com6n1e.png)

## top进程变化cpu负载情况

**top 运行中可以通过 top 的内部命令对进程的显示方式进行控制。内部命令如下：**`<br />`s – 改变画面更新频率`<br />`l – 关闭或开启第一部分第一行 top 信息的表示`<br />`t – 关闭或开启第一部分第二行 Tasks 和第三行 Cpus 信息的表示`<br />`m – 关闭或开启第一部分第四行 Mem 和 第五行 Swap 信息的表示`<br />`N – 以 PID 的大小的顺序排列表示进程列表`<br />`P – 以 CPU 占用率大小的顺序排列进程列表`<br />`M – 以内存占用率大小的顺序排列进程列表`<br />`h – 显示帮助`<br />`n – 设置在进程列表所显示进程的数量`<br />`q – 退出 top`<br />`s – 改变画面更新周期

序号 列名 含义`<br />`  PID 进程id`<br />`  PPID 父进程id`<br />`  RUSER Real user name`<br />` UID 进程所有者的用户id`<br />`  USER 进程所有者的用户名`<br />` GROUP 进程所有者的组名`<br />`  TTY 启动进程的终端名。不是从终端启动的进程则显示为 ?`<br />`  PR 优先级`<br />`  NI nice值。负值表示高优先级，正值表示低优先级 0`<br />`  P 最后使用的CPU，仅在多CPU环境下有意义`<br />`  %CPU 上次更新到现在的CPU时间占用百分比`<br />`  TIME 进程使用的CPU时间总计，单位秒`<br />`  TIME+ 进程使用的CPU时间总计，单位1/100秒`<br />` %MEM 进程使用的物理内存百分比`<br />`  VIRT 进程使用的虚拟内存总量，单位kb。VIRT=SWAP+RES`<br />`  SWAP 进程使用的虚拟内存中，被换出的大小，单位kb。`<br />`  RES 进程使用的、未被换出的物理内存大小，单位kb。RES=CODE+DATA`<br />`  CODE 可执行代码占用的物理内存大小，单位kb`<br />` DATA 可执行代码以外的部分(数据段+栈)占用的物理内存大小，单位kb`<br />`  SHR 共享内存大小，单位kb`<br />`  nFLT 页面错误次数`<br />`  nDRT 最后一次写入到现在，被修改过的页面数。`<br />`  S 进程状态。（D=不可中断的睡眠状态，R=运行，S=睡眠，T=跟踪/停止，Z=僵尸进程）`<br />` COMMAND 命令名/命令行`<br />`  WCHAN 若该进程在睡眠，则显示睡眠中的系统函数名`<br />`  Flags 任务标志，参考 sched.h

默认情况下仅显示比较重要的 PID、USER、PR、NI、VIRT、RES、SHR、S、%CPU、%MEM、TIME+、COMMAND 列。可以通过下面的快捷键来更改显示内容。

通过 f 键可以选择显示的内容。按 f 键之后会显示列的列表，按 a-z 即可显示或隐藏对应的列，最后按回车键确定。`<br />`按 o 键可以改变列的显示顺序。按小写的 a-z 可以将相应的列向右移动，而大写的 A-Z 可以将相应的列向左移动。最后按回车键确定。`<br />`按大写的 F 或 O 键，然后按 a-z 可以将进程按照相应的列进行排序。而大写的 R 键可以将当前的排序倒转。

top使用方法：

**使用格式：**

**top [-] [d] [p] [q] [c] [C] [S] [s] [n]`<br />`**

**参数说明：**

**d：指定每两次屏幕信息刷新之间的时间间隔。当然用户可以使用s交互命令来改变之。**

p:通过指定监控进程ID来仅仅监控某个进程的状态。

q:该选项将使top没有任何延迟的进行刷新。如果调用程序有超级用户权限，那么top将以尽可能高的优先级运行。

S：指定累计模式。

s：使top命令在安全模式中运行。这将去除交互命令所带来的潜在危险。

i：使top不显示任何闲置或者僵死进程。

c:显示整个命令行而不只是显示命令名。

常用命令说明：

Ctrl+L：擦除并且重写屏幕`<br />`

K：终止一个进程。系统将提示用户输入需要终止的进程PID，以及需要发送给该进程什么样的信号。一般的终止进程可以使用15信号；如果不能正常结束那就使用信号9强制结束该进程。默认值是信号15。在安全模式中此命令被屏蔽。

i：忽略闲置和僵死进程。这是一个开关式命令。

q：退出程序

r:重新安排一个进程的优先级别。系统提示用户输入需要改变的进程PID以及需要设置的进程优先级值。输入一个正值将使优先级降低，反之则可以使该进程拥有更高的优先权。默认值是10。

S：切换到累计模式。

s：改变两次刷新之间的延迟时间。系统将提示用户输入新的时间，单位为s。如果有小数，就换算成m s。输入0值则系统将不断刷新，默认值是5 s。需要注意的是如果设置太小的时间，很可能会引起不断刷新，从而根本来不及看清显示的情况，而且系统负载也会大大增加。

f或者F：从当前显示中添加或者删除项目。`<br />`

o或者O：改变显示项目的顺序`<br />`

l：切换显示平均负载和启动时间信息。`<br />`

m:切换显示内存信息。

t:切换显示进程和CPU状态信息。

c:切换显示命令名称和完整命令行。

M:根据驻留内存大小进行排序。

**P:根据CPU使用百分比大小进行排序。**

**T:根据时间/累计时间进行排序。**

**W:将当前设置写入~/.toprc文件中。**

**查看多核CPU命令`<br />`**mpstat -P ALL  和  sar -P ALL

## curl请求接口

curl是非常方便的Rest 客户端, 可以很方便的完成 Rest API测试, 利用curl对http协议发送Get/Post/Delete/Put, 同时还可以携带header 来满足Rest API 需求的特定条件

curl 常用的参数

-X/--request [GET|POST|PUT|DELETE|…]  使用指定的http method发出 http request

-H/--header                           设定request里的header

-i/--include                          显示response的header

-d/--data                             设定 http parameters

-v/--verbose                          輸出比较多的信息

-u/--user                             使用者账号

-b/--cookie                           cookie 文件路径 使用cookie

linux command line 的参数, 同一个功能常会有两个完全相同的参数, 一个是比较短的参数, 另一个是比较长的参数

1、测试get请求
$ curl http://www.linuxidc.com/login.cgi?user=test001&password=123456

2、测试post请求
$ curl -d "user=nickwolfe&password=12345" http://www.linuxidc.com/login.cgi
方式一：发送磁盘上面的xml文件（推荐）
root [ /apps ]$ curl -X POST -H 'content-type: application/xml'  -d @/apps/myxmlfile.txt http://172.19.219.xx:8081/csp/faq/actDiaUserInfo.action
ps：其中myxmlfile.txt为磁盘上面的xml文件，后面为请求路径

方式二：在命令行直接发送xml结构数据

root [ /apps ]$ curl -H 'content-type: application/xml' -X POST -d '`<?xml version="1.0" encoding="UTF-8"?><userinfoReq>``<subsNumber>`13814528620`</subsNumber><type>`3`</type></userinfoReq>`' http://172.19.219.xx:8081/csp/faq/actDiaUserInfo.action
或者

root [ /apps ]$ echo '`<?xml version="1.0" encoding="UTF-8"?><userinfoReq>``<subsNumber>`

`https://www.ekwing.com/home/classtop?class=443`

https://www.ekwing.com/home/cityhw

请求 URL: https://passport.ekwing.com/index/getschooluser?callback=jQuery17208287960962547929_1634277562968&uname=%E7%BF%BC%E5%B0%8F%E5%B0%8F1&pw=jSB5rGAv2seFjniqPD1Ic7AoGk9a6QfPMyvwJvDYjVxwaNDwY7cMhTV9Z90CSNUgdc2SGJ5cfRk9R0V0UUgNJc%2BQh9Ch90mZ%2BSUx8czho2gAU%2B9Qg6wFCYoKai3uhZ7UtT3MylPxytzccEQnpNAeaylQrqDGMrbJaRDD%2FwAu2Qc%3D&encrypt_key=407ac0f7864098ba320af44dc0f38dad&encrypt_type=rsa&school_name=%E5%8A%B1%E5%BF%97%E5%AD%A6%E6%A0%A1&login_type=4&code=&code_token=&_=1634277699157

## rpm安装卸载

-ivh安装

i[install ]

v[查看信息]

-qa查询所有安装信息

-q

-e卸载 全称

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928174937-bdinaah.png)

## 三剑客

### cut切分文件

### sort排序

### wc统计单词数

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928175447-xnovzci.png)

## grep

经常和|连用

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928175733-pzs8lap.png)

ps -ef |grep

find

## set

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928175958-llyemi3.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928180012-n94iq7d.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928180034-wr7jpgl.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928180201-rkzvpv2.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928180321-vxpkclc.png)

## awk

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928180345-r3cefbi.png)

# shell编程

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928180526-lak2vdg.png)

### 执行脚本文件

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210928181122-gv2i7a4.png)

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210929100553-rxdo02p.png)

#### ./hello.sh方法一

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210929100210-4qymaid.png)

#### sh或bash hello.sh方法二

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210929100227-weczbp4.png)

#### source或. hello.sh

![image.png](https://b3logfile.com/siyuan/1629903953048/assets/image-20210929100648-4auelc0.png)
