---
title: git2
date: 2019-08-19 10:01:07
tags: git
---

# 命令介绍

## git status

- 用于查看仓库中的文件状态
	- 在哪个分支
	- 是否有提交
	- 是否有新的文件，是否有追踪过这个文件，是否更改过
- 查看工作区和缓存区内容

## git add 文件名

- 用于追踪文件
- 用于将工作区的内容提交到暂存区


## git commit 文件名

- 用于提交文件
- -a 用于modified文件的提交
- -m ""   引号内写下修改内容，避免打开vim编辑器添加
- 将暂存区内容传到本地库

## git log

- 查看历史版本
-  --pretty=oneline	以简洁的方式显示
-  --oneline	以最简单方式显示只显示head指针的过去版本，而不显示head指向的新版本
- 多屏显示类似linux中的less显示

## git relog

- 显示head指针需要移动多少步才能达到想要的版本

## git reset --hard 哈希索引值

- 选择你想要到的版本

## git reset --hard HEAD^

- 回退到之前版本，取决于^的数，数量表示回退补数（不建议多步）

## git reset --hard HEAD~步数

- 显示你要后退的版本步数

## git help reset

- reset 的帮助


## git reset

- --soft	仅仅在本地库移动HEAD指针
- --mixed	
	- 在本地库移动HEAD指针
	- 重置暂存区
- --hard	
	- 在本地库移动HEAD指针
	- 重置暂存区
	- 重置工作区
- 找回文件的一种方式，回退到之前的版本，把之前版本的文件恢复，不过前提必须在文件存在时的状态提交到了本地库


## git diff 文件名

- 将工作区文件与暂存区文件进行比较
- 红色表示删除过
- 前面有加号表示添加的内容


## git diff 【本地库中的历史版本】【文件名】

- 将工作区中的文件和本地库历史记录进行比较
- 不带文件名比较多个文件


	
---


# 本地的仓库分类

## 本地库

- 历史版本
	- 通过head指针指示当前处于的版本

## 暂存区

- 临时存储


## 工作区

- 写代码


---

# git的分支

- 从多个分支对一个项目进行开发


## master

- 主要分支


## feature_***

- 刚开始内容和master一样
- 之后的内容是独立的分支，在合并之前不会对master和其他分支有影响
- 作为一个独立的功能进行开发


## hot_fix分支

- 用于修复bug


## git branch -v

- 查看现有分支


## git branch 分支名

- 新建分支
- 一般以feature_***形式命名
- 修复bug分支一般以hot_fix命名 


## git checkout 分支名

- 用于切换分支