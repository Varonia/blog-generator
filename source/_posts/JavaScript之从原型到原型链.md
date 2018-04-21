---
title: JavaScript之从原型到原型链
date: 2018-04-19 17:35:54
tags: JavaScript
---

> 是时候讲一讲`__proto__`和`prototype`的恩怨情仇了

# 什么是原型

JavaScript 常被描述为一种基于原型的语言 (prototype-based language)——每个对象拥有一个原型对象，对象以其原型为模板、从原型继承方法和属性。原型对象也可能拥有原型，并从中继承方法和属性，一层一层、以此类推。这种关系常被称为原型链 (prototype chain)，它解释了为何一个对象会拥有定义在其他对象中的属性和方法。

那什么是原型呢？你可以这样理解：每一个JavaScript对象(null除外)在创建的时候就会与之关联另一个对象，这个对象就是我们所说的原型，每一个对象都会从原型"继承"属性。

# 原型与原型链

我们首先通过构造函数创建一个对象实例来进行理解。

```js
function Person(){}

var person1 = new Person()
```

在控制台输入'person1.'，你会看到，浏览器将根据这个对象的可用的成员名称进行自动补全：
![](http://ww1.sinaimg.cn/large/7dbf9c78ly1fqib52cjlej20ep07sgm1.jpg)
在这个列表中，你可以看到定义在 person1 的原型对象、即 Person() 构造器中的成员—— `constructor`等。同时也有一些其他成员——`toString`、`valueOf`等这些成员定义在 Person() 构造器的原型对象、即 Object 之上。
下图展示了原型链的运作机制。
![](https://mdn.mozillademos.org/files/13891/MDN-Graphics-person-person-object-2.png)
那么，调用 person1 的“实际定义在 Object 上”的方法时，会发生什么？比如：

``person1.valueOf()``

这个方法发生了如下过程：

- 浏览器首先检查，person1 对象是否具有可用的 valueOf() 方法。
- 如果没有，则浏览器检查 person1 对象的原型对象（即 Person）是否具有可用的 valueof() 方法。
- 如果也没有，则浏览器检查 Person() 构造器的原型对象（即 Object）是否具有可用的 valueOf() 方法。Object 具有这个方法，于是该方法被调用，

没有官方的方法用于直接访问一个对象的原型对象——原型链中的“连接”被定义在一个内部属性中，在 JavaScript 语言标准中用 [[prototype]] 表示（参见 ECMAScript）。然而，大多数现代浏览器还是提供了一个名为 __proto__ （前后各有2个下划线）的属性，其包含了对象的原型。你可以尝试输入 person1.__proto__ 和 person1.__proto__.__proto__，看看代码中的原型链是什么样的。

# prototype

每个函数都有一个 prototype 属性，就是我们经常在各种例子中看到的那个 prototype ，比如：

```js
function Person() {

}
// 虽然写在注释里，但是你要注意：
// prototype是函数才会有的属性
Person.prototype.name = 'Kevin';
var person1 = new Person();
var person2 = new Person();
console.log(person1.name) // Kevin
console.log(person2.name) // Kevin
```

到此为止，我们可以将prototype和__proto__联系在一起了。

```js
function Person() {

}
var person = new Person();
console.log(person.__proto__ === Person.prototype); // true
```
