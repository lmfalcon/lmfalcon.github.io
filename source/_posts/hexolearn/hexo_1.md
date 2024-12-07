---
title: hexo_1
date: 2019-07-17 01:14:53
tags: hexo
---

## 第一章

内容
注意以上要在root权限下进行（sudo su ,ctrl+D退出root）
hexo v			版本
hexo init		初始化模板
hexo new 文章名	新建文章，一般存储在blog/source/_post目录下
hexo clean		清理
hexo g			生成新文章
hexo s			生成blog在本地localhost:4000

---

## 第二章

内容
这次因为修改了md文件导致hexo g 时无法更新，问题出在：
1. mv 重命名注意不要遗漏扩展名，否则改变文件格式
2. 修改文章标题只用修改title，与文件名无关

---


## hexo的迁移

参考了很多网络上的经验：
1. 首先还是先复制旧电脑中的内容放到新电脑中。 复制的内容可以不含node_modules文件夹，因为新电脑中也会装node而且是新的版本。
2. git需要安装，之后设置SSH.这些网上应该可以轻松搜到。
3. 然后是nodejS和其包管理工具npm,npm切换到淘宝源，保证国内运行的速度。具体的切换方式可以参考阿里云提供的教程。
4. 我们的hexo之前用的hexo可能版本比较老nexT主题可能也比较老，所以这两个应该都需要做更新，但是里面的设置是老，更新了就会随着改动，这里不妨按照next主题的推荐设置方法用，其实可以备份一份文件之后参照的更改恢复，我这次是一个个更改恢复的。
'''
···
# Installed through npm 这里复制的是hexo的配置文件
cp node_modules/hexo-theme-next/_config.yml _config.next.yml
# Installed through Git 这里复制的是next的配置文件
cp themes/next/_config.yml _config.next.yml
···
'''
这样设置就不会在git更新过程中出现冲突
关于hexo的更新我实验有效的方法是
'''
这个命令用于查询npm里过时的应用不是最新版本的应用
npm outdated
 47  npm config list
   48  npm install npm@latest -g
   49  hexo version
   50  npm i hexo-cli -g
   52  hexo version
   53  npm install -g npm-check
   54  npm-check
   55  npm install -g npm-upgrade
   56  npm-upgrade
   57  npm update -g
   58  npm update --save

下载这个主题
git clone https://github.com/theme-next/hexo-theme-next themes/next

'''
顺带一提：反正每次转换到新的电脑也会在网上找一下新的教程大概率不会在blog中搜索。只是给一个参考。


## 参考文献

bing 百度
