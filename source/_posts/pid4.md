---
title: Git学习日记
top: 0
copyright: true
date: 2024-11-30 8:00:00
updated: 2024-11-30 8:00:00
permalink:
password:
comments:
tags: [Git]
categories: 
    - [学习]
keywords:
description:
---
摘要：本文主要记录了Git学习的笔记。主要学习了git基础知识，如：基本命令学习、版本回退等。参考[链接](https://liaoxuefeng.com/books/git/)。
<!--more-->
## 创建版本库
[传送门](https://liaoxuefeng.com/books/git/create-repo/index.html)
> 版本库又名仓库（Repository），你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

```
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```
`.git`目录默认是隐藏的，可以通过`ls -ah`命令看见

### 关于文件改动
> 首先这里再明确一下，所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外。版本控制系统可以告诉你每次的改动，比如在第5行加了一个单词“Linux”，在第8行删了一个单词“Windows”。而图片、视频这些二进制文件，虽然也能由版本控制系统管理，但没法跟踪文件的变化，只能把二进制文件每次改动串起来，也就是只知道图片从100KB改成了120KB，但到底改了啥，版本控制系统不知道，也没法知道。

版本控制系统只能跟踪文本文件的改动，二进制文件无法追踪。

### 将文件添加
1. 将文件添加至仓库（添加到暂存区）
```
$ git add <文件>
$ git add . #将目录下所有文件都添加
```
> 执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

没有提示消息即是提交成功。

> 为什么Git添加文件需要`add`，`commit`一共两步呢？因为`commit`可以一次提交很多文件，所以你可以多次`add`不同的文件。

`add`可以将多个文件放在一块写添加暂存。


2. 提交到仓库
```
$ git commit -m "<提交改动说明>"
```
> 简单解释一下`git commit`命令，`-m`后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

建议添加`-m`提交消息。

### 摘要
初始化一个Git仓库，使用`git init`命令。

添加文件到`Git`仓库，分两步：
1. 使用命令`git add <file>`，注意，可反复多次使用，添加多个文件；
2. 使用命令`git commit -m <message>`，完成。

【以上记录自11月26日】