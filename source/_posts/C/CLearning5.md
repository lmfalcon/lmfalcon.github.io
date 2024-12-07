---
title: CLearning5
date: 2019-09-03 13:08:28
tags: C
---

# C语言的类型

## 简介

- sizeof运算符(不是函数）可以求出类型在内存中占用的大小
```
printf(sizeof(short));
printf(sizeof(long));
printf(sizeof(int));
```
- 二进制的最高位，表示正负
```
#include<stdio.h>
#include<limits.h>
void main(){
	printf(("%d,%d"),INT_MAX,INT_MIN);	//%d表示十进制的整数
	printf(("%u,%u"),UINT_MAX,0);	//%u表示十进制的无符号整数
}
```
- 原码
	- 演示代码
	```
	#include<stdio.h>
	void main(){
		int x = 1;
		printf("%x",&x)	//打印十六进制数用%x
		//计算机的原码表示有符号整数中的正数及无符号整数
	```
- 反码
	- 正数：反码原码相同
	- 负数：符号位为1，其他位取反
	- 反码等于补码减1
- 补码
	- 正数：原码反码补码都相同
	- 负数：反码，加1
	- 计算机的负数用补码解析的（其实正负数都是用补码）
	- 可以忽略符号进行加减法（两个数直接相加）
	```
	#include<stdio.h>
	void main(){
		int x = -1;
		printf("%x",&x);
		printf("%d,%u",x,x);	
		getchar();

	}
	```
### 构造类型

- 数据
- 结构体
- 共用体

### 基本类型

- 字符类型
	- 字符常量
	```
	#include<stdio.h>
	void main(){
		//用单引号括起来的单个字符or转义字符，也可以是数字（十进制无需单引号，八进制十六进制可以加单引号）
		putchar('a');
		putchar('\n');
		putchar(123);
		//其实数字（不加单引号）也就对应ASCIIS表中的字符输出，内存中都以ASCIIS码储存
		putchar('1');//字符1
		putchar(1);	//1对应的ASCIIS码字符
		printf("双引号内部是字符串常量");
		printf("");//每个字符串都有一个/0作为字符串的结束，空字符串也有哦，所以这个占一个字节。一个字符占一个字节。空字符串一个字节，其他有内容字符串至少两个字节。
		printf("%c",'a');	//%c打印字符
		printf("%c，%d",'A'+1); //打印出B,66	说明格式化输出可以控制打印的是字符还是ascii码
		//C语言中字符串常量不能命名给字符型变量
	}

	```
	- 字符变量
	```
	char a = 'a'
	```
	- 输出可见字符
	```
	#include<stdio.h>
	void main(){
		for (int i = 32; i<127; i++)
		{
			printf("%c",i);	//我的写法
			putchar(i);	//课堂写法
		}
	}
	```
	
- 数值类型
	- 整形常量
	- 整数的原码和补码是嵌入式工程师必须掌握的
	```
	#include<stdio.h>
	void main(){
		printf("%d",10);	//10就是十进制的整形常量
		printf("%d",0100);	//0100就是八进制的整形常量
		printf("%d",0x10);	//0x10就是十六进制的整型常量
		printf("%d",12u);	//12u表示无符号整数常量，且之前不可以加负号
	}
	```
	```
	//二进制正数表示
	#include<stdio.h>
	#include<limits.h>	//用于表示数据类型的最大值和最小值类似于SHORT_MAX or SHORT_MIN,用大写字母表示
	void main(){
		int num = 10;
		printf("%x",&num);
			
		printf("\n%d,%d",sizeof(short),SHORT_MAX);
		//如果没有unsigned,默认是signed，有一个符号位

		getchar()
	}
	```
	- 浮点型
	```
	#include<stdio.h>
	#include<limits.h>
	#include<float.h>	//包含float的极限
	void main(){
		printf("%f",1.23);	//%f是十进制的浮点数
		printf("%f",1.23e4);	//e/E表示指数，10的多少次方，但是指数部分必须是整数
		printf("%d,%d",sizeof(1.0),sizeof(1.0f));	//默认没有f是double类型（8字节），有f是float类型（4字节））
		printf(("%d,%d"),INT_MAX,INT_MIN);
		printf(("%f,%f"),FLT_MAX,FLT_MIN);	//%f表示默认小数点后6位可以通过%numf控制打印到小数点后的位数
		// FLT_MAX表示能表示的最大正负数，FLT_MIN表示最小的正负数）
		getchar();
	}
	```
	```
	#include<stdio.h>
	#include<math.h>	//有很多常用的数学函数sin or cos
	void main(){
	//已知三角形的三边求三角形面积
		double a,b,c;
		a = 1.0;
		b = 2.0;
		c = 3.0;
		p = (a + b + c)/2;
		s = sqrt(p * (p - a) * (p - b) * (p - c));	//光标所在行右键可以查看定义
		printf("三角形面积为%f",s);
	}
	```
- 枚举类型

### 指针类型

- 

### 空类型


## 变量

- 声明就是让编译器知道变量的类型和存在
- 编译器建立变量符号表
	- 用于存放的内存地址，类型的储存，存放名称和数据
	- 查找是否有无声明变量

## 类型转换

### 自动类型转换

- 默认数据类型转换高精度类型加低精度类型会自动将低精度类型转换为高精度类型
- 由于无符号和有符号比较无符号范围更大，自动转换时会自动转换为无符号

### 强制类型转换

- 强制类型转换格式 类型名（表达式）如(int)1.0
- 高精度装换为低精度有精度丢失，所以这个过程必须要有强制类型转换
- 高精度转换为低精度还可能出现数据溢出的情况
- 强制类型转换得到的所需中间变量，原变量类型。变量值都保持不变。内存会单独开出强制类型转换中间变量的内存空间。
