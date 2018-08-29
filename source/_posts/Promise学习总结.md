---
title: Promise学习总结
date: 2018-08-19 15:10:49
tags: Javascript
---

- [仓库地址](https://github.com/Varonia/promise-demo)

- Promise根据状态(``pending/Fulfilled/Rejected``)进行下一步链式操作的判定条件，一旦状态改变，就不会再变

- Promise在没有设置返回值时默认返回undefined

- Promise中如果嵌套了`then()`则按顺序完成
```javascript
new Promise( resolve => {
    console.log('Step 1');
    setTimeout(() => {
        resolve(100);
    }, 1000);
})
    .then( value => {
        return new Promise(resolve => {
            console.log('Step 1-1');
            setTimeout(() => {
                resolve(110);
            }, 1000);
        })
            .then( value => {
                console.log('Step 1-2');
                return value;
            })
            .then( value => {
                console.log('Step 1-3');
                return value;
            });
    })
    .then(value => {
        console.log(value);
        console.log('Step 2');
    });
// Step 1-1 Step 1-2 Step 1-3 Step 2    
```

- Promise会自动捕获内部异常，并交给`rejected`响应函数处理`-catch捕获/reject响应捕获`
```js
console.log('here we go');
new Promise( resolve => {
    setTimeout( () => {
        throw new Error('bye');
    }, 2000);
})
    .then( value => {
        console.log( value + ' world');
    })
    .catch( error => {
        console.log( 'Error：', error.message);
    });
```

- Promise的`catch`返回值依然认为是处于`Fulfilled`状态，继续执行`then()`，除非catch throw一个新的错误，则会置于`Rejected`状态

- Promise.prototype.finally()
`finally`方法用于指定不管 Promise 对象最后状态如何，都会执行的操作。
```js
promise
.then(result => {···})
.catch(error => {···})
.finally(() => {···});
```

- Promise.all
`Promise.all`方法用于将多个 Promise 实例，包装成一个新的 Promise 实例。
```js
const p = Promise.all([p1, p2, p3]);
```
    上面代码中，`Promise.all`方法接受一个数组作为参数，`p1`、`p2`、`p3`都是 Promise 实例，如果不是，就会先调用Promise.resolve方法，将参数转为 Promise 实例，再进一步处理。

    `p`的状态由`p1`、`p2`、`p3`决定，分成两种情况:
    1. 只有`p1`、`p2`、`p3`的状态都变成`fulfilled`，`p`的状态才会变成`fulfilled`，此时`p1`、`p2`、`p3`的返回值组成一个数组，传递给`p`的回调函数。
    2. 只要`p1`、`p2`、`p3`之中有一个被`rejected`，`p`的状态就变成`rejected`，此时第一个被`reject`的实例的返回值，会传递给`p`的回调函数。


- Promise.race
`Promise.race`方法同样是将多个 Promise 实例，包装成一个新的 Promise 实例。
区别在于只要`p1`、`p2`、`p3`之中有一个实例率先改变状态，`p`的状态就跟着改变。那个率先改变的 Promise 实例的返回值，就传递给`p`的回调函数。