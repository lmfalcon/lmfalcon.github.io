---
title: linuxbasic2
date: 2019-07-23 22:28:27
tags: linux

---

# linux基本终端操作

## echo 输出命令 

　　echo "hello world" 终端输出hello world
　　echo "hello world" > helloworld.txt
　　　　> 重定向至输入至特定位置
　　echo "xxxx" >> helloworld.txt
　　　　> 再次重定向则覆盖
　　　　>>两次重定向会追加

## > 终端能输出的都能重定向输出

## | 管道，有输入有输出

	指令1|指令2|...|指令n	从指令1的输出作为指令2的输入，一直到指令n输出
	举例：ls -l|more 查看文件列表并分屏显示

## ln 建立链接

1. -s 软连接
   1. 类似快捷方式
   2. 删除软连接不影响源文件
   3. 软连接显示链接文件大小
   4. 可以链接不存在文件
   5. 可以连接目录
   6. 可以跨系统
例子：ln -s 1.txt softlink1.txt	
2. 硬链接	
   1. 类似多名称
   2. 删除硬链接，若无其他硬链接删除data，若有则无影响
   3. 硬链接显示data大小，多个硬链接实际上只有data实际大小
   4. 不可以链接不存在文件
   5. 不可链接目录
   6. 不可跨系统
例子：ln 2.txt hardlink2.txt

---

## grep 文件内容搜索

-	grep '搜索内容' 搜索文件路径
-	-t 忽略大小写
-	-n 显示行号
-	-v 取反，不显示搜索内容
-	grep 搜索内容可用正则

## find 文件搜索

1.	名称搜索
   -		find ./ 文件名称
   -	类正则：
			find ./ '*.txt'
			find ./ 'sa?asd.txt'
2.	大小搜索
	- find ./ -size +30M				 大于30M
	-			    -30M				 小于30M
	-			    +15M -size -30M	 大于15M小于30M

---

## tar 归档文件 和 gz 压缩文件

1.	归档是确保文件完整性
2.	压缩是节省空间
3.	tar > 源文件
4.	gz 文件
   - 可能   > 源文件
   - 也可能 < 源文件
5.	-c 生成档案文件，创建打包文件
6.	-v 显示进度
7.	-f 指定文件名称，必须放最后
8.	-x 解开打包文件
9.	-z 解压缩和压缩
10.	-C 指定要解档目录

### 常用操作:

	1.	tar -cvf 归档文件名.tar 待归档文件1...		改变文件大小
	2.	tar -xvf 归档文件名.tar						改变文件大小
	3.	tar -zcvf 压缩文件.tar.gz 待压缩文件1...	改变文件大小
	4.	tar -zxvf 压缩文件.tar.gz					改变文件大小
	5.	tar -zxvf 压缩文件.tar.gz -C 指定目录

## zip 和 unzip 

1.	zip -r a.zip a  压缩a目录成a.zip文件
2.	unzip a.zip		解压缩文件

## bz2 压缩与解压

1.	-j 解压和压缩
2.	tar -jcvf all.atr.bz2 *.txt
3.	tar -jxvf all.atr.bz2 

## rar和unrar

-	类似zip
	
---

## 文件权限

ls -l 
文件类型 文件拥有者u 文件所属组g 其他用户权限o 文件指针数 拥有者 用户所在组
rwx-	4210	 读，写，执行，无权限
所有用户a
chmod 权限修改
- -R 递归修改
- chmod u+r 文件名	 加权限
- chmod u-r 文件名	 减权限
- chmod u=rwx 文件名   设置权限
- chmod 777 文件名   
	-	7 rwx
	-	6 rw-
	-	5 r-x
	-	4 r--
	-	3 -wx
	-	2 -w-
	-	1 --x
	-	0 ---


