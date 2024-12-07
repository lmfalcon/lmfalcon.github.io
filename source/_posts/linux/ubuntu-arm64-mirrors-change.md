---
title: ubuntu_arm64_mirrors_change
date: 2020-11-20 13:27:02
tags: ubuntu,mirror,arm64
---

# 在树莓派上安装Ubuntu系统

1.找到适合的系统，我用的是树莓派4B8G内存版本，所以使用的树莓派系统是arm64
2.建议直接在镜像源网站上找到对应的系统下载，官网下载太慢了
3.SD卡用老板给的格式化软件格式化，再用老板给的烧录软件烧录镜像文件进SD卡
4.发现可以开机了
5.装好之后要改变系统源和软件源

# 系统源和软件源设置

首先找到一个镜像网站一般是mirrors.XXXX.xxx
其次命令行进入/etc/apt/找到sources.list文件。建议用sudo su 进入管理员模式编辑，vi 打开文件参照底下原有配置更改，一般是deb https://mirrors.XXX.xxx/ubuntu-ports/ groovy（我的是这个不同的系统不同，需要参照原文件底下内容进行更改。arm64 系统的源在ubuntu-ports文件目录下。如果用ubuntu目录会报错未发现arm64。按照网上的方案复制进来即可，对应进行修改。
最后修改完成sudo apt-get update 和 sudo apt-get upgrade 升级系统更新软件源系统源。

# 豆制品、茄子、莴笋、鱼、蛋类感觉都是我爱吃的，在吃上差别有些大。(>/\\\<)!!以后点菜要注意了。


