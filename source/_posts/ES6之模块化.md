---
title: ES6之模块化概述
date: 2018-09-10 22:01:44
tags: JavaScript
---

# type="module"
ES6中使用了新语法，支持模块化原生使用：
```html
<script type="module">
  import {hello} from './module1.js';

  hello();
</script>
```
```js
//module1.js

export function hello(){
	console.log("hello world!")
}
```
只需为 script 元素添加 type=module 属性，浏览器就会把该元素对应的内联脚本或外部脚本当成 ECMAScript 模块进行处理。具体使用方法可以参考MDN export/import相关说明。

但是目前为止，该语法仍然存在兼容性问题而无法随心所欲使用，所以就涉及到了下一方法：babel

# babel

Babel 是一个 JavaScript 编译器，可以将新版语法编译为获取浏览器兼容的 JavaScript 代码，但是该方法在官网上明确提出注意：

> 在浏览器中编译的用例非常有限， 因此如果你在生产环境下工作，你应该在服务端预编译脚本。

在我们进行简单页面搭建调试时就很难使用这种方法达到我们的目的，于是，我们又跳到了下一个坑：webpack

# webpack

webpack的鼎鼎大名我想大家都是知道的，本质上，webpack是一个现代JavaScript应用程序的静态模块打包器(module bundler)。当 webpack 处理应用程序时，它会递归地构建一个依赖关系图(dependency graph)，其中包含应用程序需要的每个模块，然后将所有这些模块打包成一个或多个 bundle。

webpack各种优点自不必提，但是它的环境搭建还是让人头疼不已，抱着能不能简单直接解决问题的心态，我们找到了下一个工具：Parcel

# Parcel

![Parcel](https://upload-images.jianshu.io/upload_images/2244949-32e0d5f85fad8f75.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Parcel的首页看着还是很清爽干净的，而它的操作语法也如同网页风格一般，简单粗暴，一气呵成。

```
npm init -y

npm install -g parcel-bundler

parcel index.html
```

不过大家使用parcel还是需要小心谨慎，生产环境还是慎用，自己的小项目可以实际操刀试试。