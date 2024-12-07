---
title: javascript2
date: 2019-08-09 14:20:19
tags: javascript
---

# Javascript流程控制

## 选择语句

### if语句

- 类似C语言


### switch语句

```
switch(expression){
	case judgement 1:
		statement1;
		break;
	case judgement 2:
		statement2;
		break;
	...
	default:
		statement n;
		break;
}
```

## 循环语句

### while语句

- 类Ｃ语言

### dowhile语句

### for语句

```
for(i=1;i<100;i+=1){
sum = sum +i;
}
```

## 跳转语句

### continue语句

- 终止本次循环并开始下一次循环


### break语句

- 中断循环


# 函数

##  定义
```
function functionName(parameter 1,parameter 2,...){
	statements;
	[return expression]
}
```
## 调用

- 通常函数定义在head中，通常会被在body段调用
- 如果定义前调用会出错
- 还可以通过链接调用函数
```
## 定义函数 test(),之后为调用过程

<a href= "javascript:test();">test</a>

```

## 参数的使用

- 定义函数时的参数叫做形参（用逗号分隔多个形参）
- 使用函数时提供的参数是实参（多个实参用逗号分隔）
- 定义了多少形参调用函数时就要使用多少实参（这里注意和python不太一样，Python中可以定义有限个形参，但是不一定使用它）


## 函数返回值

- 可以将定义的函数返回一个值供其他程序段使用
- return


## 嵌套函数

- 定义：在函数内定义函数
- 好处：内部函数可以得到外部函数的参数和全局变量
- 缺点：函数的可读性降低


## 递归函数

- 函数体调用自身
- 容易造成死循环
- 定义递归函数的两个必要条件
	- 结束递归的条件
	- 包括一个递归调用语句
	


## javascript中的内置函数

|函数|说明|
|-:-|-:-|
|eval()|求字符串中表达式的值|
|isFinite()|判断一个数值是否为无穷大|
|isNaN()|判断一个数值是否为NaN|
|parseInt()|将字符串转换为整型|
|parseFloat()|将字符型转换为浮点型|
|encodeURI()|将字符串转换为有效的URL|
|encodeURIComponent()|将字符串转换为有效的URL组件|
|decodeURI()|对encodeURL()编码的文本进行解码|
|decodeURIComponent()|对encodeURIComponent()编码的文本进行解码|

- 使用示例
```
## 用于将首位数字字符串转换为数字，如果不是以数字开头会返回NaN
parseInt(StringNum,[n])

## 将首位为数字的字符串转换为浮点数，如果不是以数字开头会返回NaN
parseFloat(StringNum)

isNaN(Num)
isFinite(Num)
## 参数说明	url需要转换为网络资源地址的字符串

## URI和URL都可以表示网络资源地址，URI的表示范围更广泛，通常情况下两者是等同的,encodeURI()函数只对字符串中有意义的字符进行转义。如将字符串中的空格转换为"%20"
encodeURI(url)

## 将encodeURI()转码的网络资源地址转换为字符串并返回，decodeURI()是encodeURI的逆向操作

```

## Function()构造函数和函数直接量

- 构造函数Function()允许在运行时动态创建和编译JavaScript代码，而函数直接量却是程序构造的一个静态部分，就像函数语句一样
- 每次构造函数Function()时都会解析函数体，并创建一个新的函数对象。如果这个函数使用比较频繁则不推荐使用构造函数，会造成效率低下。而函数直接量不论是循环还是嵌套函数中，既不会每次调用重新编译，也不会每次遇到时都创建一个新的函数对象
- Function()创建的函数使用的不是静态作用域，相反地，每次都当做顶级函数进行编译


```
## 通过自定义函数限制键鼠操作

function maskingkeyboard(){
	if(event.keyCode==8){			//判断是否为退格键
		event.keyCode=0;
		event.returnValue= false;
		alert("当前设置不允许使用退格键");
	}

	if(event.keyCode==13){			//判断是否为回车键
		event.keyCode=0;
		event.returnValue= false;
		alert("当前设置不允许使用回车键");
	}
	if(event.keyCode==116){			//判断是否为F5键
		event.keyCode=0;
		event.returnValue= false;
		alert("当前设置不允许使用F5键");
	}

	if((event.altKey)&&((window.event.keyCode==37)||(window.event.keyCode==39))){				//判断是否为Alt+左右方向键
		event.returnValue= false;
		alert("当前设置不允许使用Alt+左右方向键");
	}
	
	if((event.ctrlKey)&&(event.keyCode==78)){				//判断是否为ctrl+N
		event.returnValue= false;
		alert("当前设置不允许使用Ctrl+N ");
	}
	if((event.shiftKey)&&(event.keyCode==121)){				//判断是否为shift+F10组合键
		event.returnValue= false;
		alert("当前设置不允许使用shift+ F10");
	}
}
function rightKey(){	//判断单击是否为鼠标右键
	if(event.button == 2){
		event.returnValue=false;
		alert("禁止使用鼠标右键！");
	}
}


##在html中body处插入键盘控制函数
<body onkeydown="maskingKeyboard()">
##在文档的onmousedown事件中调用rightKey()函数
document.onmousedown=rightKey;		//当鼠标右键被单击时调用rightKey()函数		
