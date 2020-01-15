---
title: "使用bcrypt加密你的密码"
date: 2019-05-13
categories: ['Python']
tags: ['密码']
keywords: ['加密', '校验']
draft: false
---

在开发程序期间多多少少会涉及到用户密码的存储，有没有什么方便的办法呢？

<!--more-->

Python 有一个很方便的库实现密码的存储和校验：[bcrypt](https://pypi.org/project/bcrypt/)。

使用起来也是非常简单的。

```python
import bcrypt


password = b"secret password"

hashed = bcrypt.hashpw(password, bcrypt.gensalt())

if bcrypt.checkpw(password, hashed):
    print("匹配")
else:
    print("匹配失败")
```