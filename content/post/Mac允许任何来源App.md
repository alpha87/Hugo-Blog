---
title: "Mac 允许任何来源 App"
date: 2019-04-19
categories: ['贵在折腾']
tags: ['Mac']
keywords: ['安装', '应用', 'APP']
draft: false
---

如果在安装过程中遇到“应用已损坏”的问题，说明系统不允许安装其他来源的应用。

如何让Mac允许安装来自任何来源的app呢？只需一条简单命令。

<!--more-->

在终端输入：

`sudo spctl --master-disable`

就可以了。