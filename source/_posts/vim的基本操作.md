---
title: vim的基本操作
date: 2018-08-19 14:37:41
tags: vim
---
>本文环境以windows为主，在学习使用vim之前，请安装git bash。大家也可以参阅官方文档进行学习，在命令行（bash）中直接输入：`vimtutor`

bash中打开代码文件最简单直接的方式就是使用vim进行操作了，命令如：
```
vim a.md
```
- vim中移动光标分别为：``h j k l键``
- vim中退出：
  - 不保存退出：``:q!``回车，为确保处于正常模式，请在输入命令以前多按几次Esc键
  - 保存退出：``:wq``，注意同上
- 修改删除
  - 删除：`x`按键为删除字符，在正常模式下使用
  - 删除单词：`dw`
  - 删除整行：`dd`
  - 删除括号内容：``di(``即``delete in ()``，可类推其他内容
  - 删除括号及括号内容：``da(``即``delete at ()``，可类推
  - 插入：`i`按键为插入，在光标前插入字符，在正常状态下按`i`可进入编辑模式；`I`为行首插入
  - 添加：`a`按键为添加，在光标后插入字符，在正常状态下按`a`可进入编辑模式；`A`为行尾插入
  - 撤销：`u`按键为重做(un-do)，`ctrl+r`按键为再撤销(re-do)
- 翻页
  - 向上翻页：``ctrl+u``
  - 向下翻页：``ctrl+d``
- 在动作前输入数字可使其重复对应数字次数