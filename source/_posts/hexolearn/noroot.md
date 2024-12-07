---
title: noroot
date: 2019-09-04 12:53:08
tags: hexo
---

# hexo不用root用户登录

- hexoblog搭建是在root权限下进行的，之后的每一个操作也是用root用户进行感觉很麻烦，所以决定改变一下

# 解决方案

- 将hexo的目录改成用户作为拥有者
```	
which hexo	//查看hexo位置，一般是软连接，看真正的hexo位置
//将hexo文件夹全部改成用户的
sudo chown -R 用户的用户名 hexo-cli所在位置（一般是这个文件夹）
//再将blog所在目录全改了
//切换到博客目录
cd blog目录
sudo chown -R 用户的用户名 ../blog目录
//这样以后说明操作都不能用sudo！！！否则又会创建root用户文件导致需要再修改blog目录
```
- 切记不能在用sudo命令使用hexo，否者又会需要改blog目录下的所有者

