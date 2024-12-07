---
title: linuxbasic3
date: 2019-07-26 17:33:38
tags: linux， ssh
---

# linux基本指令

## sudo su	切换到root

- 按ctrl + D 退出

## sudo 临时提升为root权限

- 只能提升当前指令权限

## su 用户名	切换不同用户

## passwd 默认修改当前用户密码

- 需要用root用户修改密码，普通用户有限制，root可将密码改短

## exit 用于退出当前用户，回到上一个登录用户

## who 查看当前用户

-	-q 查看当前登录人数
-	-u 查看最后一次操作时间

## 重启和关机

-	shutdown 
   -	now 立刻关机
   -	r 重启
   -	c 取消
   -	+20 20分钟后关机
   -	20:25 定时关机
-	reboot	重启无通知

## 软件安装,更新和卸载

### 安装

- make install 源代码安装包
   1. ./configure 建立makefile这个文件
   2. makeclean 清除掉上次编译过的目标文件
   3. make 依据上一步的操作进行编译，通过gcc生成可执行文件，放在当前文件目录下
   4. make install 完成最后步骤

- dpkg 安装deb包
	+ sudo dpkg -i 软件包名

- sudo apt install 软件名
   * apt-get 功能范围更小，推荐直接apt

### 更新 

- sudo apt update

### 卸载

- sudo apt remove 软件名

---

# SSH

-sudo apt install openssh-server

## 链接远程服务器

- ssh 远程服务器用户名@远程服务器IP地址
- IP查询	ifconfig

## 远程拷贝

### 上传

- scp 需要拷贝的文件的路径 用户名@IP地址：要拷贝到的路径

### 下载

- scp 用户名@IP地址：拷贝文件路径 要拷贝到的路径

### 拷贝目录

- scp -r


