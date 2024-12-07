---
title: git1
date: 2019-08-07 20:11:25
tags: git
---

# git

## git的作用

- 版本控制
- 多人开发协作方便
	- 协同修改
	- 数据备份
	- 版本管理
	- 权限控制
	- 历史记录
	- 分支管理

## 版本控制

- 集中式的版本控制工具
	- SVN  存在服务器上
	- 可能单点故障
- 分布式的版本控制
	- git 每台电脑都有一个版本库
	- 解决单点故障问题


## git优势

- 本地运行不需要联网
- 完整性保证
- 尽可能添加数据而不是删除ｏｒ修改数据
- 分支操作非常快
- linux命令全面兼容

## git分区

### 工作区

- 写代码

### 暂存区

- 临时储存

### 本地库

- 历史版本

## git和代码托管中心

### 代码托管中心

- 为了维护远程库 
- 局域网
	- GitLab服务器
- 外网
	- GitHub
	- 码云

### 本地库和远程库

- 本地库-远程库 push 
- 远程库-本地库 clone
- 远程库1-远程库2 fork 相当于复制远程库1中的内容到远程库2中
- 远程库2-远程库1 pullrequest-审核-merge 将远程库2中更新的内容经过远程库1拥有者审核后合并进来

## git命令行操作

### 本地库初始化

- 命令：git init 
- 效果：创建了一个.git的隐藏目录
- 注意：.git 目录中存放的是本地库相关的目录和文件，不能删除和乱改

### 设置签名

- 形式
	- 用户名 tom
	- Email goodmorning@adfa.com
- 区分不同版本开发人员的身份
- 辨析： 这里设置的签名和登录代码托管中心的账号密码无关
- 命令： 
	- 项目级别/仓库级别：仅在当前本地库有效		
		- git config user.name tom
		- git config user.email adsfa@asdfa.com
		- 存储位置 仓库地址/.git/config文件中user节点处
	- 系统用户级别：在本系统的系统用户范围有效		
		- git config --global user.name tom_administrator
		- git config --global user.email tom_administrator@afasa.com
		- 储存位置 ~/.gitconfig中user节点中
	- 优先级： 
		- 就近原则：项目级别优先于系统用户级别，二者都有项目级别签名优先采用
		- 不允许二者都没有
- 项目级别用户存放位置 cat .git/config
- 系统用户级别用户存放位置	
	- cd ~
	- pwd
	- ls -la|less	显示隐藏文件并分页显示
	- 查看 .gitconfig	



