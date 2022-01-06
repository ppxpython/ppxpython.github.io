---
title: cmder使用配置教程
abbrlink: 60065
date: 2022-01-06 10:10:56
tags:
categories:
  - [电脑,软件配置,安装教程]
---
cmder使用配置教程

## 1. 安装 Cmder

打开 Cmder官网（ **[https://cmder.net](https://cmder.net/)** ），下拉页面找到 **Download** 项选择下载，下载的时候，两个版本，分别是 mini 与 full 版；唯一的差别在于有没有内建 git-for-windows 工具，这是 Git for Windows 的标准配备；全安装版 Cmder 自带了 msysgit，除了 git 本身这个命令之外， cmder 完全支持 Linux 命令行，里面可以使用大量的 linux 命令，比如 grep、curl (没有 wget)、vim、grep、tar、unzip、ssh、ls、bash、perl 等，而且可以多开，快捷键复制粘贴，分屏等，功能非常强大

这里选择 full 版本点击下载。下载的是 Cmder 的压缩包，解压即可以使用。

### **启动 Cmder**

Cmder 解压后，双击 Cmder.exe 即可运行。

如果每次都进入到 Cmder 解压目录双击 Cmder.exe 打开的方式很麻烦，可以使用下面几种方式很好的解决问题；

* 1、 **把 Cmder 加到环境变量** 。把 Cmder.exe 存放的目录添加到系统环境变量；加完之后，win+r 然后输入cmder 即可。
* 2、 **添加 cmder 到右键菜单。** 添加后在任意文件夹中即可打开Cmder，上一步的把 Cmder 加到环境变量就是为此服务的，在管理员权限的终端输入以下语句即可: **Cmder.exe /REGISTER ALL**
* 3、 **为 Cmder.exe创建快捷方式** ，右击 Cmder.exe 选择 "创建快捷方式" 点击即可，或者把创建的 **快捷方式 **放到 ** C:\Windows\System32，** 加完之后，win+r 然后输入cmder 即可。

### Cmder 常用功能介绍

cmder 功能极为强大，这里就先说下常用的功能：

* **1. Cmder 常用快捷键**

```Bash
tab           自动路径补全； ctrl + t      建立新页签；ctrl + w      关闭页签;ctrl + tab    切换页签;ctrl + 1      快速切换到第1个页签ctrl + n      快速切换到第n个页签( n值无上限)alt + F4      关闭所有页签 ctr + r       历史命令搜索alt + enter   切换到全屏状态 alt + shift + 1    开启 cmd.exealt + shift + 2    开启 powershell.exealt + Shift + 3    开启 powershell.exe (系统管理员权限)
```

* 2. 可在 **视窗内** 搜寻 画面上 出现过的任意关键字。
* 3. 新增 **页签** 按钮。
* 4. 切换 **页签** 按钮。
* 5. **锁定**  **视窗** ，让视窗无法再输入。
* 6. 切换 视窗 是否提供卷轴功能，启动时可查询之前显示过的内容。
* 7. 按下滑鼠左键可开启系统选单，滑鼠右键可开启工具选项视窗。 Win+Alt+P  ：开启 **工具选项** 视窗

**cmder分屏功能： ctrl + t  或者 点击 右下角 + 号**

**分屏功能 快捷键 设置：**

### Cmder 进阶功能

* Cmder 增加了 alias 功能：可以给 **超长又难以记忆的指令** 起一个 **别名**  **，** 输入 **alias **可以查看已有的  **别名** 。打开安装目录 config/user-aliases.cmd 文件，直接修改。自定义 aliases：打开 Cmder 目录下的 config 文件夹，里面的 aliases 文件就是我们可以配置的别名文件，直接修改。
* ```
  这里将 ls 命令的别名按下列方式修改，添加至文件末尾，就可以在 ls 命令下显示中文，同时增强命令并添加颜色区分。
  ```
* ```
      l=ls --show-control-chars
  ```
* ```
      la=ls -aF --show-control-chars
  ```
* ```
      ll=ls -alF --show-control-chars
  ```
* ```
      ls=ls --show-control-chars -F
  ```
* 主控台文字自动放大缩小功能，只要按下 **Ctrl + 滑鼠滚轮** 就可以办到，还有 up 向上翻历史命令。
* 鼠标选中自动复制到剪切板。直接 鼠标右键 即可 粘贴，或者使用 Ctrl + v 进行粘贴。

## 2. Cmder 设置

**右下角 的 三杠** ，然后选择  **Settings ** ，或者 使用快捷键 **Windows+Alt+p** 打开 **设置**

### **解决文字重叠** ：

Win + ALT + P 打开设置界面 monospce，去掉勾勾即可。

### **设置编码，解决中文乱码**

**设置：set LC_ALL=zh_CN.UTF-8 **   或者    **set LANG=zh_CN.UTF-8**

**查看 git log 时乱码**

在 Startup ---> Environment 中添加下面的语句：

```C%2B%2B
set LANG=zh_CN.UTF-8
```

然后执行下面的命令，来配置git log的输出

```JavaScript
git config --global i18n.logoutputencoding utf-8
```

> 或者在 .gitconfig 文件中配置

> 更多乱码问题见： [cmder中文乱码 - CSDN博客](https://blog.csdn.net/guiying123456/article/details/62881400)

**设置中文界面** ： 选择   **General ** ---> Interface language ---> zh:简体中文

### **设置为默认终端**

setting ---> 集成 ---> 默认终端 ---> 强制使用ConEmu作为控制台应用程序的默认终端。如果允许某些程序出现错误，需要关闭此选项；比如 mkcert。

* 图中绿色设置可以强制将cmder注册成Windows的默认终端
* > 设置此选项后，系统启动后就会生效，且，即使你打开的是cmd，也会被放到cmder的窗口中执行
  >
* 红色选项可以解决每次关闭控制台时，弹出确认关闭的弹窗

**窗口位置大小记忆** ：勾选这两个设置，只需要设置一次，下次会自动记住上次终端在桌面出现的位置和窗口大小

### **设置 vi 模式下 ESC 键最小化窗口的问题**

* 将图中红色改成除了总是的其他选项，否则使用vi时会出现无法切换模式的问题
* 勾选绿色的选项可以解决打开多个终端，**任务栏显示多个窗口**的问题

### **解决粘贴多行文本时的弹窗**

例如在终端中执行多行SQL语句，总会弹出提示，勾选选项可以解决

### **将命令提示改成 $**

默认的命令提示符是λ,大家都知道Linux是$，这里提供一下修改的方法，并不是必须的

* 1) 首先在cmder的安装目录下,找到vendor/目录，然后找到clink.lua文件
* 2) 打开后可以Ctrl+F查找下面的字段 local lambda =
* 3) 将local lambda =""的值替换成$

