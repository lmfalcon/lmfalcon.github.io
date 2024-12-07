---
title: CLearning7
date: 2019-09-05 23:45:34
tags: C,C++ 
---

# bool类型

- C++有bool类型的变量，C语言没有。
- C中bool类型可以用char和int类型代替


# 块语句

- 用大括号包起来的语句块
- C中块语句定义的变量单独开辟一块内存空间，作为局部变量。而且块语句外可以定义同名变量
- 同一块语句中变量不能重名


# 算法表示
 
- 伪代码法
	- 算法不能有二义性
- 流程图法
	- 起止框				椭圆形
	- 输入输出框			平行四边形
	- 处理框				正方形		完成某些操作
	- 判断框				菱形		
	- 连接点				小圆		流程图太大则用于分解连接
	- 流程线				带箭头线	表示执行方向


# 结构化程序设计

- 分治思想
```
#include<stdio.h>
#include<stdlib.h>
#include<windows.h>

void openBaidu(){
	ShellExecuteA(0,"open","http://www.baidu.com",0)
}

void closeBaidu(){
	system("taskkill /f /im iexplore.exe");
}

void clickBaidu(){
	SetCursorPos(40,40);	//设置鼠标位置
	Sleep(5000);
	mouse_event(MOUSEEVENTF_LEFTDOWN,0,0,0,0);	//鼠标左键按下
	mouse_event(MOUSEEVENTF_LEFTUP,0,0,0,0);	//鼠标左键弹起
	mouse_event(MOUSEEVENTF_LEFTDOWN,0,0,0,0);	//鼠标左键按下
	mouse_event(MOUSEEVENTF_LEFTUP,0,0,0,0);	//鼠标左键弹起
	


}

void main(){
	while(1){
		openBaidu();
		Sleep(5000);
		clickBaidu();
		Sleep(5000);
		closeBaidu();
		Sleep(1000);
	}
}
```
- 通过不同的函数实现不同的功能，面向对象是对分治最好的体现。


# windows输入输出

- cmd中切换到操作目录
- ipconfig<0.txt>10.txt
- 上一步操作会将0.txt中的操作输入到ipconfig中（实际上没有做任何事）之后将ipconfig中的内容输入到10.txt中
- 在windows做这个操作会会覆盖之前的文档内容，Ubuntu中只是添加内容。
- ubuntu的命令行操作不同例如查询ip：ifconfig>>10.txt


# if选择分支结构

- 可以嵌套，但是还是容易乱建议减少嵌套，而是单独设计函数，这样简介清晰
- if else嵌套时注意一定要配套，不要漏写，多写。


# switch case多分支选择语句

- case 后的常量值不能重合
- 多个case可以共用一个语句块
- default分支不限定在最后，内部任何分支没有先后顺序。
- case相当一个开关，如果不加break会一直执行下去。
- 不加break说明你希望连续执行多个分支
- switch语句一般用于处理枚举类型数据
- switch的表达式只能是整数或者字符，只能用于处理常量（因为case中只能是常量，只能判断相等）


# 循环实现移动窗口

```
#include<stdio.h>
#include<stdlib.h>
#incldue<Windows.h>

void openQQ(){
	ShellExecuteA(0,"open","\"C:\\Program File (x86)\\Tencent\\QQ....QQ的位置",0,0,1);
}

void moveQQ(){
	HWND win = FindWindowA("TXGuiFoundation","QQ2013");		//HWND QQ窗口编号
	//FindWindowA根据类名和标题寻找窗口
	if(win == NULL)
	{
		printf("QQ失踪");
	}
	int y =0;
	while(i < 900)
	{
		SetWindowPos(win,NULL,y*16/9,y,400,400,0);	//设置窗口大小，以及窗口位置
		Sleep(50)
		y += 10;
		if(y/10%2==1){
			ShowWindow(win,SW_HIDE);
		}
		else{
			ShowWindow(win,SW_SHOW);
		}
	}
}
void main(){
	system("taskkill /f /im QQ.exe);
	openQQ();
	Sleep(5000);
	moveQQ();
	Sleep(5000);
}
```

