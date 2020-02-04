---
title: "Mac下安装MySQL Python包"
date: 2019-01-30
categories: ['编程']
tags: ['Python', Mac', 'MySQL', 'MySQL-python']
keywords: ['安装', 'MySQL-python']
draft: false
---

简单几步解决问题：

<!--more-->

1. `brew install MySQL`

2. `mysql.server start`

3. mysql设置密码：`ALTER USER 'root'@'localhost' IDENTIFIED BY 'password';`

4. `brew unlink mysql`

5. `brew install mysql-connector-c`

6. `brew link --overwrite mysql`

7. `pip install --user MySQL-python`

一般这样就装好了。

如果遇到了：

`ld: library not found for -lssl`

这个问题，在第*7*步使用pip可以替换为

`env LDFLAGS="-I/usr/local/opt/openssl/include -L/usr/local/opt/openssl/lib" pip install MySQL-python`