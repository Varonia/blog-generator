---
layout: responsive-design
title: Bootstrap响应式布局
date: 2018-03-27 12:22:33
tags: Bootstrap
---

- 首先当然是引用Bootstrap  
```

<!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

```

- bootstrap中container跟container-fluid的样式一个是自适应布局，一个是固定宽度布局
```
@media (min-width: 768px) {
  .container {
    width: 750px;
  }
}
```

- 可在类名中加`标签名-respnstive`实现响应式设计，如`img-responsive`

- button加类名 btn系列可实现不同样式 详见https://v2.bootcss.com/base-css.html#buttons