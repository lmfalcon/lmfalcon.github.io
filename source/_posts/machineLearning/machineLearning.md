---
title: machineLearning
date: 2021-01-07 23:07:57
tags: 吴恩达,machineLearning 
---
---
# 吴恩达机器学习课程多遍学习感悟

- 之后我每一段我觉得是需要掌握的重点的地方会列三段代码，第一段是第一遍学习后的感悟，第二段是我第二次视频学习后的感悟，第三段暂时决定是学完整个视频后重新审视第一次和第二次学习并总结精炼语句给出解释。

---

## P1-P5什么是机器学习，监督学习，无监督学习，模型描述

---

### 什么是机器学习

学多了才会有更深的感悟，这里没必要多解释，直接进入下一个内容
```
第二遍学习发现自己在这里漏了一个挺重要的内容
Task
Experience
Performance
简写TEP，
T计算机所做的任务不断重复
E计算机得到的经验成果
P评估Ｅ是否是有价值的
```

---
### 监督学习supervisedlearning
```
在我看来课程主要讲了监督学习的概念：在确定数据库样本中的分类的情况下，看机器是否能将数据进行分类。
两种监督学习的例子：分类和回归
```
```
监督学习中我们已经确定了样本的正确性，并能够给样本进行分类了，和无监督学习相比无监督学习更像是监督学习的前置操作。
```
#### 分类classification

```
类似与离散函数，只有0,1选项的选择，试用的是小的数据样本，数据样本并不连续，数量也不多
```
#### 回归regression
```
类似于连续函数，数据的样本多且相对比较连续，可以拟合出相应的曲线。
```
```
多样本中模拟出原样本中不存在的值其实就是高中数学学的线性回归，用原本样本得到拟合曲线，最终在拟合曲线上找到你要的值
```
---

### 无监督学习unsupervisedlearning
```
无监督学习的概念：在不确定数据库样本的分类前提下让计算机自己进行分类，机器可以在数据中选出有相同特征的类/簇。
无监督学的相关算法叫聚类算法。
```
```
给你大量的数据，机器需要通过数据将数据分类这些类有着相同的结构特征
```
---

### 模型描述

```
课程用的是简单的一元线性回归说明的模型，
两个变量，两个参数一个方法：
变量一：输入（input，x）feature
变量二：输出（output,y,h(x))target
方法：在我的理解是映射课程中用的是假说/假设（hoyphisi算了拼不出来（>\/<))的条件下
用类似h(x)=a+bx的一次函数拟合数据的例子，其中a,b就是其中的参数，
要得到合适的函数a,b的取值很重要，但是更重要的方法，学会调参在我看来没有选择方法重要，可能工作中调参的情况更多。
这就是一个简单的模型
```

```
x是feature数据的特征
y是我们要达到的target
h是hypothesis
这里其实无监督学习某些时候已经达到目的了，之后不需要监督学习的过程了。纠正之前无监督学习是监督学习的前置过程的理解误区。
```
---

