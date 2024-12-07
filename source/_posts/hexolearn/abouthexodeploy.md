---
title: abouthexodeploy
date: 2019-07-22 16:06:08
tags: hexo
---

## 更换主题后修改作者

出现问题描述：localhost:4000 端口正常显示但是部署到github上public文件夹内容未改变。

## hexo deploy 标准流程
1. 进入blog目录
2. sudo su root权限
3. 修改blog的内容
4. hexo clean(还不了解具体作用只是看视频中这样做）
5. hexo g（生成静态文件？视频中说hexo生成的是静态页面，具体意思未知，有待学习）
6. ctrl+D退出root权限
7. sudo hexo d 进行部署，讲博客部署到github上的lmfalcon.github.io（具体网址不是这个，而是新建仓库时的那个链接）上。

## 问题解决过程
root权限可以少打sudo命令本来很方便，但是建立ssh时我用的是lmfalcon这个用户导致git部署到github上时需要用lmfalcon这个用户。所以需要标准流程中的第6步退出过程，否者部署显示成功但是实际未部署任何文件。
