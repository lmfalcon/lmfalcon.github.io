---
title: CLearning4
date: 2019-09-01 14:40:00
tags: C
---

# windows下运行c程序

1. 建立1.c文件，内容如下：
```
#include<stdlib>
{
	system("mspaint")	//打开画图板
}
```
2. 打开命令行进入1.c文件位置：
```
cl /c 1.c	//编译
cl 1.c		//链接
1.exe		//执行
```

# 转义字符

#include<stdio>

```
int main(){
	printf("helloworld");
	printf("\n\a");	//换行\n	\a发声
	printf("\b");	//实现光标退格
	printf("\f");	//文本编辑器是换页，dos命令行只是垃圾字符
	printf("\r");	//\r移动到本行开头
	printf("\t");	//往前移动几个空格
	printf("\v");	//文本编辑器是垂直制表，dos只是垃圾字符
	printf("\0");	//什么都不操作，\0有没有都一样
	getchar();
	printf("\\");	//单斜杠
	printf("\"");	//一个双引号
	putchar('h');	//输入一个字符
	putchar(104);	//输出对应的ASCIIS码的字符
	putchar('\xhh');		//代表一到两位十六进制输出对应ASCIIS的字符
	putchar('\101');	//\ddd代表三位八进制
	return 1;
}
```

# 常量与变量

```
#include<stdio.h>
#include<stdlib.h>


void main(){

	int num = 10;
	printf(%d,%x",num, &num);	//%d是十进制，%x是十六进制，&num是取num的地址

	system("pause");
	
	const int x = 100;	//定义常量方法一
	#define X 100		//定义常量方法二,define本质就是替换，如果define加上分好就会连分号一起复制
	//易语言就是define加上很多标识符实现的比如
#define 主函数 main
#define 返回值为空 void

返回值为空 主函数(){
}
//上面的函数是可以编译的，因为define定义了，替换成标注的标识符
```
# 替换两个数的算法

```
int a = 100;
int b = 10;
//方法一
a = a + b;
b = a - b;
a = a - b;
//方法二
a = a * b;
b = a / b;
a = a / b;
//一般运用于节约内存的场合使用

