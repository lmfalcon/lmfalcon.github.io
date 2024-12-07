---
title: ideaIDE
date: 2019-08-11 21:47:05
tags: idea
---

# idea配置

## idea安装位置

- /usr/local/idea/


## idea配置文件

- /usr/local/idea/bin/idea.vmoptions文件
- 文件可以改变idea的运存缓存等信息


## idea的启动文件

- /usr/local/idea/bin/idea.sh文件
- 快速打开可以将  sudo ln -s /idea安装目录/bin/idea.sh /usr/bin/ 这样就可以在命令行启动idea


## idea的家目录下配置文件

- 第一次启动后会在~/.IdeaIC20XX.X文件夹，里面有两个文件夹
	- config 中记录了在idea的部分setting中的用户配置
	- system 中记录了缓存，编译，日志，框架等用户配置信息
- config 中也有idea64.vmoptions文件，建议修改这个文件，加快idea运行速度。


# idea项目位置

- ~/IdeaProjects/
- 类似于eclipse中的workspaces
- 新建java项目后会多出项目的文件夹

## src文件夹

- 随项目建立，存放包和java文件


## out文件夹

- 随着项目运行建立，存放编译好的class文件


# idea的插件

## ideavim

- 默认在插件列表了，安装即可
- 配置文件存放在~/.ideavimrc
	- 可以设置leader键，但是不能使用插件
- 重启进入idea生效配置后使用vim编辑器，建议还是多设置写commandmode的leader快捷键，这样可以将编辑的影响降到最低
- :actionlist可以查看vim能设置的idea相关快捷键
- 设置方法nnoremap <leader>gc :action GotoClass<CR>


# idea快捷键

- 可以设置成类似eclipse的快捷键，当然还是有一部分会不一样。我还是决定是适应新快捷键
- 设置位置setting中的keymap

## 有时间再补快捷键列表


# idea模板

- 插入文档注释
	- Setting 中的File and Code Templates中设置
- Setting 中的Live Templateplates中设置简写补全模板
	- main 补全public static void main(String[] args){
	- sout 补全System.out.println()
	- 可以自己设置
