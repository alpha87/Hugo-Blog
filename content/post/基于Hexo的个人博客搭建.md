---
title: "基于Hexo的个人博客搭建"
date: 2017-10-15
categories: ['贵在折腾']
tags: ['博客']
keywords: [ ]
draft: false
---

为什么会有这篇文章的诞生？因为在学习Python的过程中总想给自己找点乐子，为了记录学习也是为了记录生活，总觉得没有一个属于自己的博客不圆满，今天也算是实现了吧。下面我就来分享一下这两天的成果。

我们的博客是基于Hexo的，官网的描述只有一句话：

> A fast, simple, powerful blog framework

当你看完这篇教程以后，你就会觉得，恩，真的是这样。

<!--more-->

## 生成页面

在使用Hexo之前，我们必须安装Node.js运行环境。

简单的说 Node.js 就是运行在服务端的JavaScript，一个基于Chrome JavaScript 运行时建立的一个平台，一个事件驱动I/O服务端JavaScript环境，基于Google的V8引擎，V8引擎执行Javascript的速度非常快，性能非常好。

### 安装Node.js

首先要去官网安装Node.js。[Node.js官网地址](https://nodejs.org/en/)

### 设置淘宝npm镜像

安装好以后首先要做的事是使用淘宝npm镜像加速，要不然下载速度巨慢。

输入命令：

```bash
npm config set registry https://registry.npm.taobao.org
npm info underscore
```

如果配置成功,第二步会有提示。

## 生成Hexo

以上两步都成功完成之后就可以继续了。输入命令安装Hexo：

`npm install -g hexo`

安装好以后就可以开始搭建静态博客了。

我在C盘创建一个新文件夹，命名为blog。打开这个文件夹，按住shift键单击右键，点击“在此处打开命令窗口”，输入命令：

`hexo init`

然后就等待Hexo在blog文件夹下自动生成一些文件，完成以后会提示可以使用了。

安装依赖包：

`npm install`

生成静态页面和启动本地服务的命令：

`hexo s -g`

启动成功会提示打开[http://localhost:4000/](http://localhost:4000/)，按下Ctrl+C停止。

打开网址就可以看到刚才生成的静态页面了。

这些是一些hexo的命令：

```
hexo new"postName" # 新建文章
hexo new page"pageName" # 新建页面
hexo generate # 生成静态页面至public目录
hexo server # 开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy # 将.deploy目录部署到指定空间
hexo help # 查看帮助
hexo version # 查看Hexo的版本
```

## 部署环境

我们把博客部署到GitHub上，所以首先要有GitHub账户，如果你已经申请过就可以跳过这一步了。

### 搭建仓库

进入[Github](https://github.com/)网站注册一个账号，完成邮箱认证就可以开始项目了。

在Repository name一栏填入你的`用户名+github.io`，比如我的用户名是alpha87, Repository name就写`alpha87.github.io`。**注意仓库名称格式，一定是yourname.github.io**。

### 部署公钥

进入账号的Personal setting页面，选择SSH and GPG keys，进入密钥配置页面。填入本机公钥，点击Add SSH key。

到这里，你一定会问，SSH密钥对是什么，在哪能找到。接下来就告诉你如何获取密钥。

### 获取密钥

首先需要下载[git for windows](https://git-for-windows.github.io/)。下载好以后在桌面单击右键运行“Git Bash here”，输入：

`ssh-keygen -t rsa -C "git邮箱"`

然后会提示你输入key的名称，直接回车，之后弹出来什么都按回车默认值就行。

然后在用户目录下找到`.ssh`目录，找到`id_rsa.pub`文件，用记事本打开，复制到刚才需要添加的SSH key里就可以了。

然后输入：

`ssh -T git@github.com`

当你第一次使用Git的clone或者push命令连接GitHub时，会得到一个警告：

```bash
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
```

输入“yes”，如果返回Hi yourname! You’ve successfully authenticated, but GitHub does not provide shell access.则说明公钥部署成功。

## 发布站点

想要发布站点还得设置一下，打开blog目录下的_config.yml。在最下边找到deploy：


```
deploy:
  type: git
  repository: git@github.com:yourname/yourname.github.io.git
  branch: master
```

yourname也就是你的用户名。

先输入命令：

`npm install hexo-deployer-git --save`

然后输入：

`git config --global user.name "你的用户名"`
`git config --global user.email "你的邮箱"`

然后部署：

`hexo d -g`

这样操作以后，浏览器打开https://yourname.github.io 就可以看到刚才本地预览页面了。

## 完事

这下就可以愉快的写博客啦!