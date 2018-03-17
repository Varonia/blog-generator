---
title: CSS之元素居中
date: 2018-03-17 17:45:39
tags: CSS
---
人们经常抱怨在CSS中居中元素的问题，其实这个问题其实并不复杂，只是因为方法众多，需要根据情况从众多方法中选取一个出来。

## 水平居中
#### 1. inline-block配合text-align  (可不定宽使用)
你可以轻松的在一个 block 元素中水平居中一个 inline 元素，以下代码对 inline，inline-block，inline-table 和 inline-flex 等有效。当子元素不是以上类型时可以设置``display: inline-block``。
```
.parent {
  text-align: center;
}
```
#### 2.margin:0 auto方法
在 block 元素被设定固定宽度的情况下，可以使用设置元素 margin-left 和 margin-right 的值为 auto 的方法实现水平居中。
```
.child {
  width: 100px;
  margin: 0 auto;
}
```
当block 元素未被设定固定宽度的情况下，只需要在子元素的css中加 ``display:table;``即可。
```
.parent {
  width: 200px;
  height: 200px;
  background: #ccc;
}
.child {
/*width: 100px;
  height: 100px; */
  background: rgba(199,1,1,0.2);
  display: table;
  margin: 0 auto;
}
```

#### 3. absolute配合transform （可不定宽使用）
```
.parent{
    position:relative;
}
.child{
    position:absolute;
    left:50%;
    transform: translateX(-50%);
}
```
#### 4. 使用Flex布局
```
.parent {
  display: flex;
  justify-content: center;
}
```
## 垂直居中
### 1. 垂直居中 inline 或者 inline-* 元素
#### 1.1 单行
inline/text 元素可以简单的用设置相同的上下 padding 值达到垂直居中的目的。
```
.center {
  pading-top: 30px;
  padding-bottom: 30px;
}
```
如果因为某种原因不能使用 padding 的方法，你还可以设置 line-height 等于 height来达到目的。
```
.center {
  height: 100px;
  line-height: 100px;
  white-space: nowrap;
}
```
#### 1.2 多行
相同的上下 padding 也可以适用于此种情况，如果不能生效，你可以尝试将该元素的父元素的 dispaly 设置为 table ，同时该元素的 dispaly 设置为 table-cell，然后设置 vertical-align。
```
.parent {
  display: table;
  width: 200px;
  height: 400px;
}
.child {
  display: table-cell;
  vertical-align: middle;
}
```
如果上述方法不能使用，你可以尝试使用 flexbox,一个单独的 flexbox 子元素可以轻易的在其父元素中居中。谨记，这种方法需要父元素有固定的高度。
```
.parent {
  display: flex;
  justify-content: center;
  flex-direction: column;
  height: 400px;
}
```
如果上述两种方式均不能使用，你可以使用“幽灵元素”技术，这种方法采用伪元素 ::before 撑开高度 ，文字垂直居中。
```
.parent {
  position: relative;
}
.parent::before {
  content: " ";
  display: inline-block;
  height: 100%;
  width: 1%;
  vertical-align: middle;
}
.child {
  display: inline-block;
  vertical-align: middle;
}
```
### 2. 垂直居中 block 类的元素
```
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}
```
使用 flexbox
```
.parent {
  display: flex;
  align-items: center;
}
```

## 水平垂直居中
#### 1. inline-block配合text-align加上table-cell配合vertical-align
```
.parent{
    display: table-cell;
    vertical-align:middle;
    text-align:center;
}
.child{
    display: inline-block;
}
```
不过使用这种方法需注意，如需实现严格的垂直居中需在父元素中设置``font-size:0；``

#### 2. absolute配合transform
```
.parent{
    position: relative;
}
.child{
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
}
```
#### 3. 使用 flexbox
```
.parent {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

>参考资料
[segmentfault: CSS之各种居中](https://segmentfault.com/a/1190000004260458)
[segmentfault: CSS居中完全指南](https://segmentfault.com/a/1190000004517401)