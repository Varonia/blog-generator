---
title: ES6之函数
date: 2018-08-20 22:21:47
tags: Javascript
---

> 尽管ES9已经发布了...

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

如果此时，全局变量x不存在，就会报错

# rest参数

ES6 引入 rest 参数（形式为...变量名），用于获取函数的多余参数，这样就不需要使用arguments对象了。rest 参数搭配的变量是一个数组，该变量将多余的参数放入数组中。rest本身就是数组，可以使用数组的方法。

```
function add(...values) {
  let sum = 0;

  for (var val of values) {
    sum += val;
  }

  return sum;
}

add(2, 5, 3) // 10
```
注意，rest 参数之后不能再有其他参数（即只能是最后一个参数），否则会报错。

# name属性

函数的name属性，返回该函数的函数名。
```
function foo() {}
foo.name // "foo"
```
如果将一个匿名函数赋值给一个变量，ES5 的name属性，会返回空字符串，而 ES6 的name属性会返回实际的函数名。
```
var f = function () {};

// ES5
f.name // ""

// ES6
f.name // "f"
```
如果将一个具名函数赋值给一个变量，则 ES5 和 ES6 的name属性都返回这个具名函数原本的名字。
```
const bar = function baz() {};

// ES5
bar.name // "baz"

// ES6
bar.name // "baz"
```
Function构造函数返回的函数实例，name属性的值为anonymous。
```
(new Function).name // "anonymous"
```
bind返回的函数，name属性值会加上bound前缀。
```
function foo() {};
foo.bind({}).name // "bound foo"

(function(){}).bind({}).name // "bound "
```

# 箭头函数

ES6 允许使用“箭头”（=>）定义函数。
```
var f = v => v;

// 等同于
var f = function (v) {
  return v;
};
```
如果箭头函数不需要参数或需要多个参数，就使用一个圆括号代表参数部分。
```
var f = () => 5;
// 等同于
var f = function () { return 5 };

var sum = (num1, num2) => num1 + num2;
// 等同于
var sum = function(num1, num2) {
  return num1 + num2;
};
```
箭头函数可以与变量解构结合使用。
```
const full = ({ first, last }) => first + ' ' + last;

// 等同于
function full(person) {
  return person.first + ' ' + person.last;
}
```

**使用注意点**
箭头函数有几个使用注意点。

（1）函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象。

（2）不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误。

（3）不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替。

（4）不可以使用yield命令，因此箭头函数不能用作 Generator 函数。

上面四点中，第一点尤其值得注意。this对象的指向是可变的，但是在箭头函数中，它是固定的。