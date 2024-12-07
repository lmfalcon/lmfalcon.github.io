---
title: golang1
date: 2019-08-29 14:05:33
tags: golangconfig，golanginstall
---

# golang

## 安装

- 不建议用sudo apt install 安装，因为版本太老了
- [官网](https://golang.google.cn/)
- 建议安装地址 /usr/local/	解压会自动建一个go文件夹
- tar -C /usr/local -xzf go1.12.9.linux-amd64.tar.gz


## 配置

- 之前安装了gcc 所以配置时默认的是这个老版本go
- 用go version查看当前版本
- 用go env 查看go的运行环境
- 用which go 查看go的可执行文件位置
- 用whereis go 查看用多少go文件地址
- 配置环境在.bashrc中
```
# go path
export GOPATH=$HOME/go
export GOROOT=/usr/local/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```
- 网上说GOROOT和GOPATH地址不能一样
