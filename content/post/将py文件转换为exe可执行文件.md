---
title: "将py文件转换为exe可执行文件"
date: 2017-12-15
categories: ['Python']
tags: ['可执行文件']
keywords: [ ]
draft: false
---

有一个库可以实现py文件转换为exe可执行文件。

<!--more-->

## pip安装

`pip install pyinstaller`

## 使用

安装好就可以使用了，在需要转换的py文件的文件夹下使用命令提示符，输入：

`pyinstaller -F -w demo.py`

然后在该目录下会生成一个dist文件夹，这个文件夹下会有demo.exe。

具体参数可参考[PyInstaller Doc](https://pyinstaller.readthedocs.io/en/stable/usage.html)。

**注意：在我现在使用的时候，pyinstaller还不支持python3.6。**