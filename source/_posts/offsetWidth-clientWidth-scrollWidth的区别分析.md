---
title: 'offsetWidth,clientWidth,scrollWidth的区别分析'
date: 2018-04-07 22:10:40
tags: DOM
---

大家在使用JS取宽高的时候第一时间想到的是什么API呢？offsetWidth?clientWidth?还是scrollWidth?
它们各自的含义，彼此的差异大家又是否很清楚呢？本文就是分析讲解这些内容。

- offsetWidth, offsetHeight : 视窗content width + padding + 滚动条宽高 + border

- clientWidth, clientHeight : 视窗content width + padding

- scrollWidth, scrollHeight : 所有content width，包括当前隐藏在滚动区域之外的部分 + padding

![示意图](http://ww1.sinaimg.cn/large/7dbf9c78ly1fq4gp0lmxyj20hs0g5402.jpg)

由上面的介绍可以看出，只有offsetWidth属性包含了滚动条的宽度，所以，如果我们有需要获取滚动条宽度可据此进行计算

```

scrollbarWidth = offsetWidth - clientWidth - getComputedStyle().borderLeftWidth - getComputedStyle().borderRightWidth

```

