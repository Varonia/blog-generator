---
title: call、apply与bind
date: 2018-04-29 16:12:21
tags: JavaScript
---

# call :
首先说明call的语法结构 ：``fun.call(thisArg, arg1, arg2, ...)``

- thisArg: 在fun函数运行时指定的this值，在非严格模式下如果声明为null和undefined的this值会自动指向全局对象(浏览器中就是window对象)

- arg1,arg2... : 接受的参数

可以让call()中的对象调用当前对象所拥有的function，也可以使用call()来实现继承，如``Array.prototype.slice.call(arguments)``可以将 类数组 转化为真正的数组。

# apply:

call()方法的作用和 apply() 方法类似，只有一个区别，就是 call()方法接受的是若干个参数的列表，而apply()方法接受的是一个包含多个参数的数组。

apply的语法结构：``func.apply(thisArg, [argsArray])``

apply的功能用法和call类似，通过动态改变this实现继承

# bind:

bind() 方法与 apply 和 call 很相似，也是可以改变函数体内 this 的指向。

MDN的解释是：bind()方法会创建一个新函数，称为绑定函数，当调用这个绑定函数时，绑定函数会以创建它时传入 bind()方法的第一个参数作为 this，传入 bind() 方法的第二个以及以后的参数加上绑定函数运行时本身的参数按照顺序作为原函数的参数来调用原函数。

使用范例代码如下
```
var foo = {
    bar : 1,
    eventBind: function(){
        $('.someClass').on('click',function(event) {
            console.log(this.bar);      //1
        }.bind(this));
    }
}
```

