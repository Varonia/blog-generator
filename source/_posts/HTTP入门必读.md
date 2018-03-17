---
title: HTTP入门必读
date: 2018-03-03 15:21:12
tags: HTTP
---
废话不说，直接进入正文吧！

# W3C 简介（查维基百科）  

W3C这么大名鼎鼎的存在想必你肯定是听说过的吧，那么它到底是什么呢？

***

**万维网联盟**（**World Wide Web Consortium**，**W3C**），又称**W3C理事会**，是[万维网](https://zh.wikipedia.org/wiki/%E5%85%A8%E7%90%83%E8%B3%87%E8%A8%8A%E7%B6%B2 "万维网")的主要国际[标准组织](https://zh.wikipedia.org/wiki/%E6%A8%99%E6%BA%96%E7%B5%84%E7%B9%94 "标准组织")<sup>[[2]](https://zh.wikipedia.org/wiki/%E4%B8%87%E7%BB%B4%E7%BD%91%E8%81%94%E7%9B%9F#cite_note-consortium-2)</sup>。(引自维基百科)
*** 
<!-- more -->

**主要历史**

万维网联盟（W3C）由[蒂姆·伯纳斯-李（李爵士）](https://zh.wikipedia.org/wiki/%E6%8F%90%E5%A7%86%C2%B7%E6%9F%8F%E5%85%A7%E8%8C%B2-%E6%9D%8E "蒂姆·伯纳斯-李")于1994年10月离开[欧洲核子研究中心](https://zh.wikipedia.org/wiki/%E6%AD%90%E6%B4%B2%E6%A0%B8%E5%AD%90%E7%A0%94%E7%A9%B6%E7%B5%84%E7%B9%94 "欧洲核子研究中心")（CERN）后成立，在[欧盟执委会](https://zh.wikipedia.org/wiki/%E6%AD%90%E7%9B%9F%E5%9F%B7%E5%A7%94%E6%9C%83 "欧盟执委会")和[国防高等研究计划署](https://zh.wikipedia.org/wiki/%E5%9C%8B%E9%98%B2%E9%AB%98%E7%AD%89%E7%A0%94%E7%A9%B6%E8%A8%88%E5%8A%83%E7%BD%B2 "国防高等研究计划署")（DARPA）的支持下成立于[麻省理工学院](https://zh.wikipedia.org/wiki/%E9%BA%BB%E7%9C%81%E7%90%86%E5%B7%A5%E5%AD%B8%E9%99%A2 "麻省理工学院")[MIT计算机科学与人工智能实验室](https://zh.wikipedia.org/wiki/MIT%E8%A8%88%E7%AE%97%E6%A9%9F%E7%A7%91%E5%AD%B8%E8%88%87%E4%BA%BA%E5%B7%A5%E6%99%BA%E6%85%A7%E5%AF%A6%E9%A9%97%E5%AE%A4 "MIT计算机科学与人工智能实验室")（MIT／LCS）<sup>[[2]](https://zh.wikipedia.org/wiki/%E4%B8%87%E7%BB%B4%E7%BD%91%E8%81%94%E7%9B%9F#cite_note-consortium-2)</sup>，DARPA曾率先推出了[互联网](https://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%AF%E7%B6%B2 "互联网")及其前身[ARPANET](https://zh.wikipedia.org/wiki/ARPANET "ARPANET")。

该组织试图通过W3C制定的新标准来促进业界成员间的兼容性和协议。不兼容的HTML版本由不同的供应商提供，导致网页显示方式不一致。联盟试图让所有的供应商实施一套由联盟选择的核心原则和组件。

***

**标准**

为解决网络应用中不同平台、技术和开发者带来的不兼容问题，保障网络信息的顺利和完整流通，万维网联盟制定了一系列标准并督促网络应用开发者和内容提供者遵循这些标准。标准的内容包括使用语言的规范，开发中使用的导则和解释引擎的行为等等。W3C也制定了包括[XML](https://zh.wikipedia.org/wiki/XML "XML")和[CSS](https://zh.wikipedia.org/wiki/CSS "CSS")等的众多影响深远的标准规范。

但是，W3C制定的网络标准似乎并非强制而只是推荐标准。因此部分网站仍然不能完全实现这些标准。特别是使用早期[所见即所得](https://zh.wikipedia.org/wiki/%E6%89%80%E8%A7%81%E5%8D%B3%E6%89%80%E5%BE%97 "所见即所得")[网页](https://zh.wikipedia.org/wiki/%E7%BD%91%E9%A1%B5 "网页")编辑软件设计的网页往往会包含大量非标准代码。

***


# MDN 简介（查维基百科）
<br>
MDN？这是什么？想必很多刚入行的人都有这个疑问，直接贴个新闻给你们看。

[Mozilla brings Microsoft, Google, the W3C, Samsung together to create cross-browser documentation on MDN – The Mozilla Blog](https://blog.mozilla.org/blog/2017/10/18/mozilla-brings-microsoft-google-w3c-samsung-together-create-cross-browser-documentation-mdn/)

内容大概是：Mozilla, Microsoft, Google, Samsung 和 W3C 将合作把 MDN 打造成最好的 Web 文档。今天开始，Microsoft 会把 MSDN 上相关的页面重定向到 MDN。这是17年10月的新闻哦。

那么，MDN的简介来咯~

***

**MDN Web Docs**（旧称Mozilla Developer Network、Mozilla Developer Center，简称MDN）是一个汇集众多[Mozilla基金会](https://zh.wikipedia.org/wiki/Mozilla%E5%9F%BA%E9%87%91%E6%9C%83 "Mozilla基金会")产品和网络技术开发文档的免费网站<sup>[[1]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-1)</sup>。

***

**历史**

该项目始于2005年，最初由Mozilla公司员工Deb Richardson领导。自2006年以来，文档工作由Eric Shepherd领导<sup>[[2]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-MitchellBlog-2)</sup>。

网站最初的内容是由[DevEdge](https://zh.wikipedia.org/wiki/%E7%B6%B2%E6%99%AF#%E8%A7%A3%E6%95%A3 "网景")提供，但在[AOL](https://zh.wikipedia.org/wiki/AOL "AOL")收购Netscape后，DevEdge网站也宣布关闭。为此Mozilla基金会向AOL获取了DevEdge发布的内容<sup>[[3]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-3)</sup><sup>[[2]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-MitchellBlog-2)</sup>，同时将DevEdge内容搬移到mozilla.org<sup>[[4]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-4)</sup><sup>[[5]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-DriaDevedge-temp-5)</sup>。

MDN本身有一个论坛，并在Mozilla IRC网络上有一个[IRC](https://zh.wikipedia.org/wiki/IRC "IRC")频道#mdn。MDN由[Mozilla公司](https://zh.wikipedia.org/wiki/Mozilla%E5%85%AC%E5%8F%B8)提供服务器和员工的资助。

2016年10月3日发表的[Brave](https://zh.wikipedia.org/wiki/Brave_(%E7%BD%91%E9%A1%B5%E6%B5%8F%E8%A7%88%E5%99%A8) "Brave (网页浏览器)")网页浏览器将MDN作为其[搜索引擎](https://zh.wikipedia.org/wiki/%E6%90%9C%E5%B0%8B%E5%BC%95%E6%93%8E "搜索引擎")选项之一<sup>[[6]](https://zh.wikipedia.org/wiki/MDN_Web_Docs#cite_note-6)</sup>。

***

# HTML 所有标签列表（查 MDN）

## 根元素

| Element | Description |
| --- | --- |
| [`<html>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/html "HTML <html> 元素 表示一个HTML文档的根（顶级元素），所所以它也被称为根元素。其他所有其他元素必须是此元素的后代。") | 代表 HTML 或 XHTML 文档的根。其他所有元素必须是这个元素的子节点。 |

***

## 文档元数据

| Element | Description |
| --- | --- |
| [`<head>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/head "HTML head 元素 规定文档相关的通用信息（元数据），包括文档的标题，文档的样式和脚本的链接（定义）等。") | 代表关于文档元数据的一个集合，包括脚本或样式表的链接或内容。 |
| [`<title>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/title "HTML <title> 元素 定义文档的标题，显示在浏览器的标题栏或标签页上。它只可以包含文本，若是包含有标签，则包含的任何标签都不会被解释。") | 定义文档的标题，将显示在浏览器的标题栏或标签页上。该元素只能包含文本，包含的标签不会被解释。 |
| [`<base>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/base "HTML <base> 元素 指定用于一个文档中包含的所有相对URL的基本URL。一份中只能有一个<base>元素。") | 定义页面上相对 URL 的基准 URL。 |
| [`<link>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link "HTML 中<link>元素指定了外部资源与当前文档的关系. 这个元素的使用方法包括为导航定义关系框架.这个元素经常用来链接css文件。") | 用于链接外部的 CSS 到该文档。 |
| [`<meta>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta "HTML <meta> 元素表示那些不能由其它HTML元相关元素 (<base>, <link>, <script>, <style> 或 <title>) 之一表示的任何元数据信息.") | 定义其他 HTML 元素无法描述的元数据。 |
| [`<style>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/style "HTML的<style>元素包含了文档的样式化信息或者文档的一部分。指定的样式化星系包含的该元素内，通常是CSS的格式。") | 用于内联 CSS。 |

***

## 脚本

| Element | Description |
| --- | --- |
| [`<script>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/script "HTML <script> 元素用于嵌入或引用可执行脚本。") | 定义一个内联脚本或链接到外部脚本。脚本语言是 JavaScript。 |
| [`<noscript>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/noscript "如果页面上的脚本类型不受支持或者当前在浏览器中关闭了脚本，则HTML 元素定义要插入的html部分。") | 定义当浏览器不支持脚本时显示的替代文字。 |
| [`<template>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/template "HTML <template> 元素 是一种用于保存客户端内容的机制，该内容在页面加载时不被渲染，但可以在运行时使用JavaScript进行实例化。")| 通过 JavaScript 在运行时实例化内容的容器。 |

***

## 章节

| Element | Description |
| --- | --- |
| [`<body>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/body "HTML 主体元素 (<body>) 表示的是HTML文档的主体内容，任何一个HTML文档，只允许存在一个 <body> 元素。") | 代表 HTML 文档的内容。在文档中只能有一个 `<body>` 元素。 |
| [`<section>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/section "HTML Section 元素 (<section>) 表示文档中的一个区域（或节），比如，内容中的一个专题组，一般来说会有包含一个标题（heading）。一般通过是否包含一个标题 (<h1>-<h6> element) 作为子节点 来 辨识每一个<section>。") | 定义文档中的一个章节。 |
| [`<nav>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/nav "HTML导航栏 (<nav>) 描绘一个含有多个超链接的区域，这个区域包含转到其他页面，或者页面内部其他部分的链接列表.")  | 定义只包含导航链接的章节。 |
| [`<article>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/article "<article>元素表示文档、页面、应用或网站中的独立结构，其意在成为可独立分配的或可复用的结构，如在发布中，它可能是论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。") | 定义可以独立于内容其余部分的完整独立内容块。 |
| [`<aside>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/aside "<aside> 元素表示一个和其余页面内容几乎无关的部分，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。其通常表现为侧边栏或者嵌入内容。他们通常包含在工具条，例如来自词汇表的定义。也可能有其他类型的信息，例如相关的广告、笔者的传记、web 应用程序、个人资料信息，或在博客上的相关链接。") | 定义和页面内容关联度较低的内容——如果被删除，剩下的内容仍然很合理。 |
| [`<h1>,<h2>,<h3>,<h4>,<h5>,<h6>`](https://developer.mozilla.org/zh-CN/docs/HTML/Element/Heading_Elements) | 标题元素实现了六层文档标题，`<h1>` 是最大的标题，`<h6>` 是最小的标题。标题元素简要地描述章节的主题。 |
| [`<header>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/header "<header>元素表示一组引导性的帮助，可能包含标题元素，也可以包含其他元素，像logo、分节头部、搜索表单等。") | 定义页面或章节的头部。它经常包含 logo、页面标题和导航性的目录。 |
| [`<footer>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/footer "HTML <footer> 元素表示最近一个章节内容或者根节点（sectioning root ）元素的页脚。一个页脚通常包含该章节作者、版权数据或者与文档相关的链接等信息。")  | 定义页面或章节的尾部。它经常包含版权信息、法律信息链接和反馈建议用的地址。 |
| [`<address>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/address "HTML 的<address>元素可以让作者为它最近的<article>或者<body>祖先元素提供联系信息。在后一种情况下，它应用于整个文档。") | 定义包含联系信息的一个章节。 |
| [`<main>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/main "HTML Main元素()呈现了文档<body>或应用的主体部分。主体部分由与文档直接相关，或者扩展于文档的中心主题、应用的主要功能部分的内容组成。这部分内容在文档中应当是独一无二的，不包含任何在一系列文档中重复的内容，比如侧边栏，导航栏链接，版权信息，网站logo，搜索框（除非搜索框作为文档的主要功能）。") | 定义文档中主要或重要的内容。 |

***

## 组织内容

| Element | Description |
| --- | --- |
| [`<p>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p "HTML <p>元素（或者说 HTML 段落元素）表示文本的一个段落。该元素通常表现为一整块与相邻文本分离的文本，或以垂直的空白隔离或以首行缩进。另外，<p> 是块级元素。") | 定义一个段落。 |
| [`<hr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/hr "HTML <hr> 元素表示段落级元素之间的主题转换（例如，一个故事中的场景的改变，或一个章节的主题的改变）。在HTML的早期版本中，它是一个水平线。现在它仍能在可视化浏览器中表现为水平线，但目前被定义为语义上的，而不是表现层面上。") | 代表章节、文章或其他长内容中段落之间的分隔符。 |
| [`<pre>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/pre "HTML <pre> 元素表示预定义格式文本。在该元素中的文本通常按照原文件中的编排，以等宽字体的形式展现出来，文本中的空白符（比如空格和换行符）都会显示出来。(紧跟在 <pre> 开始标签后的换行符也会被省略)") | 代表其内容已经预先排版过，格式应当保留 。 |
| [`<blockquote>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote "HTML中的元素（或者 HTML 块级引用元素），代表其中的文字是引用内容。通常在渲染时，这部分的内容会有一定的缩进（注 中说明了如何更改）。若引文来源于网络，则可以将原内容的出处 URL 地址设置到 cite 特性上，若要以文本的形式告知读者引文的出处时，可以通过 <cite> 元素。") | 代表引用自其他来源的内容。 |
| [`<ol>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol "HTML <ol> 元素 表示多个有序列表项，通常渲染为有带编号的列表。") | 定义一个有序列表。 |
| [`<ul>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul "The HTML <ul> 元素 ( 或 HTML 无序列表元素） 代表多项的无序列表，即无数值排序项的集合，且它们在列表中的顺序是没有意义的。通常情况下，无序列表项的头部可以是几种形式，如一个点，一个圆形或方形。头部的风格并不是在页面的HTML描述定义, 但在其相关的CSS 可以用 list-style-type 属性。") | 定义一个无序列表。 |
| [`<li>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/li "HTML <li> 元素 (或者 HTML 列表条目元素) 用于表示列表里的条目。它必须被包含在一个父元素里：一个有顺序的列表(<ol>)，一个无顺序的列表(<ul>)，或者一个菜单 (<menu>)。在菜单或者无顺序的列表里，列表条目通常用点排列显示。在有顺序的列表里，列表条目通常是在左边有按升序排列计数的显示，例如数字或者字母。") | 定义列表中的一个列表项。 |
| [`<dl>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/dl "HTML <dl> 元素 （或 HTML 描述列表元素）是一个包含术语定义以及描述的列表，通常用于展示词汇表或者元数据 (键-值对列表)。") | 定义一个定义列表（一系列术语和其定义）。 |
| [`<dt>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/dt "HTML <dt> 元素 （或 HTML 术语定义元素）用于在一个定义列表中声明一个术语。该元素仅能作为 <dl> 的子元素出现。通常在该元素后面会跟着 <dd> 元素， 然而，多个连续出现的 <dt> 元素都将由出现在它们后面的第一个 <dd> 元素定义。") | 代表一个由下一个 `<dd>` 定义的术语。 |
| [`<dd>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/dd "HTML <dd> 元素（HTML 描述元素）用来指明一个描述列表  (<dl>) 元素中一个术语的描述。这个元素只能作为描述列表元素的子元素出现，并且必须跟着一个 <dt> 元素。") | 代表出现在它之前术语的定义。 |
| [`<figure>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/figure "HTML <figure> 元素代表一段独立的内容, 经常与说明(caption) <figcaption> 配合使用, 并且作为一个独立的引用单元。当它属于主体(main flow)时，它的位置独立于主体。这个标签经常是在主文中引用的图片，插图，表格，代码段等等，当这部分转移到附录中或者其他页面时不会影响到主体。") | 代表一个和文档有关的图例。 |
| [`<figcaption>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/figcaption "HTML <figcaption> 元素 是与其相关联的图片的说明/标题，用?于描述其父节点 <figure> 元素里的其他数据。这意味着 <figcaption> 在<figure> 块里是第一个或最后一个。同时 HTML Figcaption 元素是可选的；如果没有该元素，这个父节点的图片只是会没有说明/标题。")   | 代表一个图例的说明。 |
| [`<div>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div "HTML <div> 元素 (或 HTML 文档分区元素) 是一个通用型的流内容容器，它在语义上不代表任何特定类型的内容，它可以被用来对其它元素进行分组，一般用于样式化相关的需求（使用 class 或 id 特性) 或者对具有相同特性的一组元素进行分组 (比如 lang)，它应该在没有任何其它语义元素可用时才使用 (比如 <article> 或 <nav>) 。") | 代表一个通用的容器，没有特殊含义。 |

***

## 文字形式

| Element | Description |
| --- | --- |
| [`<a>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a "HTML <a> 元素  (或锚元素) 可以创建一个到其他网页、文件、同一页面内的位置、电子邮件地址或任何其他URL的超链接。") | 代表一个链接到其他资源的*超链接* 。 |
| [`<em>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/em "HTML 着重元素 (<em>) 标记出需要用户着重阅读的内容， <em> 元素是可以嵌套的，嵌套层次越深，则其包含的内容被认定为越需要着重阅读。") | 代表*强调* 文字。 |
| [`<strong>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/strong "Strong 元素 (<strong>)表示文本十分重要，一般用粗体显示。") | 代表*特别重要* 文字。 |
| [`<small>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/small "HTML 中的元素將使文本的字体变小一号。(例如从大变成中等，从中等变成小，从小变成超小)。在HTML5中，除了它的样式含义，这个元素被重新定义为表示边注释和附属细则，包括版权和法律文本。") | 代表*注释* ，如免责声明、版权声明等，对理解文档不重要。 |
| [`<s>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/s "HTML <s> 元素 使用删除线来渲染文本。使用 <s> 元素来表示不再相关，或者不再准确的事情。但是当表示文档编辑时，不提倡使用 <s> ；为此，提倡使用 <del> 和 <ins> 元素。") | 代表*不准确或不相关* 的内容。 |
| [`<cite>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/cite "HTML引用（ Citation）标签 (<cite>) 表示一个作品的引用。它必须包含引用作品的符合简写格式的标题或者URL，它可能是一个根据添加引用元数据的约定的简写形式。") | 代表*作品标题* 。 |
| [`<q>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/q "HTML引用标签 (<q>)表示一个封闭的并且是短的行内引用的文本. 这个标签是用来引用短的文本，所以请不要引入换行符; 对于长的文本的引用请使用 <blockquote> 替代.") | 代表内联的*引用* 。 |
| [`<dfn>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/dfn "HTML 定义元素 (<dfn>) 表示术语的一个定义。") | 代表一个术语包含在其最近祖先内容中的*定义* 。 |
| [`<abbr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/abbr "HTML <abbr>元素代表缩写，并可选择提供一个完整的描述。") | 代表*省略* 或*缩写* ，其完整内容在 `title` 属性中。 |
| [`<data>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/data "HTML <data> 元素 将一个指定内容和机器可读的翻译联系在一起。但如果内容是与 time 或者 date 相关的，一定要使用 <time>。")   | 关联一个内容的*机器可读的等价形式* （该元素只在 WHATWG 版本的 HTML 标准中，不在 W3C 版本的 HTML5 标准中）。 |
| [`<time>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/time "HTML time 标签(<time>) 用来表示24小时制时间或者公历日期，若表示日期则也可包含时间和时区。")  | 代表*日期* 和*时间* 值；机器可读的等价形式通过 `datetime` 属性指定。 |
| [`<code>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/code "HTML <code> 元素呈现一段计算机代码. 默认情况下, 它以浏览器的默认等宽字体显示.") | 代表*计算机代码* 。 |
| [`<var>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/var "<var> 标签表示变量的名称，或者由用户提供的值。") | 代表*代码中的变量* 。 |
| [`<samp>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/samp "<samp> 元素用于标识计算机程序输出，通常使用浏览器缺省的 monotype 字体（例如 Lucida Console）。") | 代表程序或电脑的*输出* 。 |
| [`<kbd>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/kbd "HTML键盘输入元素(<kbd>) 用于表示用户输入，它将产生一个行内元素，以浏览器的默认monospace字体显示。") | 代表*用户输入* ，一般从键盘输出，但也可以代表其他输入，如语音输入。 |
| [`<sub>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/sub "HTML <sub> 元素定义了一个文本区域，出于排版的原因，与主要的文本相比，应该展示得更低并且更小。"),[`<sup>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/sup "HTML <sup> 元素定义了一个文本区域，出于排版的原因，与主要的文本相比，应该展示得更高并且更小。") | 分别代表*下标* 和*上标* 。 |
| [`<i>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/i "HTML元素 <i> 用于表现因某些原因需要区分普通文本的一系列文本。例如技术术语、外文短语或是小说中人物的思想活动等，它的内容通常以斜体显示。") | 代表一段*不同性质* 的文字，如技术术语、外文短语等。 |
| [`<b>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/b "HTML <b>元素表表示相对于普通文本字体上的区别，但不表示任何特殊的强调或者关联，通常以粗体显示。") | 代表一段*需要被关注* 的文字。 |
| [`<u>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/u "HTML <u> 元素使文本在其内容的基线下的一行呈现下划线。在HTML5中, 此元素表示具有未标注的文本跨度，显示渲染，非文本注释，例如将文本标记为中文文本中的专有名称(一个正确的中文标记), 或 将文本标记为拼写错误。") | 代表一段需要*下划线*呈现的文本注释，如标记出拼写错误的文字等。 |
| [`<mark>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/mark "这个 HTML mark 标签代表突出显示的文字,例如可以为了标记特定上下文中的文本而使用这个标签. 举个例子，它可以用来显示搜索引擎搜索后关键词。")  | 代表一段需要被高亮的*引用* 文字。 |
| [`<ruby>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ruby "HTML <ruby> 元素 被用来展示东亚文字注音或字符注释。") | 代表被*ruby 注释* 标记的文本，如中文汉字和它的拼音。 |
| [`<rt>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/rt "HTML <rt> element 包含字符的发音，字符在 ruby 注解中出现，它用于描述东亚字符的发音。这个元素始终在 <ruby> 元素中使用。")   | 代表*ruby 注释* ，如中文拼音。 |
| [`<rp>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/rp "HTML <rp> 元素用于为那些不能使用 <ruby> 元素展示 ruby 注解的浏览器，提供随后的圆括号。")   | 代表 ruby 注释两边的*额外插入文本* ，用于在不支持 ruby 注释显示的浏览器中提供友好的注释显示。 |
| [`<bdi>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/bdi "HTML <bdi> 元素 (双向隔离元素) 会隔离可能以不同方向进行格式化的外部文本。")   | 代表需要*脱离* 父元素文本方向的一段文本。它允许嵌入一段不同或未知文本方向格式的文本。 |
| [`<bdo>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/bdo "<bdo> 元素 (HTML双向覆盖元素)用于覆盖当前文本的朝向，它使得字符按给定的方向排列。") | 指定子元素的*文本方向* ，显式地覆盖默认的文本方向。 |
| [`<span>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/span "HTML <span> 元素是短语内容的通用行内容器，并没有任何特殊语义。可以使用它来编组元素以达到某种样式意图（通过使用类或者Id属性），或者这些元素有着共同的属性，比如lang。应该在没有其他合适的语义元素时才使用它。<span> 与 <div> 元素很相似，但 <div> 是一个 块元素 而 <span> 则是  行内元素 .") | 代表一段没有特殊含义的文本，当其他语义元素都不适合文本时候可以使用该元素。 |
| [`<br>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/br "HTML 元素 换行 <br> 在文本中产生一个换行（回车键）。这对于写诗或写一个地址来说显得很有用。它可以将行明显地分开。") | 代表*换行* 。 |
| [`<wbr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/wbr "HTML <wbr> 元素  — 一个文本中的位置，其中浏览器可以选择来换行，虽然它的换行规则可能不会在这里换行。")  | 代表*建议换行 (Word Break Opportunity)* ，当文本太长需要换行时将会在此处添加换行符。 |

***

## 编辑

| Element | Description |
| --- | --- |
| [`<ins>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ins "HTML <ins> 元素定义已经被插入文档中的文本。") | 定义*增加* 到文档的内容。 |
| [`<del>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/del "HTML 删除文字元素（<del>）表示已经从文档中删除的文本范围。此元素通常是（但不必）呈现删除线的文本。") | 定义从文档*移除* 的内容。 |

***

## 嵌入内容

| Element | Description |
| --- | --- |
| [`<img>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img "HTML Image 元素（ <img> ）代表文档中的一个图像。") | 代表一张*图片* 。 |
| [`<iframe>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/iframe "HTML内联框架元素 <iframe> 表示嵌套的浏览上下文，有效地将另一个HTML页面嵌入到当前页面中。在HTML 4.01中，文档可能包含头部和正文，或头部和框架集，但不能包含正文和框架集。但是，<iframe>可以在正常的文档主体中使用。每个浏览上下文都有自己的会话历史记录和活动文档。包含嵌入内容的浏览上下文称为父浏览上下文。顶级浏览上下文（没有父级）通常是浏览器窗口。") | 代表一个*内联的框架* 。 |
| [`<embed>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/embed "HTML <embed> 元素 用于表示一个外部应用或交互式内容的集合点，换句话说，就是一个插件。")   | 代表一个*嵌入* 的外部资源，如应用程序或交互内容。 |
| [`<object>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/object "HTML <object> 元素（或者称作 HTML 嵌入对象元素）表示引入一个外部资源，这个资源可能是一张图片，一个嵌入的浏览上下文，亦或是一个插件所使用的资源。") | 代表一个*外部资源* ，如图片、HTML 子文档、插件等。 |
| [`<param>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/param "HTML <param> 元素(或 HTML Parameter 元素) 定义了 <object>的参数") | 代表 `<object>` 元素所指定的插件的*参数* 。 |
| [`<video>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video "HTML <video> 元素 用于在HTML或者XHTML文档中嵌入视频内容。")   | 代表一段*视频* 及其视频文件和字幕，并提供了播放视频的用户界面。 |
| [`<audio>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio "HTML <audio> 元素用于在文档中表示音频内容。 <audio> 元素可以包含多个音频资源， 这些音频资源可以使用 src 属性或者<source> 元素来进行描述； 浏览器将会选择最合适的一个来使用。对于不支持<audio>元素的浏览器，<audio>元素也可以作为浏览器不识别的内容加入到文档中。")   | 代表一段*声音* ，或*音频流* 。 |
| [`<source>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source "The HTML <source> element specifies multiple media resources for either the <picture>, the <audio> or the <video> element. It is an empty element. It is commonly used to serve the same media content in multiple formats supported by different browsers.")   | 为 `<video>` 或 `<audio>` 这类媒体元素指定*媒体源* 。 |
| [`<track>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/track "HTML <track> 元素 被当作媒体元素—<audio> 和 <video>的子元素来使用。它允许指定计时字幕（或者基于事件的数据），例如自动处理字幕。")  | 为 `<video>` 或 `<audio>` 这类媒体元素指定*文本轨道（字幕）* 。 |
| [`<canvas>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/canvas "<canvas>元素可被用来通过脚本（通常是JavaScript）绘制图形。比如,它可以被用来绘制图形,制作图片集合,甚至用来实现动画效果。你可以(也应该)在元素标签内写入可提供替代的的代码内容，这些内容将会在在旧的、不支持<canvas>元素的浏览器或是禁用了JavaScript的浏览器内渲染并展现。")  | 代表*位图区域* ，可以通过脚本在它上面实时呈现图形，如图表、游戏绘图等。 |
| [`<map>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/map "HTML <map> 属性 与 <area> 属性一起使用来定义一个图像映射(一个可点击的链接区域).") | 与 `<area>` 元素共同定义*图像映射* 区域。 |
| [`<area>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/area "HTML <area> 元素 在图片上定义一个热点区域") | 与 `<map>` 元素共同定义*图像映射* 区域。 |
| [`<svg>`](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Element/svg "思考下下面的svg图片（代表意大利国旗）：")  | 定义一个嵌入式*矢量图* 。 |
| [`<math>`](https://developer.mozilla.org/zh-CN/docs/Web/MathML/Element/math)  | 定义一段*数学公式* 。 |

***

## 表格

| Element | Description |
| --- | --- |
| [`<table>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table "HTML的 table 元素表示表格数据 — 即通过二维数据表表示的信息。") | 定义*多维数据* 。 |
| [`<caption>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption "HTML <caption> 元素 (or HTML 表格标题元素) 展示一个表格的标题， 它常常作为 <table> 的第一个子元素出现，同时显示在表格内容的最前面，但是，它同样可以被CSS样式化，所以，它同样可以出现在任何一个一个相对于表格的做任意位置。") | 代表*表格的标题* 。 |
| [`<colgroup>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/colgroup "HTML 中的 表格列组（Column Group <colgroup>） 标签用来定义表中的一组列表。") | 代表表格中一组*单列或多列* 。 |
| [`<col>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/col "HTML <col> 元素 定义表格中的列，并用于定义所有公共单元格上的公共语义。它通常位于<colgroup>元素内。") | 代表表格中的*列* 。 |
| [`<tbody>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/tbody "这个 HTML 标签  元素在一个  元素中可以出现一个或者更多。") | 代表表格中一块*具体数据* （表格主体）。 |
| [`<thead>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/thead "HTML的<thead>元素定义了一组定义表格的列头的行。") | 代表表格中一块*列标签* （表头）。 |
| [`<tfoot>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/tfoot "此页面仍未被本地化, 期待您的翻译!") | 代表表格中一块*列摘要* （表尾）。 |
| [`<tr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/tr "HTML <tr> 元素定义表格中的行。 Those can be a mix of <td> and <th> elements.") | 代表表格中的*行* 。 |
| [`<td>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td "The Table cell HTML element (<td>) defines a cell of a table that contains data. It participates in the table model.") | 代表表格中的*单元格* 。 |
| [`<th>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th "此页面仍未被本地化, 期待您的翻译!") | 代表表格中的*头部单元格* 。 |

***

## 表单

| Element | Description |
| --- | --- |
| [`<form>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form "HTML <form> 元素 表示了文档中的一个区域，这个区域包含有交互控制元件，用来向web服务器提交信息。") | 代表一个*表单* ，由控件组成。 |
| [`<fieldset>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset "此页面仍未被本地化, 期待您的翻译!") | 代表*控件组* 。 |
| [`<legend>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend "HTML的元素（也称为HTML的域说明元素（or HMTL  Legend Field Element））代表一个用于表示它的父元素<fieldset>的内容的标题。") | 代表 `<fieldset>` 控件组的*标题* 。 |
| [`<label>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label "HTML 元素表示用户界面中项目的标题。") | 代表表单控件的*标题* 。 |
| [`<input>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input "HTML <input> 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据。") | 代表允许用户编辑数据的*数据区* （文本框、单选框、复选框等）。 |
| [`<button>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button "HTML <button>元素 表示一个可点击的按钮。") | 代表*按钮* 。 |
| [`<select>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select "HTML select (<select>) 元素是一种表单控件，可创建选项菜单。菜单内的选项为<option> , 可以由 <optgroup> 元素分组。选项可以被用户预先选择。") | 代表*下拉框* 。 |
| [`<datalist>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist "HTML Datalist 元素 (<datalist>) 包含了一组<option>元素,这些元素表示其它表单控件可选值.")  | 代表提供给其他控件的*一组预定义选项* 。 |
| [`<optgroup>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/optgroup "在一个web表单中, HTML元素 <optgroup> 会创建包含在一个 <select> 元素中的一组选项") | 代表一个*选项分组* 。 |
| [`<option>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option "在web表单中,  HTML元素 <option>  用于定义在<select>,  <optgroup> 或<datalist> 元素中包含的项。<option> 可以在弹出窗口和 html 文档中的其他项目列表中表示菜单项。") | 代表一个 `<select>` 元素或 `<datalist>` 元素中的一个*选项* |
| [`<textarea>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea "HTML <textarea> 元素表示一个多行纯文本编辑控件。") | 代表*多行文本框* 。 |
| [`<keygen>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/keygen "HTML <keygen> 元素是为了方便生成密钥材料和提交作为 HTML form 的一部分的公钥.这种机制被用于设计基于 Web 的证书管理系统。按照预想，<keygen> 元素将用于 HTML 表单与其他的所需信息一起构造一个证书请求，该处理的结果将是一个带有签名的证书。")   | 代表一个*密钥对生成器* 控件。 |
| [`<output>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/output "HTML <output> 标签表示计算或用户操作的结果。")  | 代表*计算值* 。 |
| [`<progress>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/progress "HTML中的progress (<progress>) 元素用来显示一项任务的完成进度.虽然规范中没有规定该元素具体如何显示,浏览器开发商可以自己决定,但通常情况下,该元素都显示为一个进度条形式.")  | 代表*进度条* 。 |
| [`<meter>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter "HTML <meter>元素用来显示已知范围的标量值或者分数值。")  | 代表*滑动条* 。 |

***

## 交互元素

| Element | Description |
| --- | --- |
| [`<details>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/details "HTML <details> 元素被用作发现小部件，用户可以从其中检索附加信息。")  | 代表一个用户可以(点击)获取额外信息或控件的*小部件* 。 |
| [`<summary>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/summary "HTML <summary> 元素 用作 一个<details>元素的一个内容的摘要，标题或图例。")  | 代表 `<details>` 元素的*综述* 或*标题* 。 |
| [`<menuitem>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/menuitem "此页面仍未被本地化, 期待您的翻译!") | 代表一个用户可以点击的菜单项。 |
| [`<menu>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/menu "HTML <menu> 元素 呈现了一组用户可执行或激活的命令。这既包含了可能出现在屏幕顶端的列表菜单，也包含了那些隐藏在按钮之下、当点击按钮后显示出来的文本菜单。")   | 代表菜单。 |

***

# 什么是空元素
<br>
不包含任何内容的HTML元素被称为空元素。在 HTML 中，通常在一个空元素上使用一个闭标签是无效的。例如， ``<input type="text"></input>`` 的闭标签是无效的 HTML。

在 HTML 中有以下这些空元素：

*   [`<area>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/area "HTML <area> 元素 在图片上定义一个热点区域")
*   [`<base>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/base "HTML <base> 元素 指定用于一个文档中包含的所有相对URL的基本URL。一份中只能有一个<base>元素。")
*   [`<br>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/br "HTML 元素 换行 <br> 在文本中产生一个换行（回车键）。这对于写诗或写一个地址来说显得很有用。它可以将行明显地分开。")
*   [`<col>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/col "HTML <col> 元素 定义表格中的列，并用于定义所有公共单元格上的公共语义。它通常位于<colgroup>元素内。")
*   [`<colgroup>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/colgroup "HTML 中的 表格列组（Column Group <colgroup>） 标签用来定义表中的一组列表。") when the [`span`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/colgroup#attr-span) is present
*   [`<command>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/command "command元素用来表示一个用户可以调用的命令.")
*   [`<embed>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/embed "HTML <embed> 元素 用于表示一个外部应用或交互式内容的集合点，换句话说，就是一个插件。")
*   [`<hr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/hr "HTML <hr> 元素表示段落级元素之间的主题转换（例如，一个故事中的场景的改变，或一个章节的主题的改变）。在HTML的早期版本中，它是一个水平线。现在它仍能在可视化浏览器中表现为水平线，但目前被定义为语义上的，而不是表现层面上。")
*   [`<img>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img "HTML Image 元素（ <img> ）代表文档中的一个图像。")
*   [`<input>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input "HTML <input> 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据。")
*   [`<keygen>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/keygen "HTML <keygen> 元素是为了方便生成密钥材料和提交作为 HTML form 的一部分的公钥.这种机制被用于设计基于 Web 的证书管理系统。按照预想，<keygen> 元素将用于 HTML 表单与其他的所需信息一起构造一个证书请求，该处理的结果将是一个带有签名的证书。")
*   [`<link>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link "HTML 中<link>元素指定了外部资源与当前文档的关系. 这个元素的使用方法包括为导航定义关系框架.这个元素经常用来链接css文件。")
*   [`<meta>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta "HTML <meta> 元素表示那些不能由其它HTML元相关元素 (<base>, <link>, <script>, <style> 或 <title>) 之一表示的任何元数据信息.")
*   [`<param>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/param "HTML <param> 元素(或 HTML Parameter 元素) 定义了 <object>的参数")
*   [`<source>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source "The HTML <source> element specifies multiple media resources for either the <picture>, the <audio> or the <video> element. It is an empty element. It is commonly used to serve the same media content in multiple formats supported by different browsers.")
*   [`<track>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/track "HTML <track> 元素 被当作媒体元素—<audio> 和 <video>的子元素来使用。它允许指定计时字幕（或者基于事件的数据），例如自动处理字幕。")
*   [`<wbr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/wbr "HTML <wbr> 元素  — 一个文本中的位置，其中浏览器可以选择来换行，虽然它的换行规则可能不会在这里换行。")

***

# 什么是可替换元素
<br>
CSS 里，**可替换元素（replaced element）**的展现不是由CSS来控制的。这些元素是一类 外观渲染独立于CSS的 外部对象。 典型的可替换元素有 [`<img>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img "HTML Image 元素（ <img> ）代表文档中的一个图像。")、 [`<object>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/object "HTML <object> 元素（或者称作 HTML 嵌入对象元素）表示引入一个外部资源，这个资源可能是一张图片，一个嵌入的浏览上下文，亦或是一个插件所使用的资源。")、 [`<video>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video "HTML <video> 元素 用于在HTML或者XHTML文档中嵌入视频内容。") 和 表单元素，如[`<textarea>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea "HTML <textarea> 元素表示一个多行纯文本编辑控件。")、 [`<input>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input "HTML <input> 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据。") 。 某些元素只在一些特殊情况下表现为可替换元素，例如 [`<audio>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio "HTML <audio> 元素用于在文档中表示音频内容。 <audio> 元素可以包含多个音频资源， 这些音频资源可以使用 src 属性或者<source> 元素来进行描述； 浏览器将会选择最合适的一个来使用。对于不支持<audio>元素的浏览器，<audio>元素也可以作为浏览器不识别的内容加入到文档中。") 和 [`<canvas>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/canvas "<canvas>元素可被用来通过脚本（通常是JavaScript）绘制图形。比如,它可以被用来绘制图形,制作图片集合,甚至用来实现动画效果。你可以(也应该)在元素标签内写入可提供替代的的代码内容，这些内容将会在在旧的、不支持<canvas>元素的浏览器或是禁用了JavaScript的浏览器内渲染并展现。") 。 通过 CSS [`content`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/content "CSS的 content CSS 属性用于在元素的  ::before 和 ::after 伪元素中插入内容。使用content 属性插入的内容都是匿名的可替换元素。") 属性来插入的对象 被称作 **匿名可替换元素（**anonymous replaced elements**）**。
