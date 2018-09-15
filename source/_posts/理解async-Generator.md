---
title: 理解Generator/async
date: 2018-09-08 16:32:22
tags: JavaScript
---

# Generator

说起Generator，就要先来讲一下JS中的异步实现。

JavaScript 语言对异步编程的实现，就是回调函数。所谓回调函数，就是把任务的第二段单独写在一个函数里面，等到重新执行这个任务的时候，就直接调用这个函数。但当有多个回调函数嵌套时，代码会很容易陷入一团乱麻，这种情况我们称为回调地狱。

为了解决这个问题，JS提出了Promise，允许将回调函数的横向加载，改成纵向加载。采用Promise，连续读取多个文件。那么Promise是否也存在一些缺点呢？是的，Promise的最大问题是代码冗余，原来的任务被Promise 包装了一下，不管什么操作，一眼看去都是一堆 then，原来的语义变得很不清楚。

在这种情况下，ES6提出了Generator函数，它最大特点就是可以交出函数的执行权（即暂停执行）。
```js
var g = gen(1);
g.next() // { value: 3, done: false }
g.next() // { value: undefined, done: true }
```

但是Generator在流程管理却不方便（即何时执行第一阶段、何时执行第二阶段），于是在ES2017 标准引入了 async 函数，使得异步操作变得更加方便。

# async

async 函数是什么？一句话，它就是 Generator 函数的语法糖。

```js
const asyncReadFile = async function () {
  const f1 = await readFile('/etc/fstab');
  const f2 = await readFile('/etc/shells');
  console.log(f1.toString());
  console.log(f2.toString());
};
```

async函数返回一个 Promise 对象，可以使用then方法添加回调函数。当函数执行的时候，一旦遇到await就会先返回，等到异步操作完成，再接着执行函数体内后面的语句。

async函数内部return语句返回的值，会成为then方法回调函数的参数。

```js
async function f() {
  return 'hello world';
}

f().then(v => console.log(v))
// "hello world"
```

有时，我们希望即使前一个异步操作失败，也不要中断后面的异步操作。这时可以将第一个await放在try...catch结构里面，这样不管这个异步操作是否成功，第二个await都会执行。

```js
async function f() {
  try {
    await Promise.reject('出错了');
  } catch(e) {
  }
  return await Promise.resolve('hello world');
}

f()
.then(v => console.log(v))
// hello world
```
或者采用
```js
async function f() {
  await Promise.reject('出错了')
    .catch(e => console.log(e));
  return await Promise.resolve('hello world');
}

f()
.then(v => console.log(v))
// 出错了
// hello world
```

