---
title: ES6之对象相关
date: 2018-09-07 22:07:01
tags: JavaScript
---

- Object.create()

创建一个新对象很简单，new一下就好了，但是创建一个空对象呢？当你查看创建的对象属性时会发现，对象依然保留一个属性：`__proto__`，这时就轮到本次主角登场了:
```
var a = Object.create(null)
```
这种写法还具有一个功能，那就是继承原型
```
var b = Object.create(Number.prototype)
```

- 属性定义

在日常使用中经常能遇到希望将代码中的变量放到对象中的情况，es6提供了支持。

```
var name = "Leo"
var object = { [name]: 1 }
// {Leo:1}
```

- get/set 方法

MDN解释两个函数时是这么说明的：get语法将对象属性绑定到查询该属性时将被调用的函数。当尝试设置属性时，set语法将对象属性绑定到要调用的函数。
还是举例说明吧：
```
var a = {
	_name: "Leo",
	get name(){return a._name},
	set name(value){}
}
a.name = "Oli"
a.name  //"Leo"
```

- 浅拷贝

在es5中浅拷贝我们通常使用遍历来完成，而es6中提供了几种方便的方式

```
var obj1 = {a:1,b:2,c:3}
var obj2 = Object.assign({},obj1)
```

```
var obj3 = {...obj1}

var aa = 1
var bb = 2
var obj4 = {...obj1, ...obj2, aa, bb, get x({return 'hi'})}
```

- defineProperty 方法

该方法可设置属性的get/set方法，利用这个方法可以解决一个很有意思的题
``a === 1 && a === 2 && a ===3``
```
var i = 0
Object.defineProperty(window,'a',{
	get(){
		i+=1
		return i
	}
	})
a === 1 && a === 2 && a ===3 //true
```
同时，该属性也是Vue实现双向绑定的一个重要底层原理

- 属性描述符

[MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)

