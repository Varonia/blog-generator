---
title: hexo搭建流程简单攻略【Windows平台】
date: 2018-02-27 17:19:41
tags:
---
> 使用`Hexo`搭建个人博客已经很常见了，但是在`Windows`平台下还是很多坑，繁繁琐琐，所以把我搭建的过程及遇到的坑分享给大家做个参考。

#### Hexo安装
`Hexo`安装的前提环境为`Node.js`和`Git`，如果您的电脑中已经安装上述必备程序，那么恭喜您！接下来只需要使用 `npm` 即可完成 `Hexo` 的安装。
```
$ npm install -g hexo-cli
(友情提示：最好提前把npm源换成taobao或使用cnpm，否则会经常出现一堆报错)
```
如未安装以上程序，建议使用google/baidu到官网进行下载安装。

<!-- more -->

#### 部署本地项目
进入你打算放置hexo项目文件的目录，比如`D:\demo\` ，执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```
$ hexo init <folder>   //<folder>为你打算给Hexo项目命名的文件名
$ cd <folder>
$ npm install
```
新建完成后，指定文件夹的目录如下：
```
.
├── _config.yml    //网站配置文件
├── package.json   //应用程序的信息
├── scaffolds      //模版文件夹

├── source
|   ├── _drafts
|   └── _posts     //你推送的博文
└── themes         //你的主题文件夹
```

#### 开始你的第一篇博文
 打开`git bash`，`cd`进入你的`hexo`项目文件夹，使用`hexo new file`命令即可新建一篇博文，如下示意
```
hexo new 开博大吉
```
![示意](http://upload-images.jianshu.io/upload_images/2244949-a63f8d2984c9c0dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

新建博文后即可通过路径找到文件进行编辑，或者使用`start xxx.md`命令进行编辑。

#### 网站配置
至此，我们本地项目基本框架已经搭建好了，为了让我们的博客网站能够被访问，我们需要对网站配置文件进行编辑，挂载到我们的GitHub上。
`start _config.yml`或直接使用编辑器打开`_config.yml`文件
- 修改`# site`中相关内容
```
# Site
title: V.M小站                                    //网站标题
subtitle: 来一起晒阳光吧                           //网站描述
description: 呆萌怕生 温暖无害                     //个人描述
author: Varonia                                  //作者（你的名字）
language: zh-Hans                                //语言
timezone:
```
- 修改最下方`# Deployment`中相关内容
```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy: 
  type: git
  repo: git@github.com:Varonia/Varonia.github.io.git   //地址修改为你自己的GitHub地址
  username: Varonia   //如后文提到的hexo g -d命令中发生can't find username错误时手动添加本行内容，可有效解决
```

#### 挂载GitHub

最激动人心的环节来了！做完这步以后你就可以通过你的GitHub让人访问你的博客了！那么，我们来咯！

- GitHub新建库
在 GitHub 上新建一个空 repo，repo 名称是「你的用户名.github.io」（请将你的用户名替换成真正的用户名）
- 使用gitbash命令部署
```
npm install hexo-deployer-git --save   //安装 git 部署插件
hexo clean
hexo generate
hexo deploy  //这两步的命令可简化为hexo g -d  建议每次进行修改需重新推送时都执行这三个命令
```
进入「你的用户名.github.io」对应的 repo，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接，当当当当！你的博客做好啦！

#### 更换主题

Hexo拥有着丰富的主题资源，你可以根据自己的喜好进行选择更换。通过访问官网[Hexo主题](https://hexo.io/themes/)页面进行选择。
选择好你想要的主题后，进入它的GitHub页面，复制它的 SSH 地址或 HTTPS 地址，假设地址为`github.com:lewis-geek/hexo-theme-Aath.git`，使用`git bash`进入你的项目文件根目录

```
$ git clone -b master https://github.com/lewis-geek/hexo-theme-Aath.git themes/aath
//aath为该主题默认主题名，可自行修改，但务必与网站配置文件中填写的名字保持一致
```

修改`_config.yml`中第 75 行 `theme: hexo-theme-next`，保存，并重新执行上面提到的hexo三行部署命令，即：
```
hexo clean
hexo generate
hexo deploy
```
再次刷新你的页面，是不是变得美美哒了？

#### 备份仓库
> 历经千辛万苦，终于初步搭建好你的博客，是不是觉得就大功告成了？错！
说不定你什么时候手一贱改了什么东西：报错！删掉了什么东西：报错！改了下主题：报错报错报错！！！
所以千万要记得：备份备份备份！！！

我们选择将仓库备份到GitHub上，既能起到备份的作用，又方便以后修改后同步备份。

1. 在 GitHub 创建 blog-generator 空仓库
![blog-generator 空仓库](http://upload-images.jianshu.io/upload_images/2244949-ef658ab072a0cbc7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2. 按照截图中的命令执行

##### 至此，你的Hexo博客初步搭建告一段落，如果想让你的博客更加美丽，可以去主题对应的GitHub页面里仔细阅读相关的设定说明，祝大家2018新年大吉！