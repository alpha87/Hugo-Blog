---
title: "Html实现打字机效果"
date: 2020-01-15
categories: ['JavaScript']
tags: ['前端']
keywords: [ ]
draft: false
---

怎样让博客的标语更与众不同呢？

可以使用打字机效果，让标语一字一字打出来。这样看起来更有动感。

<!--more-->

这里我们需要用到 [typed.js](https://github.com/mattboldt/typed.js/)。

# 安装

```bash
npm install typed.js

yarn add typed.js

bower install typed.js
```

# CDN

```html
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.11"></script>
```

# 使用

```html
<html>
  
  <head>
    <title>TypedJS Test</title>
    <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.11"></script>
  </head>
  
  <body>
    <span class="test"></span>
    <script>var options = {
        strings: ['天行健，君子以自强不息。'],
        typeSpeed: 40
      };

      var typed = new Typed('.test', options);
    </script>
  </body>

</html>
```

# 官方示例

可以参考这个网页的效果：[http://mattboldt.github.io/typed.js/](http://mattboldt.github.io/typed.js/)