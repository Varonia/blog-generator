---
title: line-height VS font-size
date: 2018-08-22 20:10:09
tags: css
---

# line-height概念

先来看看MDN里对于`line-height`的定义，来帮大家有个初步的概念认识。

`line-height`属性用于设置行所需要的空间，例如文本。对于块级元素，它指定元素中线框的最小高度。在未替换的内联元素中，它指定用于计算线框高度的高度。对于替代行内元素，如 button 或其他 input 元素，line-height 没有影响（原文未提到，对于部分替代元素，line-height 依然可以影响元素的样式布局）。

怎么样，看完MDN的解释以后明白了吗？还是依旧一头雾水？那么，来看看我对于它的理解吧。

# 我的解读

先说一个大家都熟知的现象，我们知道div的高度是由里面文档流元素的内容撑开的。如果一个空div里面打入了一个空格或是文字，则此div就会有一个高度。那么这个高度是什么呢？并不是很直观的`font-size`，而是`line-height`。

要证明这一点很简单，做一个对比即可。

```
.test1{font-size:20px; line-height:0; border:1px solid #cccccc; background:#eeeeee;}
.test2{font-size:20px; line-height:20px; border:1px solid #cccccc; background:#eeeeee;}
```

![image.png](http://upload-images.jianshu.io/upload_images/2244949-0250ec806e5cdfd8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

大家可能会发现上面示例中明明font-size和line-height设置了一样的大小，但似乎上下还有间隙，这就是line-height的另一个大坑了，一个小栗子献上。

```
.test{
  font-size:20px; 
  line-height:20px; 
  border:1px solid #cccccc; 
  background:#eeeeee;}
```

![image.png](http://upload-images.jianshu.io/upload_images/2244949-31a970bfe3c8f2c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

怎么样？爽不爽？字体从边框里面出来了哦。这里就需要搬运一下方方知乎文章里的讲解了。

![image.png](http://upload-images.jianshu.io/upload_images/2244949-3f1a0e1a3d80cdd3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 一个内联元素有两个高度：`content-area` 高度和 `virtual-area` （实际区域？）高度
（`virtual-area` 是我自己发明的单词，它表示对人类有效的高度，你在其他地方是看不到这个单词的）；

`content-area`的高度是由字体度量定义的（font-size的坑，感兴趣的自己爬）；

`vitual-area`的高度就是 `line-height`，这个高度用于计算 line-box 的高度；

`virtual-area`和`content-area`高度的差异叫做 `leading`。`leading` 的一半会被加到 `content-area` 顶部，另一半会被加到底部。因此 `content-area` 总是处于 `virtual-area` 的中间。
计算出来的 `line-height`（也就是 `virtual-area` 的高度）可以等于、大于或小于 `content-area`。如果 `virtual-area` 小于 `content-area`，那么 `leading` 就是负的，因此 line-box 看起来就比内容还矮了。
（其实就是说`line-height`高度是以中间线为基准上下均分，而`font-size`是根据其字体基线进行高度分配，当两者数值一致的时候因为分配原则不同自然出现上下边界不一致）

而在实际应用中对这些的解读就很简单直接了——`font-size`的大小不一定是它实际所占空间的大小，它自带`line-height`效果，如果你的`line-height`与`font-size`一致或者接近就会很倒霉...所以尽量在设计的时候留出一点富裕值就好了。

