---
title: "如果 Ubuntu 没声音怎么办"
date: 2017-11-13
categories: ['Linux']
tags: ['Ubuntu']
keywords: [ ]
draft: false
---
先说一种特殊的情况，如果你是双系统，即有可能你是windows和ubuntu系统同时使用的话，完整关机一次可能问题就解决了。如果没有解决就继续往下看。

<!--more-->

打开终端输入：

`sudo apt-get install pavucontrol`

安装完成后：

`pavucontrol`

打开软件查看音量是否正常，如果不正常调至100即可。

如果重启后还有问题，可以尝试使用`sudo`模式打开。