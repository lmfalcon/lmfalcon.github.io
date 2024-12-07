---
title: git3
date: 2019-08-24 21:31:59
tags: git
---

# 分支操作

## 合并分支

1. 切换到要修改的分支（被合并，增加新内容）上	git checkout[老内容分支]
2. 执行merge命令	git merge[新内容分支]

### 产生冲突

- 打开冲突文件，head到等号是当前分支内容，等号到新内容分支名为冲突修改内容
- 解决步骤
	- 删除不想要的内容
	- git add 文件名
	- git commit -m "修改内容" 注意这里现在不能加文件名否则会报错
	


# 哈希

- 一种加密算法
	- 将明文转换为密文

## 特点

- 不管输入数据的数据量有多大，输入同一个哈希算法，得到的加密结果长度固定
- 哈希算法确定，输入数据确定，输出数据也是确定的
- 哈希算法确定，输入数据有变化，输出数据一定有变化而且可能有很大的变化
- 哈希算法不可逆

## 分类

- MD5
- SHA1（字母不区分大小写，应该是代表十六进制数）
- CRC32


## 与git关联

- Git底层采取SHA-1 算法
- 哈希算法可以用来校验文件是否修改


# git 与 svn 区别

- svn为集中式管理，每次保留修改部分，不存在修改部分
- git 把数据看做是小型文件系统的快照，每次提交更新都会对全部文件制作一个快照保存快照索引，如果文件没有修改git不再重新储存，只保留指针指向之前文件
	- 提交对象及其父对象形成链表
- git的快照
	- 自身哈希
	- commit
	- tree
	- parent
	- author
	- commiter


# git 如何管理分支

- 类似链表结构
- 首个版本为root
- 开始HEAD指针指向master指针
- 若有新的分支则新建一个新的指针
- 切换分支只是改变HEAD指针位置


# github

- 创建账号
- 创建仓库
- 仓库网址保存
	- git remote add origin(保存的仓库网址) 网址（url）将仓库网址起别名
	- git remote -v 查看当前所有的网址别名
- 将新成员加入项目，点击setting，选择Collaborators，填写新成员github账号发送邀请，新成员接收到邀请后点击接受，新成员就可push内容到远端库了

# 推送

- git push 网址 本地库提交分支
	- 第一次可能遇到https问题。需要删掉https试一次，在加上https试一次，然后就可以用啦
	- 目的是将本地库推送到远程库
- 新成员不能将本地库内容推送到远程库

# 克隆

- git clone 网址
	- 会完整的把远程库克隆到当前文件夹下的仓库名文件夹
	- 创建远程库的地址别名
	- 初始化本地库
- 新成员可以克隆内容到本地库，可以在本地库进行修改，但是不能上传到远程库


# pull拉取

- git pull 相当于 git fetch + git merge 的合并
- git fetch 【远程库地址别名】【远程分支名】
	- 不改变本地文件，只是下载到本地
	- 下载的文件到了git checkout origin/master 分支上
	- 用于查看改变而不着急更改
- 以上都是读操作不需要确定身份
- 因为拉取有merge过程可能出现冲突问题，所以可以拆开来用


# pull文件冲突

- 当git push 文件时远程库有了新的版本，这时的push操作是不会生效的。
- 只能git pull 文件，当文件冲突时，会出现XXX|merge分支，这个分支操作和之前的分支冲突解决办法相同，选择删除冲突的内容。同样的git add 之后不带文件名的git commit


# 跨团队协作

- 以其他团队成员身份希望参与他人的工程开发，可以用fork的方式将项目复制到自己的目录下，
- 可以clone到自己的本地
- 也可以push到自己的远程库
- 将自己的改好的项目传回他人的团队
	- github上pull request，进入后点击create pull request
	- 类似发封邮件给项目创建人
	- 项目创建人查看pull request，可以回复comment，可以commit看对方提交了什么，可以看files changed 具体做的文件修改。对代码进行审核
	- 如果没问题，merge pull request合并代码，填写confirm merge填写本次操作的日志信息
	

# SSH登录

- 命令行下输入ssh-keygen -t rsa -C 邮箱地址
- 生成SSH的目录，进入到目录中，可以看到两个文件 
	- id_rsa
	- id_rsa.pub 
		1. 内容复制，
		2. 进入github
		3. 进入personal settings 
		4. 进入SSH and GPG keys
		5. title随意，keys粘贴复制内容
- 通过 git remote add 地址别名 SSH地址
- git remote -v 查看SSH编码
- git push SSH的别名 master 推送至远程库（可以不填写账号密码）


# git的图形界面

- eclipse 内置了git插件


# eclipse 操作

## 为项目初始化git

- 工程上点右键选Team
- 选share_project
- 选git
- use or create repository in parent folder of project 勾选
- 选中项目
- 之后点击create repository
- finish

## 为项目提交

- 工程上右键选Team
- 选commit
- 显示三个部分
	- unstaged changes
	- staged changes
	- commit message
- eclipse中会有一些特定文件是eclipse中管理本地库的隐藏文件，这些文件不需要通过git上传，因为不同版本的eclipse用的特定文件也不同
	- .classpath
	- .project
	- .settings
	- target

## git的忽略文件

- url github.com/github/gitignore
- 例如java 参照网址中机制，
	1. 在用户家目录中找到.gitconfig文件放在一个目录下方便一起修改
	2. 新建复制网站中的代码，命名按照github上的仓库名
	3. 除了这些eclipse中还要忽略
		- .classpath
		- .project
		- .settings
		- target
	4. 在.gitconfig中加入下面代码
```
[core]
	excludesfile = ~/java.gitconfig
```

## eclipse 项目提交

- 工程右键选Team
- 选择add to index
- 之后在选择commit提交


## eclipse推送到远程库

- Team 
- remote
- push
- 填写url


## 远程库工程放到本地

###  高版本操作

- import 导入工程
- git/projects from git
- clone url
- Destination 选择eclipse工作区目录
- import as general project

### 低版本操作

- 前面的都一样，不能导入到当前工作区目录，只能导到工作区以外的目录中
- Destination 非eclipse工作区目录
- 之后的步骤相同


## eclipse 解决冲突

- 各自提交到本地库没问题
- 如果推送到同一远程库，后推送会出现冲突
- 同样的先pull文件之后处理冲突，也可以用merge tool查看多文件区别
- 处理好后正常推送远程库即可

## eclipse创建or切换分支

- Team
- switch to 
- New branch or other



# git工作流

## 集中式工作流

- 类SVN无分支

## gitflow工作流

- 新功能开发在master下的develop分支上进行
- develop下还有feature_XX等分支负责具体功能开发
- bug在master下hotfix下进行修复并且修复后尽快合并会master分支和develop分支
- 上线前进行最后测试需要建立一个release分支测试。
- 将develop分支合并至release上且有bug直接修复
- 上线时合并到master分支上和develop分支上

## froking工作流

- 常用于项目外人员开发


# gitlab 服务操作

- 初始化gitlab
	- gitlab-ctl reconfigure
- 启动gitlab
	- gitlab-ctl start
- 停止gitlab
	- gitlab-ctl stop

# 浏览器访问

- 可能需要停掉防火墙
	- service firewall stop 
- gitlab设置密码
- 之后类似github操作 
