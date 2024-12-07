---
title: wirelessproblem
date: 2019-08-21 22:37:57
tags: wifi, hard_block,airplane_mode
---

# 问题描述

打开电脑发现无法联无线网，使用以下命令检查：
```
ifconfig -a
```
1. 发现两个接口：eno1和lo,并没有发现无线网卡
2. 退出Ubuntu系统，进入win10依旧未发现无线网卡，怀疑无线网卡损坏。
3. 外出购买内置无线网卡rtl8723be
	- 安装后win10系统默认关闭wifi，睡眠后开启wifi接口可打开，重启后又关闭。尝试用笔记本默认硬件开关F12和fn+ F12，只能切换飞行模式和wifi，但是wifi仍处于关闭状态
	- Ubuntu系统处于飞行模式并且显示wifi硬件开关关闭。尝试笔记本默认wifi硬件开关，按键无效或终端输入~符号。
4. ubuntu系统下尝试下列命令解决问题
```
rfkill list
```
显示 soft blocked no
hard blocked yes
说明硬件开关阻塞
```
rfkill unblock all
rfkill list
```
未造成任何改变，此方法仅适合与开关软件阻塞
尝试挂起系统解决问题
```
sudo pm-suspend
```
找不到pm命令，连接网线，通过有线网络下载pm
```
sudo apt install pm
```
断开有线网络
```
sudo pm-suspend
```
回车唤起系统，发现wifi正常使用。
但是每次开机后挂起很麻烦，所以寻找其他解决办法
```
sudo modprobe -r rtl8723be
sudo modprobe rtl8723be
```
尝试开闭模块重新激活，失败
```
sudo vim /etc/modprobe.d/blacklist.conf
最后增加
blacklist hp-wmi
....
等一系列网上方法
```
失败，重启后问题仍无法解决
```
github上更新rtl系列网卡驱动
依照README提示安装相关的kernel部件
git clone ....
cd 克隆的文件夹
make
make install
sudo modprobe -r rtl8723be
sudo modprobe rtl8723be
sudo vim /etc/modprobe.d/rtl8723be.conf
	依照网上配置
```
原来可以链接的wifi显示连接失败，需要激活
重启后问题未得到解决
```
进入clone的文件夹
sudo make uninstall
```
卸载后重启可以通过挂起联网

---

# 问题解决方案

- 只有通过挂起解决
- 熟悉特别linux系统前不打算再尝试解决这个问题
- 已购买原相同无线内置网卡尝试解决问题
- 下次ubuntu系统不要使用rtl（瑞昱系列的网卡）
- 熟悉使用以下linux命令
```
sudo pm-suspend 系统挂起
rfkill list	无线设备列表
rfkill unblock all	不阻塞所有
rfkill block all	阻塞所有
ifconfig -a	查看所有端口
sudo lshw -C Network	查看无线设备
sudo lsmod	查看在用模块
sudo modprobe 修改在用模块
make	make install	make uninstall		编译式的安装和卸载
git clone 的使用

/etc/modprobe.d/下的文件的修改
blacklist.conf	用于增加黑名单模块，防止开机启动
```

---

# 仍存在问题

- 不能直接开启
- 挂起后不稳定，一定时间后掉线



