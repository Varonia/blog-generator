---
title: Array的几个实用方法
date: 2018-04-16 16:12:23
tags: JavaScript
---

# 别致的Array方法小技巧

- concat方法：如果数组成员包括对象，concat方法返回当前数组的一个浅拷贝

- slice方法：通过call方法，在它们上面调用slice方法，可以将类似数组的对象转为真正的数组。

- reduce方法：由于该方法会遍历数组，所以实际上还可以用来做一些遍历相关的操作。

# 静态方法

## Array.isArray()

通过`Array.isArray()`来判断参数是否为数组，能有效弥补typeof运算符的不足

```js
var arr = [1, 2, 3];

typeof arr // "object"
Array.isArray(arr) // true

```


# 实例方法

## valueOf()，toString()

valueOf方法是一个所有对象都拥有的方法，表示对该对象求值。不同对象的valueOf方法不尽一致，数组的valueOf方法返回数组本身。toString方法也是对象的通用方法，数组的toString方法返回数组的字符串形式。

```js

var arr = [1, 2, 3];
arr.valueOf() // [1, 2, 3]
arr.toString() // "1,2,3"

var arr = [1, 2, 3, [4, 5, 6]];
arr.toString() // "1,2,3,4,5,6"

```

## push()，pop()

push方法用于在数组的末端添加一个或多个元素，并返回添加新元素后的*数组长度*;
pop方法用于删除数组的最后一个元素，并返回*该元素*。注意，两种方法都会改变原数组。

```js
var arr = [];

arr.push(1) // 1
arr.push('a') // 2
arr.push(true, {}) // 4
arr // [1, 'a', true, {}]

arr.pop() // {}
arr // [1, 'a', true]
```

## shift()，unshift()

shift方法用于删除数组的第一个元素，并返回该元素;
unshift方法用于在数组的第一个位置添加元素，并返回添加新元素后的数组长度。注意，两种方法都会改变原数组。

```js
var a = ['a', 'b', 'c'];

a.shift() // 'a'
a // ['b', 'c']

a.unshift('x'); // 3
a // ['x','b','c']
```

## join()

join方法以指定参数作为分隔符，将所有数组成员连接为一个字符串返回。如果不提供参数，默认用逗号分隔。
如果数组成员是undefined或null或空位，会被转成空字符串。

```js
['a',, 'b'].join('-')
// 'a--b'
```

## concat()

concat方法用于多个数组的合并。它将新数组的成员，添加到原数组成员的后部，然后返回一个新数组，原数组不变。

```js
['hello'].concat(['world'], ['!'])
// ["hello", "world", "!"]
```

如果数组成员包括对象，concat方法返回当前数组的一个浅拷贝。所谓“浅拷贝”，指的是新数组拷贝的是对象的引用。

```js
var obj = { a: 1 };
var oldArray = [obj];

var newArray = oldArray.concat();

obj.a = 2;
newArray[0].a // 2
```
上面代码中，原数组包含一个对象，concat方法生成的新数组包含这个对象的引用。所以，改变原对象以后，新数组跟着改变。

## reverse()

reverse方法用于颠倒排列数组元素，返回改变后的数组。注意，该方法将改变原数组。
```js
var a = ['a', 'b', 'c'];

a.reverse() // ["c", "b", "a"]
a // ["c", "b", "a"]
```

## slice()

slice方法用于提取目标数组的一部分，返回一个新数组，原数组不变。
它的第一个参数为起始位置（从0开始），第二个参数为终止位置（但该位置的元素本身不包括在内）。如果省略第二个参数，则一直返回到原数组的最后一个成员。	如果slice方法的参数是负数，则表示倒数计算的位置。

```js
var a = ['a', 'b', 'c'];

a.slice(0) // ["a", "b", "c"]
a.slice(1) // ["b", "c"]
a.slice(1, 2) // ["b"]
a.slice(2, 6) // ["c"]
a.slice(-2) // ["b", "c"]
a.slice(-2, -1) // ["b"]
```

slice方法的一个重要应用，是将类似数组的对象转为真正的数组。

```js
Array.prototype.slice.call({ 0: 'a', 1: 'b', length: 2 })
// ['a', 'b']

Array.prototype.slice.call(document.querySelectorAll("div"));
Array.prototype.slice.call(arguments);
```

## splice()

splice方法用于删除原数组的一部分成员，并可以在删除的位置添加新的数组成员，返回值是被删除的元素。注意，该方法会改变原数组。
splice的第一个参数是删除的起始位置（从0开始），第二个参数是被删除的元素个数。如果后面还有更多的参数，则表示这些就是要被插入数组的新元素。

