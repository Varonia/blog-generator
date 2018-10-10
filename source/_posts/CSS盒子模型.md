---
title: CSS盒子模型
date: 2018-03-19 20:32:29
tags: CSS
---

css盒子模型分为标准盒子模型和ie盒子模型，分别对应
`box-sizing`: `content-box` | `border-box`

| 值 | 描述 |
| ------ | ------ |
|content-box|这是由 CSS2.1 规定的宽度高度行为。宽度和高度分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距和边框。|
|border-box|为元素设定的宽度和高度决定了元素的边框盒。就是说，为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。通过从已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。|
写一段代码看一下区别：

```
div {
  width: 200px;
  background: red;
  height: 200px;
  padding: 50px;
  margin: 50px;
  box-sizing:border-box;
  border: 10px solid;
}
```

![content-box](https://upload-images.jianshu.io/upload_images/2244949-2115c21348042fcb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


可以看到`content-box`中`width`仅计算`contentWidth`

![border-box](https://upload-images.jianshu.io/upload_images/2244949-87d18be582ad7368.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

而`border-box`中`width`是计算`contentWidth`+`padding`+`border`

在实际生产环境中个人更倾向于使用`border-box`，可以使我更直观地设置我想要达成的效果而免去考虑其他属性造成的影响。

