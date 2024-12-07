---
title: linuxbasic1
date: 2019-07-23 19:14:41
tags: linux

---

# linux入门基本命令
- 终端命令格式 command [-option] [parameter]
- command --help 查看命令帮助
- man command  manualpage命令使用手册  
进入文件后搜索常用: 
- /搜索内容 类似window ctrl+F
换页常用: 
- f 前一页
- b 后一页
- q 退出

---

## ls 当前文件夹所有文件(类DOC dir 命令) 

-	-a 显示隐藏 
-	-l 显示详细信息 
-	-h 显示大小用人理解的单位

## cd 切换目录 

-	. 当前目录 
-	.. 上级目录 
-	~ 家目录 
-	/ 根目录 
-	- 回到上次进入目录

## pwd 当前路径

## touch 新建文件 注意文件的扩展名加这个是好习惯，创建复制移动都要注意这点

## mkdir 新建目录 

- -p 递归创建

## gedit 编辑文件ubuntu可以打开文本文件，习惯后配置好的vim还是用vim打开文件编辑

## vi 所有linux都可以用的文本编辑器

## rm 删除 

-	-i 交互式运行 
-	-f 强制进行忽略不存在 
-	-r 递归删除可删文件夹

## mv 移动文件，重命名 

-	-i 交互方式 
-	-v 显示移动过程 
-	-f 

## cp 复制文件（DOS copy）

- 文件备份 sudo cp 路径/文件名.扩展名 路径/文件名.扩展名.bak(2)
	
## tree 以树状显示路径

## clear 清屏（DOS cls）ctrl + l

## which 命令位置

## 快捷键

- 命令终止 ctrl + c 
- ctrl + shift + + 放大
- ctrl + - 缩小

## cal 日期 

-   -3 显示上月本月下月 
-	-j 显示当年第几天 直接写年份

## date 显示日期 

-	格式化显示举例 "+%Y年%m月%d日 %H时%M分%S秒"
## history 显示曾经执行过得指令 

-		直接加数字n显示最近执行过得n条指令	
-		!编号执行编号那条指令 
-      家目录下 ls -al 有个.bash_history 文件记录history

## cat 文件查看or合并文件内容  

-	-n 加行号 
-	-b 非空行加编号 
-	-s 遇到两行以上空行只显示一个
-	cat 1.txt 2.txt 连接显示两个文件

## more 分页查看文件内容（举例more etc/servers）

-	+num 从num行显示文件
-	fb 翻页ctrl +f ctrl + v
-	q 退出
-	more 1.TXT 2.txt 也可以连接文件但是效果不一样
-	-p 清屏查看
-	-s 连续两个空行只显示一行
-	回车查看一行
-	空格查看一列

---

# linux 入门基本路径介绍

/ 表示根目录
~ 根目录
~/user 根目录下用户目录
/bin 可执行的二进制文件
/etc 存配置文件
/root root权限目录
/boot 启动使用文件 /boot/grub 系统引导
/dev 设备文件 u盘挂载 mount /dev/U盘名称 /mnt
/lib 系统使用的函数库目录，程序执行过程中需要调用的一些额外的函数库
/mnt 默认挂载点
/opt 额外安装软件目录
/sbin 给root用户使用的可执行二进制文件
/tmp 程序执行的临时文件
/srv 服务启动后的需要访问的数据目录
/usr UNIX system resource应用程序的存放目录 /usr/bin /usr/lib /usr/local/lib
/var /var/log 日志文件 /var/run 存放运行程序PID
