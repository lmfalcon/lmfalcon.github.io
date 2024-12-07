---
title: tmux_zsh_ranger
date: 2019-08-29 12:25:48
tags: tmux, zsh, ranger
---

# tmux

## 简介

- terminal multiplexer
	
## 安装
```
mkdir ~/shellsoftware
cd ~/shellsoftware
git clone https://github.com/tmux/tmux.git
cd tmux
sh autogen.sh
./configure && make
```

## 分类

|server|服务器。输入tmux命令就开启一个服务器|
|-:-|-:-|
|session|会话。一个服务器可以包含多个会话|
|window|窗口。一个会话可以包含多个窗口|
|panel|面板。一个窗口可以包含多个面板|

## 基本操作(<C-b>+指令）

|开启会话|tmux new -s <session-name>|
|-:-|-:-|
|断开会话|+d|
|显示已有会话|tmux ls|
|连接指定会话|tmux a -t 指定会话名|
|关闭会话|tmux kill-session -t 指定会话名|
|关闭所有会话|tmux kill-server|
- Ctrl+b 激活控制台；此时以下按键生效
- 系统操作
	- ? 列出所有快捷键；按q返回
	- d 脱离当前会话；这样可以暂时返回Shell界面，输入tmux attach能够重新进入之前的会话
	- D 选择要脱离的会话；在同时开启了多个会话时使用
	- Ctrl+z 挂起当前会话
	- r 强制重绘未脱离的会话
	- s 选择并切换会话；在同时开启了多个会话时使用
	- : 进入命令行模式；此时可以输入支持的命令，例如kill-server可以关闭服务器
	- [ 进入复制模式；此时的操作与vi/emacs相同，按q/Esc退出
	- ~ 列出提示信息缓存；其中包含了之前tmux返回的各种提示信息
- 窗口操作 
	- c 创建新窗 & 关闭当前窗口
	- 数字键 切换至指定窗口
	- p 切换至上一窗口
	- n 切换至下一窗口
	- l 在前后两个窗口间互相切换
	- w 通过窗口列表切换窗口
	- , 重命名当前窗口；这样便于识别
	- . 修改当前窗口编号；相当于窗口重新排序
	- f 在所有窗口中查找指定文本
- 面板操作
	- ” 将当前面板平分为上下两块
	- % 将当前面板平分为左右两块
	- x 关闭当前面板
	- ! 将当前面板置于新窗口；即新建一个窗口，其中仅包含当前面板
	- Ctrl+方向键 以1个单元格为单位移动边缘以调整当前面板大小
	- Alt+方向键 以5个单元格为单位移动边缘以调整当前面板大小
	- Space 在预置的面板布局中循环切换；依次包括even-horizontal、even-vertical、main-horizontal、main-vertical、tiled
	- q 显示面板编号
	- o 在当前窗口中选择下一面板方向键移动光标以选择面板
	- { 向前置换当前面板
	- } 向后置换当前面板
	- Alt+o 逆时针旋转当前窗口的面板
	- Ctrl+o 顺时针旋转当前窗口的面板


# zsh

## 用处

- 一个比较流行的shell窗口

## 安装oh-my-zsh

```
sudo apt install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## 配置

- 由于配置文件大都需要改还是应该在刚刚装系统时配置zsh
- .zshrc在用户家目录下


# ranger

## 用处

- 一个可视化目录管理工具


## 用法

- 类似vim的操作
