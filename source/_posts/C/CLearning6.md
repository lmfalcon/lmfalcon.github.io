---
title: CLearning6
date: 2019-09-04 12:39:58
tags: C 
---

# C语言printf

- 八进制%o
- 十进制%d
- 十六进制%x


# C语言打印二进制

```
#define _CRT_SECURE_NO_WARNINGS	//关闭安全检查
#include<stdio.h>
#include<stdlib.h>

void main(){
	int num =12312;
	char str[32];
	_itoa_s(num,str,32,2);	//最后一位传参定义转换为几进制
	printf("%s",str);

}
```

# 显示极大极小值

- 因为之前写过int，unsigned，float，这里只介绍double
```
# include<stdio.h>
# include<float.h>

void main(){
	printf("%400f,%400f",DEL_MAX,DEL_MIN);	//之前可能有地方printf写错了，暂时不改了，反正不会重用这里的代码
	//注意这里的极小值其实是小数点后的精确位数
	}
```

# 类型提升

- char,short字符无论有无符号都会在表达式中转换为int or unsigned
```
...
printf("%d,%d,%d",sizeof(short1),sizeof(short2),sizeof(short1+short2))	//会输出2,2,4
//sizeof可以判断表达式，short字符无论有无符号都会在表达式中转换为int
```

# 可以跨平台移植的软件

## 不同平台的C

- 不同平台，不同编译器，同样的一个整数数据类型，可能大小不一样
- int	16位的情况下是2个字节，32位	4个字节
- long 64位linux是8个字节，windows 32,64都是4个字节


## 解决方法

```
#include<stdint.h>	//数据类型可以跨平台移植，字节都是一样的，只要支持C99的编译器都可以
#include<stdio.h>
#include<stdlib.h>

void main(){
	int32_t	num =123;
	printf("%d,%d",sizeof(num),num);
}
```

# bool型数据

```
#include<stdbool.h>		//支持C语言的bool型变量
//因为每次都要打印，但是我不想写#include<stdio.h>所以省略以下内容

void main(){
	_Bool bl;
	bl = true;	//1
	printf("bl=%d",bl);
	printf("\nsize= %d",sizeof(bl));
	}
```

# stdlib.h中的随机数

- 随机数生成代码

```
time_t
srand((unsigned int)time(&ts));	//用系统时间生成随机数种子
a = rand%num //a是生成的随机数范围在0到num之间，如果要改变下线可以加减一个数同时调整上限即可
```

# 运算符

## 算数运算符

- 数学计算中有高精度数参与，则结果按高精度表示
- 加减乘除取余，自加自减等

```
//键盘输入一个数举例
//由于键盘输入常常是字符串（与Python作对比eval函数好用啊）
#define _CRT_SECURE_NO_WARNINGS

void main(){
	int x,y;
	scanf_s("%d",&x);
	scanf_s("%d",&y);	//键盘输入，输入的就是进入到int x,y中的就是数字了
	}
```
- 求余运算操作数不能包含double，float类型
- 求余运算除数和被除数都可以是负数
- 要打印%就必须写上两个%%，例如
```
printf("x%%y=%d",z);
//输出为x%y = z
```
- 求余函数（x-(x/y)*y)
- 自加自减运算符优先于乘除运算符
- 左值就是等号左边的值，等号是赋值运算，赋值运算规则如下
	 - 左边不能是表达式
	 - 左边不能是常量或者一个数
	 - 赋值号会自动将右值转换为左值的类型

### 逗号运算符

```
int num = (1,2);
printf("%d"，num);
//输出为2
```
- 这里的逗号就是顺序求值运算符
- 整个表达式的值就是逗号后面的值
- 逗号运算符优先级最低
- 只在顺序求值时起到求值作用，其他时候只是连接语句或者间隔作用


## 关系运算符

- ? 表达式1:表达式2
```
5 >3 ? printf("成立") : printf("不成立");
```
- 字符串比较，如果是常量是一个内存地址，但是如果除常量外还另外定义了一个变量，字符串变量就算和常量的值相同，用==判断的结果也是false
- 条件运算符且条件运算符的优先级高于赋值运算符，运算顺序是从右到左

## 逻辑运算符

- 表达式1？表达式2：表达式3	这个是三目运算符
- 三目运算符会自动进行数据类型转换
```
int num =2;
float fl = 1;
printf("%f",num > fl ? num : fl);
```

## 位运算符



# 左值和程序实体

- 程序实体是内存中的一块区域
- 左值是左值表达式简称，是指明程序实体的表达式
- 判断一个程序左值的方法是看是否能放在等号左边（有例外const）
- const是例外，初始化的时候可以放在赋值号左边。const变量必须一开始就初始化，而且const是左值

