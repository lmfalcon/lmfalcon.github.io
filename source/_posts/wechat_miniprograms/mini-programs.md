---
title: mini_programs
date: 2020-11-30 22:12:57
tags: wechat,miniprogram
---


# 微信小程序入门

# 开发者工具熟悉，APPID

# 官方文档

## 微信小程序的框架

- MINA 微信小程序的原生框架
- 微信小程序提供了自己的视图层语言WXML（标签）和WXSS（样式），以及JavaScript(写逻辑），


# 小程序的配置文件

## 全局配置文件app.json

1. pages 字段————可以描述当前小程序所有的页面路径，这是为了微信客户端知道当前你的小程序页面定义在哪个目录
2. windows 字段————定义小程序所有页面的顶部背景颜色，文字颜色等定义
写了一部分感觉官方文档写的好仔细应该看文档就可以学会很多吧。
接下来专心看视频记录关键就好

- navigationbar 这部分指的是导航栏


3.tabbar底部导航

- 和pages、windows一样的文件层级输入tabbar回车会自动补全所需默认代码，但是如果加上“”就不会自动补全了。
- pagepath表示点击后的连接路径
- text 文字
- iconpath 表示未选中图标路径
- selecticonpath 表示选中图标路径
- list中包含以上这些，一个list代表一个图标一个路径

## 页面配置

具体网页中的json文件用于配置具体文件的，可以配置小程序页面相关内容，也可以单独配置页面的上拉下拉刷新，

## sitemap 配置

项目中的sitemap.json文件。用于设置微信索引你的小程序。


# 模板语法

WXML（weixin Makeup Language)框架设计的标签语言

## 数据绑定


