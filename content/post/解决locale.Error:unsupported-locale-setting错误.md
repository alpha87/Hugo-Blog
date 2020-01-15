---
title: "解决locale.Error: unsupported locale setting错误"
date: 2019-03-18
categories: ['Linux']
tags: ['终端', '云服务器']
keywords: [ ]
draft: false
---

云服务器中使用`pip`工具的时候可能会报此类错误：

**`locale.Error: unsupported locale setting`**

是因为语言环境配置有误。

只需要在环境变量里添加这两行就可以解决这类问题。

<!--more-->

如果你使用的是`zsh`，可以编辑`.zshrc`文件：

```
export LC_ALL=C.UTF-8
export LANG=C.UTF-8
```

保存后执行：

`source ~/.zshrc`

就可以啦！