# 插入汇编语言

```
#include<stdio.h>
void main(){
	int x = 10;
	_asm	//插入汇编语言
	{
		mov eax,20	//将20这个值赋值给寄存器eax
		add eax,-15	//将eax的值加上-15
		mov x,eax	//将寄存器eax的值赋值给x
	}
	printf("%d",x);	//打印5
	getchar();
}
```
- 汇编常用语逆向软件开发和嵌入式开发


# 输入输出知识补充

## 输入double

```
double da,db,dc;
scanf_s("%lf%lf%lf",&da,&db,&dc);	//载入这三个数的地址，double类型必须用%lf
```
## %格式化输出

- %格式化输出，后接控制输出形式

|字母|含义|
|---|---|
|d or i|有符号十进制|
|o|无符号八进制|
|x|无符号十六进制|
|e|标准指数形式输出单双精度实数|
|u|无符号十进制|
|c|输出单个字符|
|s|输出字符串|
|f|小数点形式输出单双精度实数|
|g|选用输出宽度较小的格式输出实数|
|a|按照十六进制的指数输出|

```
printf("hellochina%nsfasfa",&num)
//仅在linux中使用（2014年），%n作为统计之前输出多少个字符，并保存到num中。

```

字母|含义
---|---
 \- |输出的数字或字符以左对齐，右边填空格的方式输出
 0| 输出的空位用0填充
m(一个正整数)|输出数据的字段宽度。如果实际位数多于m,按照实际位数输出，如果实际位数少于m,则补以空格
.n(一个正整数）|对实数，表示输出n位小数，对字符串，表示截取的字符个数
（字母）|输出长整形整数
*|输出后面的整数单位，动态变化，*相当于变量
空格|正数前面添加一个空格作为前缀，负数不变
#|显示八进制和十六进制时会加0和0x方便理解，#确保一定保留小数点
+|显示正号

```

#include<stdio.h>
void main(){
	printf("%d",10);
	printf("\n%ld",10);
	printf("\n%8d",10);	
	printf("\n%08d",10);
	printf("\n%-08d",10);
	printf("\n%.4f",1.23456789);
	printf("\n%.5s","abcdefg");
	for(int i =3; i<10; i++){
		printf("\n%*d",i,10);//*与i对应，表明宽度为i，输出10
		printf("\n%*.*f",2*i,i,10.9);	//2*i宽度，i小数点后保留几位
	}
	getchar();
}
```
- 不同的数据类型应该用相同的形式输出否则会出问题。

## typedef

- 没有创建一个新的数据类型只是为已有数据类型起一个别名
```
typedef unsigned int UIT
void main(){
	UIT i = 45536;	//代替unsigned int 
}
```

## puts

- puts类似printf但是puts会自动换行
```
puts("helloworld");
```

## scanf

- 输入多个数据可以用空格tab或者回车，但最后一个一定要回车。
- scanf要注意变量初始化，否则如果scanf未按格式输入，很可能会出现无效数据
- scanf中还可以规定输入格式，scanf中如果有%和空格之外的符号，必须输入那些符号进行格式化输入。
- 空白符在百分号前无影响，在百分号后会需要输入一个数据但是不影响输入结果。
- scanf中必须传入内存地址也就是变量前必须有&符号
- 输入%c时所有转义字符都被当做有效字符，回车这个虽然也可能转义但是一般只要正常输入字符就不会出现转移情况
- 扫描字符集合避免错误

```
char str[30] = {0};	//定义字符串，全部初始化为字符'\0'
scanf_s("%[xyz]",str);	//设定只接受xyz，如不是则停止输入。例如输入123xyz，什么都不会输入输出
//中括号内类似正则匹配
//注意\n可以作为匹配条件，此时需注意是否添加\n,否则会影响回车输入
printf("%s",str);

```
```
int num;
int data;

scanf_s("%d%n",&num,&data);	//%n用以统计输入多少个字符
printf("%d%d",num,data);



```
## getchar 

- 会把回车也当做字符


## gets

- gets_s是安全的输入类似scanf_s
- 用处是获取一个字符串



## sprintf,sscanf

```
sprintf(str,"%s%s","ge","dit");
//将两个字符串合并
```
```
int num;
char str[40] = "num = 99";
sscanf(str,"num=%d",&num);
printf("%d",num);
//通过sscanf去除其中的数字
```
```
int num
char str[40] = "for /1 %i in (1,1,10) do echo china";
sscanf(str,"for /1 %%i in (1,1,%d) do echo china",&num);
printf("\n%d",num);
num = 20;
sprintf(str,"for /1 %%i in (1,1,%d) do echo china",num);

```
