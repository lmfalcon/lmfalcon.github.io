---
title: javascript3
date: 2019-08-10 11:06:23
tags: javascript
---

# javascript对象和类

## 内部对象

- 动态对象
	- 需用new关键字来创建一个对象示例，才能使用“对象实例名.成员”的方式来访问其属性和方法 
- 静态对象
	- 不需要用new关键字创建对象实例，直接使用“对象名.成员”的方式来访问其属性和方法即可 

### Object对象

- 创建Object对象
```
obj = new Object([value])
```
	- obj 为必选项。要赋值为Object对象的变量名
	- value 可选项。任意一种Jscript基本数据类型（Number、Boolean or String）如果value是一个对象，返回不做改动的该对象。如果value为null,undefined or 没有给出，则产生一个没有内容的对象。

- Object 对象的属性
	- prototype属性
	
	```
	objectName.prototype
	## 该属性返回对象类型原型的引用
	## 参数说明： objectName:对象名称
	## 用prototype属性可以提供对象的类的一组基本功能。对象的新实例“继承”赋予该对象原型的操作

	function array_max(){
		var i,max = this[0];
		for(i = 1;i < this.length; i++){
			if(max < this[i])
				max = this[i];
		}
		return max
	}
	Array.prototype.max = array_max;	//注意这里没有括号
	var x = new Array(1,2,3,4,5,6);
	var y = x.max();

	//上面的代码执行后，y保存数组x的最大值

	```
	- constructor属性
	```
	// object.constructor
	// 参数说明object:必选项对象或者函数的名称。constructor属性是所有具有prototype的对象的成员。他们包括除了Global和MAth对象以外的所有Jscript固有对象。constructor属性保存了对构造特定对象市里的函数引用

	x= new String("Hi");
	if(x.constructor == String)
	//进行处理（条件为真）
	or

	function MyFunc(){
	//函数体
	}
	y = new MyFunc;
	if(y.constructor == MyFunc)
	//进行处理（条件为真）
	```

### Object对象的方法

#### toLocaleString()方法

- 该方法返回一个日期，该日期使用当前区域设置并已被转换为字符串
- dataObj.toLocaleString()
	- 参数说明dataObj:必选项。为任意Data对象
	- toLocaleString()方法返回一个String对象，该对象中包括了用当前区域设置的默认格式表示的日期（需要注意在不同时间段的时间显示格式是不同的注意区分）

#### toString() 方法

- 该方法返回对象的字符串表示
- objectname.toString([radix])
	- 参数说明objectname必选项。要得到字符串表示的对象
	- radix 可选项，指定将数字值转换为字符串时的进制

| 对象|操作|
|-:-|-:-|
|Array|将Array的元素转换为字符串，结果字符串由逗号分隔且连接起来|
|Boolean|如果Boolean值是true,则返回true;否则返回false|
|Date|返回日期的文字表示法|
|Error|返回一个包含相关错误消息的字符串|
|Function|返回如下格式的字符串，其中functionname 是被调用的toString()方法函数的名称：function functionname(){[native code]}|
|Number|返回数字的文字表示|
|String|返回String 对象的值|
|默认|返回[object objectname],其中objectname是对象类型的名称|

#### valueOf()方法

- 返回指定对象的原始值
- object.valueOf()
	- object是任意固有javascript对象
|对象|返回值|
|-:-|-:-|
|Array|数组的元素被转换为字符串，这些字符串由逗号分隔，并连接在一起。其操作与Array.toString和Array.join方法相同|
|boolean|Boolean值|
|Date|储存的时间是从1970年1月1日午夜开始记得毫秒数|
|Function|函数本身|
|Number|数字值|
|Object|对象本身，这是默认情况|
|String|字符串值|


## String对象

- 动态对象
- 主要用于处理和格式化文本字符串以及定位字符串中的子字符串

### 创建String对象

#### 语法

- var newstr = new String(StringText)
	- newstr 创建的String对象名
	- StringText 字符串文本
	- 例 var newstr = new String("欢迎使用JavaScript脚本")
	- 实际上任意引号引起来的字符串常量都是String对象，可以直接使用String对象的方法和属性
	- 字符串返回的是String类型,但是String对象返回的是Object类型

### String对象的属性

#### length属性

- stringObject.length
- 用于获得当前字符串的长度


#### constructor属性

- Object.constructor
- 对当前对象的函数引用
```
// 作用1类似于Object对象的使用，下面展示另一种应用
// 获取当前对象所引用的函数代码


function chronicle(name,year)
{
	this.name = name;
	this.year = year;
}
var fred = new chronicle("Year",2007);
alert(fred.constructor);	//显示对象中的函数代码

```

#### prototype属性

- 可以为对象添加属性和方法
- object.prototype.name = value
	- object 对象名or字符串变量
	- name 要添加的属性名
	- value 添加的属性值

```
function personnel(name.age)
{
	this.name = name;
	this.age = age;
}
var information = new personnel("张三哦", 27);
personel.prototype.salary = null;	//向对象中添加属性，书上是这样写得但是这个是个类啊，对象应该是information才对
information.salary = 1700;
alert(information.salary);

```

#### String 对象的方法

