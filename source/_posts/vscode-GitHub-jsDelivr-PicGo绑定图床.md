---
title: vscode+GitHub+jsDelivr+PicGo绑定图床
abbrlink: 18600
date: 2022-04-14 10:07:04
tags:
---

新建 GitHub 仓库

登录GitHub帐号之后，选择 New Repository（新建仓库）

https://pic.imgdb.cn/item/62579b35239250f7c5766d88.png

![image.png](https://pic.imgdb.cn/item/6257ae11239250f7c592c095.jpg)

仓库名填trmpblog，类型为 public（若设为private，将无法正常使用），最后 Create repository（生成仓库）。

生成 Token

![image.png](https://pic.imgdb.cn/item/6257ae26239250f7c592e37a.jpg)

在右上方点击头像，然后选择 Settings（设置）。

![image.png](https://pic.imgdb.cn/item/6257ae45239250f7c5930c48.jpg)

选择左边列表最下方的 Developer settings（开发者设置）。

![image.png](https://pic.imgdb.cn/item/6257ae5a239250f7c5933154.jpg)

选择 Personal access tokens（个人访问密钥），再点击 Generate new token（生成新的密钥）。

填写 Note（说明），这个值随便填，方便自己以后查看即可，repo栏，全部勾上。

![image.png](https://pic.imgdb.cn/item/6257ae85239250f7c59367ad.jpg)

密钥此时已经生成了，如图中红框处，此密钥值只会出现一次，务必在生成后保存到合适的地方，以后也无法查看。

![image.png](https://pic.imgdb.cn/item/6257ae98239250f7c5937c36.jpg)

配置 VS Code

![image.png](https://pic.imgdb.cn/item/6257aeaa239250f7c59397f1.jpg)

在 vs code 扩展商店中，下载 PicGo 扩展。

配置 PicGo 扩展的选项，共需要配置6个设置。

![image.png](https://pic.imgdb.cn/item/6257aebc239250f7c593b1a7.jpg)

图床类型，选择 github；
分支，推荐使用main 分支即可（注意自己的主分支）；
自定义 Url，https://cdn.jsdelivr.net/gh/【你的GitHub用户名】/【你的仓库名】，不建议更改此处设置。另外注意，地址的最后千万不要留有斜杠 / ；
路径，使用 image/ 即可，注意格式，前面不要有 / ，后面必须有 / ；
仓库，【你的GitHub用户名】/【你的仓库名】，注意格式，前后都不要用 / ；
密钥，填入之前生成的访问密钥。
内容创作
一切就绪，现在可以进行图片内容的创作了，在 VS code 编辑器，使用以下快捷键即可选择图片文件并上传到 GitHub，之后可以看到生成的图片的 markdown 代码了。

在这我用到了一个vscode中md的显示插件(非必要)可视化：Clipboard

![image.png](https://pic.imgdb.cn/item/6257aed3239250f7c593d5ce.jpg)

github中就成功上传了图片![image.png](https://pic.imgdb.cn/item/6257aee0239250f7c593ea67.jpg)

参考链接：

https://lovejy.blog.csdn.net/article/details/108156070?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~Rate-1.pc_relevant_paycolumn_v3&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~Rate-1.pc_relevant_paycolumn_v3&utm_relevant_index=1
