---
title: ES6之箭头函数
date: 2018-08-20 22:21:47
tags: Javascript
---

> 尽管ES9已经发布了...但是！并不妨碍我们箭头函数的当家地位！

> 本文标题虽然写的是箭头函数，但是这篇文章更多会是对ES6函数部分的一些特性做一个学习总结。

# 函数默认值

ES6之前，不能直接为函数的参数指定默认值，只能通过`a = a || 'exist'`形式来进行变通操作(`''`会被认为未声明)，为避免这个问题，通常可以先对参数是否被赋值做一次判定，再赋予默认值：
```js
if (typeof a === 'undefined'){
	a = 'exist'
}
```
而在ES6中允许为参数设置默认值，如：
```js
function log(x, y = 'World') {
  console.log(x, y);
}

log('Hello') // Hello World
log('Hello', 'China') // Hello China
log('Hello', '') // Hello

let x = 1; // error
const x = 2; // error
```
参数变量是默认声明的，所以不能用let或const再次声明。

## 与解构赋值默认值结合使用

参数默认值可以与解构赋值的默认值，结合起来使用。
```js
function foo({x, y = 5}) {
  console.log(x, y);
}

foo({}) // undefined 5
foo({x: 1}) // 1 5
foo({x: 1, y: 2}) // 1 2
foo() // TypeError: Cannot read property 'x' of undefined
```
上面代码只使用了对象的解构赋值默认值，没有使用函数参数的默认值。只有当函数foo的参数是一个对象时，变量x和y才会通过解构赋值生成。如果函数foo调用时没提供参数，变量x和y就不会生成，从而报错。通过提供函数参数的默认值，就可以避免这种情况。
```js
function foo({x, y = 5} = {}) {
  console.log(x, y);
}

foo() // undefined 5
```

## 作用域
一旦设置了参数的默认值，函数进行声明初始化时，参数会形成一个单独的作用域（context）。等到初始化结束，这个作用域就会消失。这种语法行为，在不设置参数默认值时，是不会出现的。
```js
var x = 1;

function f(x, y = x) {
  console.log(y);
}

f(2) // 2
```
上面代码中，参数y的默认值等于变量x。调用函数f时，参数形成一个单独的作用域。在这个作用域里面，默认值变量x指向第一个参数x，而不是全局变量x，所以输出是2。
```js
let x = 1;

function f(y = x) {
  let x = 2;
  console.log(y);
}

f() // 1
```
上面代码中，函数f调用时，参数y = x形成一个单独的作用域。这个作用域里面，变量x本身没有定义，所以指向外层的全局变量x。函数调用时，函数体内部的局部变量x影响不到默认值变量x。

如果此时，全局变量x不存在，就会报错。