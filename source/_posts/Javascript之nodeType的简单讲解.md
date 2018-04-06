---
title: Javascript之nodeType的简单讲解
date: 2018-04-05 21:25:29
tags:  Javascript
---

# Node类型

DOM1级定义了一个Node接口，该接口由DOM中所有节点类型实现。这个Node接口在JS中是作为Node类型实现的。在IE9以下版本无法访问到这个类型，JS中所有节点都继承自Node类型，都共享着相同的基本属性和方法。
Node有一个属性nodeType表示Node的类型，它是一个整数，其数值分别表示相应的Node类型，具体如下：

| 常量 | 值 | 描述 |
| --- | --- |
| Node.ELEMENT_NODE	| 1	| 一个元素节点，例如`<p>`和`<div>`。 |
| Node.TEXT_NODE | 3 | Element或者Attr中实际的文字 |
| Node.PROCESSING_INSTRUCTION_NODE | 7 | 一个用于XML文档的 ProcessingInstruction ，例如 <?xml-stylesheet ... ?> 声明。 |
| Node.COMMENT_NODE | 8	| 一个 Comment 节点。 |
| Node.DOCUMENT_NODE |9 | 一个 Document 节点。 |
| Node.DOCUMENT_TYPE_NODE | 10 | 描述文档类型的 DocumentType 节点。例如 <!DOCTYPE html>  就是用于 HTML5 的。 |
| Node.DOCUMENT_FRAGMENT_NODE | 11 | 一个 DocumentFragment 节点 |


假设我们要判断一个Node是不是元素，我们可以这样判断

```
if(someNode.nodeType == 1){
console.log("Node is a element");
}
```

这些Node类型中，我们最常用的就是`element`，`text`，`comment`，`document`，`document_fragment`这几种类型。

我们简单来介绍一下这几种类型：

### Element类型

Element提供了对元素标签名，子节点和特性的访问，我们常用HTML元素比如div，span，a等标签就是element中的一种。Element有下面几条特性：
（1）nodeType为1
（2）nodeName为元素标签名，tagName也是返回标签名
（3）nodeValue为null
（4）parentNode可能是Document或Element
（5）子节点可能是Element，Text，Comment，Processing_Instruction，CDATASection或EntityReference

### Text类型

Text表示文本节点，它包含的是纯文本内容，不能包含html代码，但可以包含转义后的html代码。Text有下面的特性：
（1）nodeType为3
（2）nodeName为#text
（3）nodeValue为文本内容
（4）parentNode是一个Element
（5）没有子节点

### Comment类型

Comment表示HTML文档中的注释，它有下面的几种特征：
（1）nodeType为8
（2）nodeName为#comment
（3）nodeValue为注释的内容
（4）parentNode可能是Document或Element
（5）没有子节点

### Document

Document表示文档，在浏览器中，document对象是HTMLDocument的一个实例，表示整个页面，它同时也是window对象的一个属性。Document有下面的特性：
（1）nodeType为9
（2）nodeName为#document
（3）nodeValue为null
（4）parentNode为null
（5）子节点可能是一个DocumentType或Element

### DocumentFragment类型

DocumentFragment是所有节点中唯一一个没有对应标记的类型，它表示一种轻量级的文档，可能当作一个临时的仓库用来保存可能会添加到文档中的节点。DocumentFragment有下面的特性：
（1）nodeType为11
（2）nodeName为#document-fragment
（3）nodeValue为null
（4）parentNode为null

我们简单地介绍了几种常见的Node类型，要记住，HTML中的节点并不只是包括元素节点，它还包括文本节点，注释节点等等。在这里我们只是简单地说明了几种常见的节点，想要进一步学习的同学可以查找一下相关资料。