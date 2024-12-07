---
title: pythonbasic1
date: 2020-11-15 13:52:51
tags: python
---

# 数据结构

## 分类

列表，元组，字典，集合

### 列表

list1 = []  空列表
列表是有序集合可以通过索引访问，
无序集合需要遍历才能知道其中的东西

type(list1)查看类型

列表长度

len(list1)

print(list1)

合并列表

list1= list1 + list2

list1.extend(list2) 将list2的函数添加到list1，扩展原有列表

list1.append("adsfa") 将列表添加新的元素

list1.insert(2,[2,3])在列表中索引为2的元素前加上一个新元素

列表索引

list[2] 列表中的第三个元素

list.index[obj] 列表中找到这个元素的索引，找到第一个索引位置

- 列表切片


list1[num1:num2:num3] 通过索引选取num1到num2的元素，num3是步长表示步长1表示连续取数，步长默认也是1，步长2表示第一项第三项第五项这样隔一取一。想象一下你在踩着格子走，1步一格和一步两格踩到的格子就明白什么是步长了。

倒着取数list1[-1],这个估计在栈或者队列中会用到

- 修改列表


list1[2] = "python" 修改列表元素
list1[2:4] = ["python","a"]修改第三第四元素

-列表统计

list1.conut(obj)  列表中某个元素统计
循环统计每个元素出现次数，要转换为set 结构例子
```
for i in set(list1):
	print(i,list1.count(i))

```

- 删除列表元素


list1.pop()  默认是最后一个元素移除

list1.pop(index) 索引移除

list1.remove(object) 移除某元素第一个匹配项

list1.reverse()   反转列表

del list1 删除列表一
del list1[index] 删除列表中的索引数

- 列表排序


list1.sort(reverse = True)倒序排序

list1.sort(reverse = False)正序排序

- 查找最大最小值


max(list1)
min(list)


- 常用操作


```
#生成一个1到10的列表

for i in range(1,11):
	list1.append(i)
print(list1)

# 简化写法

list1 = [i for i in range(1,11)]


