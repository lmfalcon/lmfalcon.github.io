---
title: network2
date: 2019-09-15 12:16:53
tags: network 
---

# 物理层基本概念

- 解决在各种计算机传输媒体上传输数据比特流
- 主要任务描述为确定与传输媒体接口的一些特性

|特性|举例|
|---|---|
|机械特性|接口形状大小，引线数目|
|电气特性|规定电压范围|
|功能特性|规定-5V表示0,5V表示1|
|过程特性|规定建立连接时各个相关部件工作的步骤|

## 数据通信的基础知识

### 典型的数据通信模型

1. PC机将文字转换为数字比特流
2. 调制解调器将数字比特流转换为模拟信号
3. 模拟信号传入公共电话网到达目标调制解调器下
4. 调制解调器将模拟信号转换回数字比特流
5. 目标PC机将数字比特流转换为显示汉字

### 几个概念解析

模拟信号：代表消息的参数的取值是连续的

数字信号：代表消息的参数的取值是离散的

码元code：在使用时间域的波形表示数字信号时，则代表不同离散数值的基本波形就成为码元。

在数字通信中常常使用时间间隔相同的符号来表示一个二进制数字，这样的时间间隔内的信号成为二进制的码元。而这个间隔的长度被称为码元长度。1码元可以携带nbit的信息量。

### 信道的几个基本概念

信道一般表示向一个方向传送信息的媒体，所以平常的通信路线往往包含一条发送信息的信道和一条接受信息的信道

单向通信（单工通信）——只能有一个方向的通信而没有反方向的交互。
- 电视
- 广播

双向交替通信（半双工通信）——通信的双方都可以发送信息，但不能同时发送（也不能同时接收）
- 对讲机

双向同时通信（全双工通信）——通信双方可以同时发送和接收信息


### 基带（baseband）信号和带通(band pass)信号

基带信号（基本频带信号）——来自信源的信号。发出的直接表达要传输信息的信号。传播距离较近，远距离失真。

带通信号——把基带信号经过载波调制后，把信号的频率范围搬移到较高的频段以便在信道中传输（即仅在一段频率范围内能够通过信道）。 远距传播减少信号衰减。


### 调制方法

- 调幅（AM）
- 调频（FM）
- 调相（PM）


### 常用编码

- 单极性不归零码（高电压1，没电压0）
- 双极性不归零码（正负电平分别表01，正负值相等）
- 双极性归零码（正负零三个电平，信号本身携带同步信息）
- 曼彻斯特编码（相同单位时间，由低到高代表0，由高到低代表1，必须经过两次采样才能得到1bit数据。可携带时钟信号，可以表示没信号传输）
- 差分曼彻斯特编码（bit中间有信号跳变，bit与bit之间也有信号跳变，表示下一个bit为0。bit中间有信号跳变，bit与bit之间无信号跳变，表示下一个bit为1。性能与曼彻斯特编码相同，抗干扰能力强）


### 信道的极限容量

实际信道传输中带宽受限，有噪声，干扰，失真，可能发生信号的波形变化。
- 有失真可识别
- 不可识别


### 奈氏准则

- 作用：假定理想状态下，为了避免码间串扰，码元的传输速率的上限值。
- 原因：任何信道中，码元传输的速率是用上限的，否则就会出现码间串扰的问题，使接收端对码元的判决（即识别）成为不可能。
- 理想低通信道的最高码元传输速率=2WBaud
	- W是理想低通信道的带宽，单位Hz
	- Baud是波特，是码元传输速率的单位。如果一个码元含有3个bit信息量，1波特=3bit/s


### 信噪比

香农用信息论的理论推导出了带宽受限且有高斯白噪声干扰的信道的极限，无差错的信息传输速率。

信道的极限信息传输速率C= Wlog2(1+S/N)   单位b/s
- W 为信道的带宽（Hz）
- S 为信道内所传信号的平均功率
- N 为信道内部的高斯噪声功率
- 上面的公式是香农公式

其中的C不可能无限大，因为N不可能很小
S/N 为信噪比

### 奈氏准则和香农公式适用范围

-------> 源点--------->发送器--------->传输系统-------->接收器------->终点------>
输入信息　　输入数据　　发送信号　　　接收信号  　　输出数据　 输出信息

发送信号到接收信号的过程码元传输速率受奈氏准则的限制

输入数据到输出数据之间信息传输速率受香农公式限制

## 传输媒体

### 电磁波

### 导向传播媒体

#### 双绞线

- 屏蔽双绞线STP
- 非屏蔽双绞线UTP


#### 同轴电缆

- 50Ω 用于数字传输
- 75Ω 用于模拟传输

#### 光纤

- 单模光纤 
- 多模光纤

### 非导向传输媒体

#### 短波通信

- 依靠电离层反射

#### 微波通信

- 直线传播
- 依靠卫星和地面信号塔


### 集线器

- 有放大信号的作用和重发作用
- 半双通
- 有冲突域
- 不安全
- 数量越多带宽越少

### 信道复用技术

#### 频分复用

- 每个用户固定频率
- 不同频率调制
- 信号复用
- 传输完成后拆分


#### 时分复用

- 每个设备设定时间段
- 按顺序收按顺序发
- 缺点：可能有空数据
 
 
#### 统计时分复用

- 不同用户用不同标记


#### 波分复用 

#### 码分复用

- 简称 CDMA
- 频率相同的信号都可以接收，但是不同用户使用不同的码型不会干扰
- 码片：每一个比特时间划分为m个短的间隔
- 利用正交向量的规则，保证格式化内积值只有1,-1,0。且无关码片的值一定是0


### 数字传输系统

- 电话局之间的中继线上传送多路的电话
- 脉码调制PCM
	- 北美T1
	- 欧洲E1


### 宽带接入技术

#### xDSL

- 用不同频率传不同的信号
- 低频给电话
- 高频留给上网


#### 光纤同轴混合网HFC

#### FTTx技术

- 光纤到户


