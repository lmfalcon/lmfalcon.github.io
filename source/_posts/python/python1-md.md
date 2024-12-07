---
title: python1.md
date: 2020-11-24 23:04:15
tags: python,datastructure
---

-------
课程来源：[AI大学Python基础入门](aidaxue.com/course/courseDetail?id=394)
-------
# 元组

## 创建元组

tuple1 = () ＃小括号创建一个新的元组

tuple1 = (‘abc',1,4,4,56,7,[1,2,'asdf'],(1,2))

#注意创建一个元素的元组时必须加逗号

tuple2 = (1,)

list1 = [1,2,3,4,5]

tuple(list1) #进行强制类型转换
 
## 常用操作

len(tuple1)


tuple1[3] #索引查找元素
tuple1[-2] #可以通过索引寻找元素，但是没法通过索引对元素进行修改

tuple1[1:3] #切片
tuple1[5:3:-1] #倒切片

tuple1+tuple2  #连接两个元组

tuple1*3 #复制

tuple2[0] = 1 
del tuple[0]  #元组元素不能修改和删除

del tuple1 #可以删除元组

max(tuple1)
min(tuple1) #取最大最小值

tuple1.count(6) #对元组内元素进行计数

## 学习问题

感觉这套课程缺乏使用实例，比如元组有啥用，怎么用，可能后面会介绍，可能一直不会介绍。不过我百度找到了

## 元组的用途

元组比列表的操作速度快
如果定义的数据是常量可以使用元组
元组不可变，可以作为字典的键(key)

# 集合

## 集合的定义

集合是无序的，所以无索引，
集合元素是不重复的，可以使用集合对列表进行去重操作

## 集合基本操作

set1 = {} #空集合

set2 = set([1,2,3,4])

type(set1)

set1.add(60) #集合中加元素

set2.update(set1) #将set1加入至set2中

set1.remove(6) #将6从集合中删除

## 集合的运算

set1-set2 #集合的差集

set1 | set2 #集合的并集

set1 & set2 #集合的交集

set1 ^ set2 #返回只被set1包含或者只被set2 包含的元素集合

set1 > set2 #如果set1真包含set2,返回true,否则返回false


## 集合的常用操作

list(set([1,1,1,2,2,4,5,6])) #列表去重

# 字典

突然想到芋圆好像是爱吃四季豆，爱吃辣，对于海鲜好像也比较喜欢，感觉好像对肉类都可以接受(最近不爱吃鱼）

## 基本用途

字典表示的是一一对应的关系，由key键value值,键值之间用“：”分隔，不同的键值对之间用逗号分隔，字典用大括号括起来，字典无序用键取数据


## 基本用法

dict1 = {} #空字典

dict2 = {'age1' : 18,'age2' : 19}

dict1 = dict([('age3',23),('age4',45)]) #可以用dict()创建字典，放入列表套元组。

dict2 = dict((['age6',23],['age7',24]))#通过元组套列表创建字典

dict1['age3']#访问键对应值如果查找的值不在字典里会报错

print(dict1,keys())#返回所有的键的列表

print(dict,values())#返回所有的值的列表

dict1.items()#返回包含所有键值的列表

del dict1['age1']#删除键值对

print（dict1）

del dict1

dict1.clear() #删除字典中所有元素的，将字典变成空字典

dict1.update(dict2) #将字典dict2中的键值对添加到dict1中

for key in dict1.keys():#遍历字典只需要遍历它的键
	print(key,dict1[key])

## 实际例子

- 有一列人名，有一列电话号码的excel表格，如何建立字典


name = ['name1','name2','name3','name4','name5']
phone_number = ['phone_number1','phone_number2','phone_number3','phone_number4','phone_number5']
zip1 = zip(name,phone_number)#zip函数将索引值一一对应组成元组
dict_phone = dict(list(zip1))

dict2 = dict1
dict1['age1'] = x
print(dict2['age1'])#会发现虽然赋值虽然发生在前面，但是改变字典1，字典2也会发生改变，print的结果是x

list2= list1
list1[0] = 0
print(list2[0])#和字典1一样
id(list1)#id()函数用于获取对象的内存地址

- 数据结构的赋值操作直接将内存地址对应
- 解决方法：


import copy #深拷贝可以用引入copy模块实现
list1=[1,2]
list2 = list1
list2 = copy.deepcopy(list1)#这样直接赋值内容，list2和list1的地址不会一样

- 芋圆很不喜欢吃面食，以后做饭注意点


# 流程控制

- 顺序
- 分支
- 循环

主要注意for经常与range()函数一起使用，range()函数是序列生成函数
range(起始值,终止值,步长)


# 数据读写

## Python的原生读写

f = open(file,mode="r",encoding=None)#file是文件路径，mode是文件打开模式，常用的应该还有encoding编码格式

### mode的常用参数

"r" 只读，默认值
"w" 可以以写的方式打开文件，会覆盖原文件
"x" 创建一个新文件打开并写入操作，如果这个文件已经存在，则会报错
"a" 以写的方式打开文件，当执行写入操作时，将会写入的内容追加在原文件之后

### 文件打开后的基本操作

f.read() #读取整个文件，字符串显示
f.readline() #一次读一行，指针在当次读取的末尾位置，直至文件的末尾。
f.readlines() #读取整个文件，以列表显示
strip() #用于移除字符串头尾指定的字符，默认为空格或者换行符，该方法只能删除开头或是结尾的字符，不能删除中间的字符。
f.seek(0,0)#第一个参数是偏移量，第二个参数是0表示文件开始处，这是默认值，1表示当前位置，2表示文件结尾

### 读取txt文件
```
f=open("path","r",encoding="utf-8")#打开文件
data=[]
for line in f.readlines():
	line=line.strip().split('\t')#去掉头尾的换行空格，并切除'\t'
	print(line)
	data.append(line)
f.close()
```

join()#这个函数用于链接两个字符串

a1 = ['a1','1']
print('\t'.join(a1))

输出结果为a1　1 

## pandas读写数据

### pandas读取txt文件

```
import pandas as pd
data=pd.read_table("path",sep='\t',header=None,encoding='utf-8',names=['col1','col2'])
#header:表头，默认不为空（以第一行作为表头，），取None,无表头
#sep：分隔符

```
- 今天芋圆说我我的名字太大众了，然后我想古代人会不会取两个字的名字，如果是两个字重名的概率会不会太大了。但是历史上不少人的名字都是两个字的比如刘备，曹操，孙权。这样两个字的名字也太普遍了。但是我忽略了一点名字为两个字的且能被我们记住的多是有名的人。古人除了名字还有字，比如关云长，张翼德，曹孟德，刘玄德，孙仲谋。还有避讳的事，只许州官放火不许百姓点灯的故事，说明以前的人如果是有名的人取名三个字也就要避讳两个字，称呼一般也不直呼其名。我如果在古代会在弱冠之年给自己取什么字呢？
- 李明=李日月=李00=李灵麟，芋圆=愈圆=0，由零结缘，零也是一种无穷。


```
# pandas读取csv文件
data2 = pd.read_csv("path",sep = ',',header = None,encoding = 'utf-8',names = ['col1','col2']
# 使用jupyter可以使用?+方法的方式查看方法下定义了哪些参数
# 例如?pd.read_csv 
# 读取excel文件的操作类似，用的是.read_excel方法
```

#### 数据写出

```
data2.to_csx("path",sep=',',header=None,encoding='utf-8',index=false)# index默认为true，index是索引，true时会输出索引列

```

## 连接数据库

### 读写mysql库

1. 创建一个连接对象

host mysql 服务器地址

port 数字类型 端口

user 用户名

passwd 密码

db 数据库名称

charset 连接编码，需要显示指明编码方式

2. 获取游标

游标是什么？

游标(cursor)是一个游动的标识，可以理解成一条sql取出对应n条结果资源的接口/句柄，就是游标，沿着游标可以一次取出一行

execute() 执行一个数据库查询和命令
fetchone() 取得结果集下一行
fetchmany(size) 取得结果集size行
fetchall() 取得结果集所有行
close() 关闭cursor


```
import pymysql # pymysql用于python3以上连接mysql的一个库
import pandas as pd
conn =  mysql.connect(host='localhost',port=3306,user='root',passwd='xxxx',db='mysql',charset='utf-8') # 创建一个连接对象，打开数据库连接
cursor = conn.cursor() # 获取游标
sql = """ SELECT *
from mysql.test1""" # 创建一个字符串语句，字符串支持换行
cursor.execute(sql)
data1 = cursor.fetchall()
# data1 = cursor.fetchmany(2)
# data2 = cursor.fetchone()
df1 = pd.DataFrame(list(data1),columns=["id","col1","col2"])
```
#### 传参

```
import pymysql # pymysql用于python3以上连接mysql的一个库
import pandas as pd
conn =  mysql.connect(host='localhost',port=3306,user='root',passwd='xxxx',db='mysql',charset='utf-8') # 创建一个连接对象，打开数据库连接
cursor = conn.cursor() # 获取游标
num0 = 6
num1 = 8
sql = """SELECT *
from mysql.test1
where col2 >= {0}
and col2 <= {1}""".format(num0,num1) # 格式化输出，将num0和num1 的值传入字符串的大括号中。由此实现传参操作
data1 = cursor.fetchall()
# data1 = cursor.fetchmany(2)
# data2 = cursor.fetchone()
df1 = pd.DataFrame(list(data1),columns=["id","col1","col2"])
```

#### 通过跳板机SSH访问数据库

```
import pymysql
import pandas as pd
from sshtunnel import SSHTunnelForwarder
with SSHTunnelForwarder(
	#配置SSH连接
	ssh_address_or_host = ("跳板机对应的ip", int('跳转机端口号")), # 指定ssh登录的跳转机的address
	ssh_password = "跳转机的密码”
	ssh_username = "跳转机的用户“
	local_bind_address = ("127.0.0.1", int("2222")), # 映射到本机的地址和端口，此处必须是127.0.0.1
	remote_bind_address = ("mysql服务器地址", int("端口号"))) as server: # mysql服务器的配置，有数据的服务器
conn = pymysql.connect(host = "127.0.0.1", port = 2222, user = "mysql服务器用户名", password = "mysql服务器的密码")
cursor = conn.cursor()	# 获取游标
```

- 今天看见芋圆感觉很憔悴，想帮帮她但是她不会接受，反而给她添麻烦了。相处中一厢情愿的事情还是尽量避免吧。也许她说的工作上的事只是需要倾听者，而不是需要你的帮助，你若提出帮助或者表达自己不能帮上忙的愧疚，她会觉得你是不是不希望听她抱怨工作上的事。不光是她也许很多人都是这样的，多注意她人的感受吧。


# pandas数据处理技巧

## DataFrame生成
```
pd.DataFrame([['a1',11],['a2',12]],columns=['col1','col2'])  #列表元组都能生成DataFrame 
```
## 查看数据框（DataFrame)数据类型

- .dtypes 方法可以查看数据框每列的数据类型
- .（列名）.dtypes 方法可以查看特定列的数据类型


## 数据框列属性变换

- df1.col2 = df1.col2.astype(int)


## 查看索引

```
list(df1.index)

```

## 查看列名

```
list(df1.columns)
```

## 列重命名

```
df1 = df1.rename(columns={"原名字":"新名字"})
```

## 数据选取

```
# 选取数据前n行
df1.header(n) #默认选取前五行
# 通过行索引
df1[1:6] # 取1到5行的数据
#通过列名选取数据
df1[["id","col1"]]
```
### 通过加条件选取数据

```
# 选取带缺失值的数据记录
df1[df1.isnull(),values==True]
df1.isnull() # 选取出来的是一个数组列表，里面都是True or False
df1[df1.nonull(),values==True]
# 缺失值填充
df1.fillna(0)
# 缺失值删除
df1=df1.dropna()
# 逻辑条件筛选
df1[~(df1.col2<=2)&(df1.col2<=10)] # ~是取非
# 类似sql语句
df1.query("col2>=6 and col2<=10") 
```

### 数据塑性（数据透视表）
```
df2
pd.pivot_table(df2.index="name",columns="date",values = "money", aggfunc = "sum", fill_value = 0)
df2_new.reset_index()
df2_new2 = pd.pivot_table(df2, index = "name", columns = "date", values = "money", aggfunc = "sum", fill_value = 0).reset_index()
df2_new2
```

### 数据拼接

- concat 是一种基本的合并方式。常用参数：axis 指明合并方向， axis = 0 是默认值，0 表示上下合并，1 表示左右合并
```
concat_data1 = pd.DataFrame({"col1":list(range(0,10)),"col2":list(range(0,10))})	

concat_data2 = pd.DataFrame({"col1":list(range(11,17)),"col2":list(range(11,17))})	

pd.concat([concat_data1,concat_data2],axis = 0) # 上下拼接时列名尽可能保持一致

# append 函数上下拼接
concat_data1.append(concat_data2).reset_index() # 将concat_data2加到concat_data1后
```
- merge 函数  
	
	常用参数：
	
	* how: 连接方式 "inner" 内连接 "left"左连接 “right" 右连接　　		
	* on 用于连接的key,即列名，要连接的数据必须要都有该列名 left_on 左侧数据用作连接的键，right_on 右侧数据用作连接的键。


```
pd.merge(df2, df1, on = "id", how = "inner") # 内连接会将两个表共有的数据连接，不共有删除。

pd.merge(df2, df1, on = "id", how = "left") # how中的以左连接数据为主即df2中有的连接，没得删除，如果df2中有，df1中没有则添加空值NaN

pd.merge(df2, df1, on = "id", how = "right")

```

## 分组统计

```
df2.groupby([分组变量])[统计变量].统计方法
df2.groupby(["name"])["money"].sum()
```




