---
title: git的使用傻瓜版
date: 2017-11-05 09:20:07
tags: [git]
---

本来之前用的github都是自己一个人用而已，来来去去都是`git pull` `git push`觉得也没什么，但去了新公司之后，代码版本管理是用的git，多人协作一起管理代码点时候，才发现我对git是一无所知。所以趁现在使用git还没有得心应手的时候，写一下平时开发的时候经常需要用到的git命令，对应git命令点使用情形和对应的语法说明。

当然，彻底掌握git才是最彻底的解决办法。[廖雪峰的Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)是网上能找到最好点git教程了。

<!-- more -->

还发现了一个比较[好玩的游戏](https://learngitbranching.js.org)

## git checkout -- (filename)

	git checkout -- index.hmtl
	
作用是清空某个文件的所有修改，这个命令会在当前分支上最新的提交拿到文件内容并覆盖掉当前文件，不管是删掉还是怎样怎样修改掉，都能“一键还原”。

注意的是，此命令只会清空工作区的修改，暂存区（commit）的内容还在。清空暂存区的话，用“git reset  HEAD file”

## 版本回退

	git reset HEAD~3 --hard
	
	git reset --hard 3628164
	
版本回退用的是`git reset`。又两种方式。`回退到前几个记录`和`回退到指定记录`。

回退到前几个记录是在HEAD后面跟数字几，如果回退版本可数版本之前，可以用`^`代替。举个例子

回退到3个版本以前可以用

	git reset HEAD^^^ --hard
	
或

	git reset HEAD~3 --hard
	
# git rebase

# 拉取远程分支

此方法或拉取远端分支到本地，并且切换到该分支。新分支与远端分支建立起联系

	git checkout -b 本地分支名x origin/远程分支名x

# 关联远程分支

	git remote add origin git@github.com:HelloWorld20/bg-location.git
	
# 从缓存区中去除

只是去除的话，

	git reset HEAD (文件名)
	
还可以让git不跟踪某个文件

	git rm (文件名) --cached
	
或者直接删除文件

	git rm (文件名)
	
# 强大的rebase

## rebase -i

`i`是 interactive，是交互式的意思，可以细粒度的修改历史commit

## rebase --onto

# HEAD的概念