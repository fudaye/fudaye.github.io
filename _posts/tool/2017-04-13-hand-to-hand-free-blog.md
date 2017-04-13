---
layout: post
title: 手摸手教你通过github搭建免费博客
category: 工具
tags: 工具
description: 
---

### 背景
  写博客的好处不多说了，希望这篇文章可以帮助你快速搭建一个属于自己的免费博客。
- github + [3-Jekyll](https://github.com/P233/3-Jekyll)  感谢 [Peiwen Lu](https://github.com/P233) 开发那么漂亮的主题，感谢 [suyan](https://github.com/suyan) 分享。
- 你不需要懂技术
- high 起来吧骚年

### 环境 
windows    Jekyll     github


### 第一步 搞一个github账号
注册地址：[github](https://github.com/)，如果不会注册请找度娘。
### 第二步 Fork 项目到自己的账号
点击这个地址--> https://github.com/suyan/suyan.github.io
![](http://upload-images.jianshu.io/upload_images/2021109-5d90e36d180949d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击"Fork",将这个项目Fork到自己的账户下。
![](http://upload-images.jianshu.io/upload_images/2021109-e5fb490bf1289f05.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
你的界面需要修改这里才能正常访问博客。点击“Settings”，修改成username.github.io 的形式，然后你再浏览器输入 username.github.io 这个地址就可以显示博客啦。例如 我的username 是fudaye 那么就是fudaye.github.io  讲“fudaye” 替换成你自己的username即可。
如果你能正常访问博客，恭喜，你已经成功一半了！

###第三步 需要掌握一点git的小知识。
下载一个 [git for windows 客户端](http://ooaeymn9o.bkt.clouddn.com/Git-2.8.1-64-bit.exe)，一路next。
![](http://upload-images.jianshu.io/upload_images/2021109-e7d0fc771387796c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
你会发现多了这么几个东东，点开 git bash。你可以输入  git version, 来查看当前版本号。
![](http://upload-images.jianshu.io/upload_images/2021109-e407f53bc2407fa3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

看到这个界面 恭喜git已经成功安装。
git 小知识，想详细了解git知识请查看[廖雪峰老师教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
我们只需要用到几个简单命令
#### 1.ssh-keygen -t rsa -C "youremail@example.com" 创建秘钥ssh。
如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
#### 2.登陆GitHub，打开“Account settings”，“SSH Keys”页面
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
![](http://upload-images.jianshu.io/upload_images/2021109-994a4dc5a1b3b240.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
保证你下载提交文件的时候不必再填写代码，如果你有多个电脑可以添加多个key。
#### 3.git clone 
![](http://upload-images.jianshu.io/upload_images/2021109-a896cab9a434393a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击 use SSH 
```
$ git clone git@github.com:fudaye/fudaye.github.io.git
Cloning into 'gitskills'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
```
C:\Users\acer 一般在个人电脑这个目录下回发现已经clone下来的项目
#### 4.git add [files]
当你修改了也就是新添和修改文件后一定要使用这个命令来提交你所修改的文件
#### 5.git commit -m "这里是注释" 用这个命令来提交你的文件。
#### 6.git origin master 来将你本地库推送到github。
#### 7. git status  用这个命令来查看状态。
然后访问你的博客就可以看见更改（会有缓存）。
### 第四步 配置个人信息 _config.yml
如果你想配置自己的域名，我一阿里云万网为例：
1.再你clone的项目下找到CNAME这个文件，将它修改成你的域名地址
2.在阿里云购买域名
3.增加解析
![](http://upload-images.jianshu.io/upload_images/2021109-509077ff4133d0ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
前两个为固定ip地址，第三个为你的github博客地址。
### 第五步  找个可以编辑文字的工具，就可以记录你生活的点点滴滴啦。
参考_posts中的目录结构自己创建适合自己的文章目录结构，简单解释一下：
比如你建立了一篇博客，日期格式不要改变，后边的名字可以更改。
2016-11-17-airbnb-boggle-game.md
```
---
layout: post
title: Airbnb Boggle Game
category: 面试  (控制博客最左侧分类的类别)
tags: Airbnb,Interview
keywords: Airbnb,Interview,Boogle Game
---
```
以上是固定格式，每一篇博客必须要有！

### 最后
人非圣贤孰能无过，有错误请各位爷及时提醒。