|方法|说明|
|-:-|-:-|
|anchor()|创建HTML锚|
|big()|使用大号字体显示字符串|
|small()|使用小号字体显示字符串|
|fontsize()|使用指定的尺寸来显示字符串|
|bold()|使用粗体来显示字符串|
|italics()|使用斜体来显示字符串|
|link()|将字符串显示为链接|
|strike()|使用删除线来显示字符串|
|blink()|显示闪动字符串，该方法不支持IE浏览器|
|fixed()|以打字机文本显示字符串|
|charAt()|返回指定位置的字符（返回的字符编码）|
|charCodeAt()|返回指定位置的字符（返回的是字符子串）|
|concat()|连接字符串|
|fontcolor()|使用指定颜色来显示字符串|
|fromCharCode()|从字符编码创建一个字符串|
|indexOf()|检索字符串|
|lastIndexOf|从后向前搜索字符串|
|localeCompare|用本地特定的顺序来比较两个字符串|
|match()|在字符串内检索指定的值或找到一个或多个与正则表达式相匹配的文本|
|repalce()|替换与正则表达式匹配的子串|
|search()|检索与正则表达式相匹配的值|
|split()|把字符串分割为字符串数组|
|substr()|从起始索引号提取字符串中指定数目的字符|
|substring()|提取字符串中两个指定的索引号之间的字符|
|slice()|提取字符串的片段并在新的字符串中返回被提取的部分|
|sub()|把字符串显示为下标|
|sup()|把字符串显示为上标|
|toLocaleLowerCase()|按照本地方式把字符串转换为小写|
|toLocaleUpperCase()|按照本地方式把字符串转换为大写|
|toLowerCase()|把字符串转换为小写|
|toUpperCase()|把字符串转换为大写|
|toSource()|代表对象的源代码|
|valueOf()|返回某个字符串对象的原始值|

## Date对象

- 用于在网页中实现时间日期

### 创建Date对象

```
dataObj = new Date();
dateObj = new Date(dateVal);
dateObj = new Date(year, month, date[,hours[,minutes[,seconds[,ms]]]]);

```
|参数|说明|
|-:-|-:-|
|dateObj|必选项，要赋值为Date对象的变量名|
|dateVal|必选项，如果是数字，从1970年1月1日计算，如果字符串，按parse方法中的规则解析，也可以从某些ActiveX(R)对象返回的VT_DATE值|
|year|必选项，需要完整年份如1970|
|month|必选项，0-11之间|
|date|必选项，1-31之间|
|hours|可选，有下级必选，0-23|
|minutes|可选，0-59|
|seconds|可选，0-59|
|ms|可选，0-999|

```
var newDate = new Date("Jan 2,2008 19:41:40");
document.write(newDate);

//运行结果 Wed Jan 2 19:41:40 UTC+0800 2008

```

### Date对象的属性

- constructor
- prototype
- 类似用法不讲解了


### Date对象的方法

- 好多啊不想打了，查吧
- 大致分为这几类
	- Date()
	- get...()
	- parse()
	- set...()
	- to...()
	- UTC()
	- valueOf()


## event 对象

- 主要用来描述JavaScript的事件
	- 事件发生元素
	- 键盘状态
	- 鼠标位置
	- 鼠标按钮状态

### 引用

- IE中event可以全局引用例： event.propertyName
- W3C 中引用event对象
	- 必须明确的将event作为参数传递到事件处理函数中
	- 例： onKeyUp = "example(this,event)" or function example(widget,event){...}
	- 尽量避免event作为传入参数变量名

	
### 属性

- altLeft属性
	- 获取左alt键的当前状态，true为关闭，false不关闭 
	- [windows.]event.altLeft
- ctrlLeft属性
- shiftLeft属性
- button属性
	- 设置或获取事件发生时用户所按的鼠标键
	- [windows.]event.button
	- 此属性仅用于onmousedown,onmouseup,onmousemove事件，其他事件都返回0

|button属性的值|说明|
|-:-|-:-|
|0|表示没有按键|
|1|按下左键|
|2|按下右键|
|3|同时按下左键和右键|
|4|按下中键|
|5|同时按下左中|
|6|同时按下右中|
|7|同时按下左中右|

- clientX 属性
	- 该属性获取鼠标在浏览器窗口中的X坐标，他是一个只读属性，即只能获取鼠标当前位置不能改变鼠标位置
	- [windows.]event.clientX
- clientY属性
- X属性
	- 该属性设置或获取鼠标指针位置相对于CSS属性中有position属性的上级元素的X轴坐标。如果CSS属性中没有position属性的上级元素，默认以body元素作为参考对象
	- [windows.]event.X 
	- 如果鼠标事件触发后，鼠标移出窗口外，则返回的值为-1,。这是个只读属性，只能通过他获取鼠标当前位置，但不能用来改变鼠标位置。
- Y属性
- cancelBubble属性
    - 检测是否接受上层元素的事件的控制。如果该属性的值是false,则允许被上层元素的事件控制；否则值为true,则不被上层元素的事件控制。
	- [windows.]event.cancelBubble[= cancelBubble]
	- 该属性的值为一个可读写的boolean,默认false
- srcElement属性
	- 用于设置或获取触发事件的对象
	- 是事件初始目标的HTML元素对象引用
	- 由事件通过元素容器层次进行处理，并可以在任意层次进行处理，因此由一个属性指向产生初始事件的元素很有帮助。

对象类型有点多，今天就写到这了，应该多编写代码而不是写心得，感觉打字是越来越熟练，但是打示例代码的速度还是有些慢。由于没有彻底学完HTML和CSS,javascript理解有些困难，所以暂且告一段落。待日后有时间再学习。










