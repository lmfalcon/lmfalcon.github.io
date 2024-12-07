---
title: javaScript1
date: 2019-08-08 14:34:46
tags: javascript
---

# javascript简介

## 特点

- 解释型语言

## 应用

- 验证用户输入内容
- 动画效果
- 窗口应用
- 文字特效
- jQuery
- Ajax


## html中的应用

###  直接嵌入

- 《script》。。。《/script》的方式嵌入内容


#### 相关属性

- 因为vim中有JavaScript的用法所以这里用中文书名号代替尖括号，防止无法显示问题
- 《script language = "JavaScript1.5">脚本语言类型及版本
- 《script src= "01.js"> 用以指定外部脚本路径，常用Javascript脚本，扩展名为.js
- 《script type = "text/javascript"> 用于代替language
- 《script defer》 文档加载完毕后再执行脚本，用于加快网页加载速度
```
<script> ... </script>
或者采用代码段方式编辑
```

### 链接外部Javascript文件

``` 
//方式说明
<script language = "javascript" src = "javascript.js"> ... </script>
```
- 用这样的方式则可以按路径使用Javascript文件

## JavaScript 语法

### 执行顺序

- 顺序执行
- 如果需要在整个html文件中执行最好放在head中



### 大小写敏感

- 需要与html作对比，html没有大小写敏感


### 每行结尾分号可有可无

- 建议还是加上吧


## 标识符

- 首字符必须是字母，下划线美元符号
- 之后可以有数字


## 关键字

|---|---|---|---|---|---|
|-:-|-:-|:-|-:|--|--|
|abstract|continue|finally|instanceof|private|this|
|boolean|default|public|int|float|throw|
|break|do|for|interface|return|typeof|
|byte|double|function|long|short|true|
|case|else|goto|native|static|var|
|catch|extends|implements|new|super|void|
|char|false|import|null|switch|while|
|class|final|in|package|synchronized|with|


## 常量

```
const 常量名：数据类型=值；
```

## 变量

- 声明
```
var varible;
```
- 可声明同时赋值
- 可同时声明赋值多个变量
- 变量只在脚本内起作用，而且也分为局部和全局变量


## 数据类型

- 整型
- 进制不同0x十六进制，0八进制
- 浮点型
- 字符串
- boolean

### 特殊数据类型

- 转义字符
|转义字符|说明|
|-:-|-:|
|\b|退格|
|\n|回车换行|
|\t|tab|
|\f|换页|
|\'|单引号|
|\"|双引号|
|\v|跳格（tab水平）|
|\r|换行（光标位置和回车不同）|
|\\|反斜杠|
|\OOO|八进制数|
|\xHH|十六进制数|
|\uhhhh|十六进制Unicode字符|

- 示例
		```
		document.writeln("<pre>");
		document.writeln("轻松学习\nJavaScript语言！");
		document.writeln("</pre>");
		运行结果为
		轻松学习
		JavaScript语言！
		```
		- 不使用pre转义字符不起作用
- 未定义值undefined和特殊数字常量NaN通常在数据类型转换后出现，因为其他的类型无法识别
- 空值null 注意不能等同于空字符串或者0


## 运算符

- 加减乘除
- 自增和自减（++，--）
- 求模

## 比较运算符

- 大于小于大于等于小于等于
- == 不判断数据类型，仅判断表面值
- === 绝对等于	判断数据类型和表面值
- !=	不判断数据类型，仅判断表面值
- !== 不绝对等于	判断数据类型和表面值


## 赋值运算符

- = 赋值
- += 
- -=
- *=
- /=
- %=
- &= 逻辑与
- |= 逻辑或
- ^= 逻辑异或 a^=b 相当于 a = a^b


## 逻辑运算符

|逻辑运算符|描述|
|:-|-|
|!|取反|
|&=|与之后赋值|
|&|逻辑与|
|竖线=|或之后赋值|
|竖线|逻辑或|
|^=|异或之后赋值|
|^|逻辑异或|
|?:|三目运算符|
| 双竖线 |或运算符|
| == | 等于运算符|
|!= | 不等于运算符|

## 位运算符

|位运算符|描述|
|-:-|:|
|&|与运算符|
|竖线|或运算符|
|^|异或运算符|
|~|非运算符|
|左尖括号两个|左移|
|右尖括号两个|带符号右移|
|右尖括号三个|填0右移|


## typeof 运算符

- 返回数据类型
```
alert(typeof a);
```

## new 运算符

- 创建一个新对象
```
new construct[(argument)]
construct 构造函数
argument 参数，可以无参
```

