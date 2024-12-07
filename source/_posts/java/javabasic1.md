---
title: javabasic1
date: 2019-07-26 00:05:15
tags: javabasic
---

# eclipse常用操作

## 快捷键

- 使用alt+/可以快速补全
- 使用ctrl + alt + 上下箭头可以批量复制代码
- 使用ctrl + shift + 上下箭头可以快速跳出大括号层代码并停留在当层标题处or大括号处

## 自动补全

- 写下main按下快速补全可以快速写main函数语句
- 写下sysout快速补全可以写输出语句

---

# Java简介

## 版本

- JavaEE 企业端
- JavaSE 标准版本
- JavaME 小型设备特殊版本

## 简称

- jdk 集成开发环境包括jre
- jre 运行环境包括jvm
- jvm Java虚拟机

## 基本编程易错及基本库介绍

- python用多了容易漏分号
- a *= b + c 等于 a*(b+C)赋值给a
- java注释和C++一样是//单行/**/行内/****/文档注释Python是##
- 类名所有单词首字母大写，变量方法则用驼峰原则
- java.awt.*库可用于图形位置控制
- java.swing.JFrame库可以生成图形界面
- java.util.Scanner用于键盘监控
- Math.random()这个方法可以直接使用生成随机数范围[0,1)
- 浮点数运算需要精确可以使用BigDecimal方法，尽量用字符串进行初始化相应库为java.Math.BigDecimal
- switch语句jdk1.7后可使用字符串作为判断条件了
``` 
switch(判断条件){
	case 条件1:
		语句1;
		break;
	case 条件2:
		...
	default:
		语句;
		break;
	}

```
