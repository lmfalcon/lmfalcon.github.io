---
title: vimbasic3
date: 2019-07-28 08:36:20
tags: vim
---

# vim基本用法3

## 文本操作

- [number]<command>[text object]
	- number 次数
	- command 命令，d(elete),c(hange),y(ank)
	- text object 文本对象，单词w，句子s,段落p
- vaw 改变括号，引号等被包裹起来的所有词包括空格
- viw 改变包裹起来的所有词不包括结尾的空格

## 复制粘贴

- 设置了autoindent，可能导致代码缩进错乱
	- 解决方式用:set paste和:set nopaste
	- 可以用插件直接解决
- 使用xp可以快速调换两个字符

### vim使用无名寄存器用于保存复制内容

- "指定寄存器名，不指定为默认的无名寄存器
- "ayiw 复制一个单词到寄存器a中，"bdd 删除当前行到b寄存器中
- ""表示无名寄存器

### 各类寄存器

- "0 复制专用寄存器
- "+ 复制到系统剪贴板
- :echo has('clipboard')查看是否有这个，1表示有，0表示无
- 貌似直接<c-sh-v>可以复制系统剪贴版的内容到vim中即使是python文件也没有问题
- 

## 宏

- q 用于录制和退出

### 示例

- 将下面的操作全部变成列表
- 用qa命令开始录制并将录制结果保存在a寄存器中
- 成功后出现recording @a 
- 按i进入插入模式
- 输入-加空格
- 此时结束录制，底端的recording @a也会消失
- 按V行选择
- 按G直接选择至尾行
- 按:发现左下角出现'<,'>
- 输入normal @a
- 完成列表
