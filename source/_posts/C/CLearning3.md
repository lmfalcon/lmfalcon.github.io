---
title: CLearning3
date: 2019-08-30 15:55:01
tags: C
---

# 跨平台执行C

- int是整数类型便于跨平台执行

##  linux

### C文件

- gcc helloc.c	生成a.out文件
- ./a.out		执行a.out文件
- 用vi可以直接执行并生成helloc的可执行文件用	./helloc可以直接执行

### cpp文件

- g++ cpp.cc(c++的源文件.cc为后缀感觉好像和windows不一样啊) -o cpp.out
- ./cpp.out


### eclipse

- linux建议上使用

### codeblocks

- linux上建议使用

### Qt

- 可以多平台运行，找到了linux版的但是./***.run文件打不开，下次尝试安装，现在windows下运行吧
- android下运行C
```
#include<android/log.h>

int main(){
	__android_log-print(ANROID_LOGDEBUG,"itcast","输入你想输入内容");	//输出调试信息 itcast是头
	return 1
}

```

## android开发

- 先编写一个hello.c文件
- 之后编写Android.mk文件
```
LOCAL_PATH := $(call my-dir)
include $(CLEAR_VARS)
LOCAL_MODULE := hello
LOCAL_SRC_FILES := hello.c
LOCAL_LDLIBS	:= -1log
include $(BULID_EXECUABLE)
```
....不写了，没工具



