---
title: aboutthehexonew
date: 2019-09-03 02:01:26
tags: hexo
---

# 建立新的blog文件

- hexo new blogname	可以建立文件但是数据库会报错，但是仍会建立文件，之后hexo clean	hexo g hexo d or hexo s 仍需要sudo 命令来进入管理员模式。
- 不用sudo新建文件，文件的所有者会是用户自己，这样方便vim编辑文件和实施预览。所以我决定忽略报错问题。
- hexo下所有命令都要用sudo执行，暂时不知道怎么解决。但是解决中遇到过以下问题
	- 首先是which hexo的位置是/usr/local/bin/hexo 这个软连接，软连接改不改拥有者区别不大因为权限是777.
	- 找到软连接对应文件发现拥有者并不是root。对应的上级文件夹也不是root用户，不明白为什么hexo仍要用root执行。
	- 可能原因
		- nodejs安装时就是root执行的后面都是要用到root
		- hexo还有其他的文件要求必须用root执行命令（但是这个设置文件我没找到）
