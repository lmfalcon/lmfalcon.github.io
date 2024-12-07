---
title: CLearning1
date: 2019-08-29 14:23:25
tags: C
---

# 第一段代码
```
#include<stdio.h>
void main(){
	printf("helloworld");
	getchar();	//等待输入一个字符
}
```
- 注释被编译器忽略，注释不影响exe文件的大小
- 断点可以分析程序当前的运行状态
- include 的作用
	- 包含头文件内容类似与import的库
	- 一般系统的文件用尖括号，而自己编写的用双引号
	- 井号与include可以有多个空格，并且最后不需要加分号结尾
- main 函数有且只能有一个


# 命令行代码

```
#include<stdlib.h>

void main(){
	system("ipconfig"); //in windows operate system,print ip info
	system("ping www.qq.com");
	system("pause");

	system("C:\\文件目录windows的形式"); //system函数的传入参数就是命令行参数
	system("net config");	//查看正在运行的网络服务
	system("netstat -a");	//监听所有程序端口信息
	system("tasklist");	//查看所有任务
	system("route print");	//查看ip路由
}
```

# windows操作
```
#include<stdio.h>
#include<windows.h>

void main(){
	printf("hello,天朝");
	MessageBox(0,"你好天朝","helloworld",0);
	//第一个参数设置为0，第一个参数是依赖的窗口编号，相当于是谁弹出来的
	//第二个参数是对话框的内容，
	//第三个参数是对话框标题，
	//第四个参数是对话框类型，设置成0即可）
	ShellExecute(0,"open","dir",0,0,1);	
	//C语言中双斜杠只代表一个斜杠,windows中的地址一定要注意
	//打开一个文件，文件夹
	ShellExecute(0,"open","url",0,0,1);
	//打开一个网址
	ShellExecute(0,"open","系统软件命令",0,0,1);
	//例如notepad打开记事本
	ShellExecute(0,"print","文件名",0,0,1);
	//打印文件
	//ShellExecute是windows系统中用于操作的函数
	ShellExecute(0,"open","mailto",0,0,1);
	//第三个参数替换成mailto：邮件地址即可直接发邮件
	/*
		参数说明
		1.那个窗口执行，0表示系统执行
		2.执行什么操作，一般open，print
		3.执行的文件路径，网址，邮件地址，可执行文件
		4.5.系统一些保留参数，一般为0
		6.控制打开的窗口显示（），隐藏（），最大化（1），最小化（6）但是不一定好用
	*/
}
```


# 头文件源文件预编译指令

- 一般情况下函数的声明应该放在头文件
- 函数的实现与变量的定义应当放在源文件

## 头文件

- 英文是head，后缀是.h,头文件是源文件的辅助文件，一般把一些函数变量，函数定义放到头文件


## 源文件

- 一般以cpp或c结尾
- cpp可以兼容c
- 函数的实现一般在此
- 同样的作用域范围，定义不可以重复，文件也不能重复包含（类似与定义重复）
```
void main() {
	printf("dsjflkasfd");	//无预编译文件无法执行	
	getchar();
}
```
### 标准化输出

```
printf("\n");	//换行
printf("%d",num);	//十进制显示
```


## 预编译指令
    	
- include是预编译指令
- 预编译指令是不需要加上分号的，加上也不影响执行
- include可以包含任意类型可以.h,.c,.cpp
