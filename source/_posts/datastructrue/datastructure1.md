---
title: datastructure1
date: 2019-08-18 09:41:46
tags: datastructure,DataStructureAbstract, array, sort, stack, queue, linklist, recursion
---

# abstract

## 优缺点

|数据结构|优点|缺点|
|-:-|-:-|-:-|
|数组|插入快，如果知道下标可以非常快的存取|查找慢，删除慢，大小固定|
|有序数组|比无序数组查找快|删除和插入慢，大小固定|
|栈|提供后进先出方式的存取|存取其他项很慢|
|队列|提供先进先出方式存取|存取其他项很慢|
|链表|插入快，删除快|查找慢|
|二叉树|查找、插入、删除都快（如果树平衡}|删除算法复杂|
|红黑树|查找、插入、删除都快。树总是平衡|算法复杂|
|2-3-4数|查找、插入、删除都快。树总是平衡，类似的树对磁盘存储有用|算法复杂|
|哈希表|如果关键字已知则存取极快，插入快|删除慢，如果不知道关键字则存取很慢，对存储空间使用不充分|
|堆|插入，删除快，对大量数据项的存取很快|对其他数据项存取慢|
|图|对现实世界建模|有些算法很复杂|

## 基本概念

- 数据结构除了数组外都可以被认为是抽象数据结构（ADT）
- 常用操作
	- 插入
	- 寻找数据项
	- 删除

# 软件工程简述

- 软件生命周期
	- 分析
	- 设计
	- 验证
	- 编码
	- 测试
	- 生产
	- 维护


# C与Java的区别

- Java无指针
- Java有内存回收机制
- Java输出不用预处理，System.out.println可以直接用。print 和println的区别在于是否换行
- Java中判断类是否是同一个通过==的方法来判断，而判断类的属性是否一致通过equals进行判断
- 调用java.io.*需要为所有的输入方法加上throws IOException
```
//java输入字符
public static char getChar() throws IOException
{
String s = getString();
return s.charAt(0);
}
//String类的charAt()方法返回一个String类对象中某个特定位置的字符，在上面的例子中，是第一个字符，号码是0.这个方法避免了无关的字符留在输入缓存中，正是无关的字符导致后续的输入总是出现错误。

//输入整数
public int getInt() throws IOException
{
String s = getString();
return Integer.parseInt(s);
}
//Integer类的parseInt()方法将字符串转成int型。

// 输入浮点数

public int getDouble() throws IOException
{
String s = getString();
Double aDub = Double.valueof(s);
return aDub.doubleValue();
}
//字符串先转换成一个Double型的对象（大写D，double类型的封装类）之后用doubleValue()方法将这个对象转换为double型。
// float型同样有Float类和valueOf()和floatValue()方法
```


# 数组array

- 其中不允许有空的数据项，否则会出现删除查找困难需要判断，是否有空数据项，难以判断是否结尾。
- 查找平均数据项为N/2


## 重复值问题

- 判断关键字是否重复
||不允许重复|允许重复|
|-:-|-:-|-:-|
|查找|N/2次比较|N次比较|
|插入|无比较，一次移动|无比较，一次移动|
|删除|N/2次比较，N/2次移动|N次比较，多于N/2次移动|

## 数组操作


- 初始化数组
```
int[] intArray;
intArray = new int[100];
//or
int[] intArray = new int[100];
//or
int intArray[] = new int[100];
// 自定义数组创建数组对象
autoData[] carArray = new autoData[4000];
//除非开始赋值否则它们将一直是特殊的null对象，尝试访问会出现空指针赋值的错误
，访问前需要先赋值
```
- 数组长度
```
int arrayLength = intArray.length;
```
- 访问数组数据项
```
temp = intArray[3];
intArray[7] = 66;
//注意数组下标从0开始，所以上例中是第八个数组值
```
## 用Java类设计数组程序

```
//lowArray.java
// demonstrate array class with low-level interface
// to run this program: C > java LowArrayApp

class LowArray
{
private long[] a;	//ref to array a
public LowArray(int size)	//constructor
	{ a = new long[size];}	//create array
public void setElem(int index,long value) //setvalue
	{ a[index] = value;}
public long getElem(int index)	//get vlaue
	{return a[index];}
}	//end class LowArray

class LowArrayApp
{
public static void main(String[] args)
	{
	LowArray arr;	//reference
	arr = new LowArray(100);	//create LOwArray object
	int nElems = 0;	//number of items in array
	int j;	//loop variable

	arr.setELem(0,77);	//insert 10 items
	arr.setElem(1,99);
	arr.setElem(2,44);
	arr.setElem(3,55);
	arr.setElem(4,22);
	arr.setElem(5,88);
	arr.setElem(6,11);
	arr.setElem(7,00);
	arr.setElem(8,66);
	arr.setElem(9,33);
	nElems = 10;	// now 10 items in array

	for (j = 0; j < nElems; j++)	// display items
	System.out.print(arr.getElem(j) + " ");
System.out.println("");
int searchKey = 26;	//search for data item
for (j = 0; j < nElems; j++)	//for each element
	if(arr.getELem(j) == searchKey)	// found item?
		break;
if(j == nElems)		//no
	System.out.println("Can't find " + searchKey);
else				//yes
	System.out.println("Found " + searchKey);
// delete value 55
for(j = 0; j < nELems; k++)		// higher ones down
	arr.setElem(k, arr.getElem(k+1));
nElems--;	//decrement size
for(j = 0; j < nElems; j++)	// display items
	System.out.print( arr.getElem(j) + " ");
System.out.println("");
}	//end main()
}//end class LowArrayApp


// 将普通的Ｊａｖａ数组封装仅LowArray类中。类中的数组隐藏了起来，它是私有的，所以只有LowArray 类中的方法才能访问它。其中的三个方法分别用来插入和检索一个数据项，和构造函数，创建一个特定大小的数组
//LowArrayApp创建一个LowArray类的对象并用它储存和操作数据。可以将LowArray类想成是工具。LowArrayApp类使用者
```

## 定义更加泛用的接口

```
// highArray.java
// demonstrates array class with high-level interface
// to run this program: C>java HighArrayApp