```js
var a = ['a', 'b', 'c', 'd', 'e', 'f'];
a.splice(4, 2, 1, 2) // ["e", "f"]
a // ["a", "b", "c", "d", 1, 2]
```

起始位置如果是负数，就表示从倒数位置开始删除。

```js
var a = ['a', 'b', 'c', 'd', 'e', 'f'];
a.splice(-4, 2) // ["c", "d"]
```

## sort()

sort方法对数组成员进行排序，默认是按照字典顺序排序。排序后，原数组将被改变。
如果想让sort方法按照自定义方式排序，可以传入一个函数作为参数。

```js
[10111, 1101, 111].sort(function (a, b) {
  return a - b;
})
// [111, 1101, 10111]
```

上面代码中，sort的参数函数本身接受两个参数，表示进行比较的两个数组成员。如果该函数的返回值大于0，表示第一个成员排在第二个成员后面；其他情况下，都是第一个元素排在第二个元素前面。

```
[
  { name: "张三", age: 30 },
  { name: "李四", age: 24 },
  { name: "王五", age: 28  }
].sort(function (o1, o2) {
  return o1.age - o2.age;
})
// [
//   { name: "李四", age: 24 },
//   { name: "王五", age: 28  },
//   { name: "张三", age: 30 }
// ]
```

## map()

map方法将数组的所有成员依次传入参数函数，然后把每一次的执行结果组成一个新数组返回。

```js
var numbers = [1, 2, 3];

numbers.map(function (n) {
  return n + 1;
});
// [2, 3, 4]

numbers
// [1, 2, 3]
```

map方法接受一个函数作为参数。该函数调用时，map方法向它传入三个参数：当前成员、当前位置和数组本身。

```js
[1, 2, 3].map(function(elem, index, arr) {
  return elem * index;
});
// [0, 2, 6]
```

## forEach()

forEach方法与map方法很相似，也是对数组的所有成员依次执行参数函数。但是，forEach方法不返回值，只用来操作数据。这就是说，如果数组遍历的目的是为了得到返回值，那么使用map方法，否则使用forEach方法。

forEach的用法与map方法一致，参数是一个函数，该函数同样接受三个参数：当前值、当前位置、整个数组。

```js
function log(element, index, array) {
  console.log('[' + index + '] = ' + element);
}

[2, 5, 9].forEach(log);
// [0] = 2
// [1] = 5
// [2] = 9
```

forEach和map方法都不会跳过undefined和null，但会跳过空位。

## filter()

filter方法用于过滤数组成员，满足条件的成员组成一个新数组返回。

它的参数是一个函数，所有数组成员依次执行该函数，返回结果为true的成员组成一个新数组返回。该方法不会改变原数组。

```js
[1, 2, 3, 4, 5].filter(function (elem) {
  return (elem > 3);
})
// [4, 5]
```

filter方法的参数函数可以接受三个参数：当前成员，当前位置和整个数组。

```js
[1, 2, 3, 4, 5].filter(function (elem, index, arr) {
  return index % 2 === 0;
});
// [1, 3, 5]
```
indexOf方法还可以接受第二个参数，表示搜索的开始位置。

```
var a = ['a', 'b', 'c'];

a.indexOf('b') // 1
a.indexOf('a', 1) // -1
```


类似地，lastIndexOf方法返回给定元素在数组中最后一次出现的位置，如果没有出现则返回-1。

注意，这两个方法不能用来搜索NaN的位置，即它们无法确定数组成员是否包含NaN。

## reduce()，reduceRight()

reduce方法和reduceRight方法依次处理数组的每个成员，最终累计为一个值。它们的差别是，reduce是从左到右处理（从第一个成员到最后一个成员），reduceRight则是从右到左（从最后一个成员到第一个成员），其他完全一样。

```js
[1, 2, 3, 4, 5].reduce(function (a, b) {
  console.log(a, b);
  return a + b;
})
// 1 2
// 3 3
// 6 4
// 10 5
//最后结果：15
```

## indexOf()，lastIndexOf()

indexOf方法返回给定元素在数组中第一次出现的位置，如果没有出现则返回-1。
indexOf方法还可以接受第二个参数，表示搜索的开始位置。

```
var a = ['a', 'b', 'c'];

a.indexOf('b') // 1
a.indexOf('a', 1) // -1
```

类似地，lastIndexOf方法返回给定元素在数组中最后一次出现的位置，如果没有出现则返回-1。

注意，这两个方法不能用来搜索NaN的位置，即它们无法确定数组成员是否包含NaN。


> 大篇幅引用自[阮一峰JS教程](http://javascript.ruanyifeng.com/stdlib/array.html#toc5)