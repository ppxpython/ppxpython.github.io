---
title: 03VUE---拦截路径挂载的问题
tags: Error
categories:
  - - 计算机科学
    - Vue
    - 前端Vue中常见问题集合
abbrlink: 12938
date: 2020-10-05 16:25:40
---
 
# 项目场景：

 vscode中没有报错，但在网页的控制台中出现错误
# 问题描述：

 vscode中没有报错，但在网页的控制台中
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2020100516264293.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)

# 原因分析：


拦截路径挂载的问题
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005162702325.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)


# 解决方案：
在上面添加
//出现问题时使用
const originalPush=VueRouter.prototype.push
VueRouter.prototype.push=function push(location,onResolve,onReject){
    if(onResolve || onReject) return  originalPush.call(this,location,onResolve,onReject)
      return originalPush.call(this,location).catch(err => err)
}
 


![在这里插入图片描述](https://img-blog.csdnimg.cn/20201005162735676.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDA1NDc1Ng==,size_16,color_FFFFFF,t_70#pic_center)