```Ruby
可以修改文件 ${CMDER_HOME}\vendor\clink.lua    if env == nil then        lambda = "λ"    else        lambda = "("..env..") λ"    end改成    if env == nil then        lambda = "$"    else        lambda = "("..env..") $"    end
```

### 将 Idea 的 Terminal 终端换成 cmder

1) 在 idea 中打开其他设置界面，在 idea 中 settings 是对当前项目生效，Other Settings 是对所有项目生效
2) 修改 shell Path 的路径，替换成下面的内容

注意将 cmder 安装目录换成你的安装目录

```Python
//这种方式比较可靠，避免了环境变量失效的问题"cmd.exe" /k ""你的cmder安装目录\vendor\init.bat"" //或者，这个需要有环境变量"cmd.exe" /k ""%环境变量配置的cmder home目录名称%\vendor\init.bat""
```

3) 再次打开Terminal终端就可以使用Linux命令了

### **将 vscode 的 Terminal 终端设置成 cmder**

1)打开设置

2) 搜索code save,点击打开设置json文件

3)将下面的代码粘贴到文件中，修改为自己需要的内容。注意：修改cmder的安装目录为自己的安装目录

```Python
// 设置终端为cmder"terminal.integrated.shell.windows": "cmd.exe","terminal.integrated.env.windows": {    //设置cmder的根目录    "CMDER_ROOT": "cmder的根目录" }, "terminal.integrated.shellArgs.windows": [ "/k", //设置启动初始化目录 "cmder的根目录\\vendor\\init.bat" ], //下面的设置可以不需要 //终端颜色配置 "workbench.colorCustomizations": { //可以将鼠标放到下面的色号上根据自己的偏好进行选择 "terminal.foreground": "#37FF13", "terminal.background": "#2b2424" }, "terminal.integrated.cursorBlinking": true, //设置terminal中的行高 "terminal.integrated.lineHeight": 1.1, "terminal.integrated.letterSpacing": 0.1, "terminal.integrated.fontSize": 12, //字体大小设置 "terminal.integrated.fontFamily": "monaco", //字体设置 "terminal.integrated.shell.linux": "/bin/zsh"
```

4) Ctrl+J打开终端，就可以使用了

### Cmder 启动选项

默认选择的启动项应该是 {cmd::Cmder} 这个命名任务，我们可以更改成其它的命令任务或者直接切换到其它的启动项。

默认的是 cmd，这里演示设置 PowerShell 的方法。也可使 设置 默认使用 bash，这个看个人需求。

### 自定义启动目录

下面就来克隆现有的{cmd::Cmder}添加一个设置自定义的启动目录的任务(Task)：

* 任务参数：下面来看  "Task parameters" 命令参数，阅读实例可知参数 /icon指定图标位置，/dir 指定启动目录，所以我们可以添加下面的参数：/icon "%CMDER_ROOT%\icons\cmder.ico" /dir "C:\Users\Fan"
* 记得在 startup 的 "Specified named task" 处选择 cmd::diy1
* 保存设置，退出，重新打开 cmder 查看效果
