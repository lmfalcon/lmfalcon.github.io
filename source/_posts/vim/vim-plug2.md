---
title: vim-plug2
date: 2019-09-02 20:49:37
tags: plugin,vim,vim-plug
---

# markdown-preview插件系列

- 折腾了很久发现可以用了，但是还是有一些问题
	1. 只能在根目录下使用，而我绝大部分的编辑是在hexo中编辑blog
	2. 不能进入报错，某个rpc的依赖插件打不开
- 解决方案
	1. 换个插件
	2. 安装instant-markdown-d发现这些插件都有相同的问题在hexo中无法编辑bolg
	3. 发现我编辑的blog都是root用户的因为我每次打开都是sudo vim，但是这些插件打开浏览器firefox是我登录用户的，所以打不开。
	4. 当然我尝试了以下直接用firefox打开markdown，firefox安装了markdown文件的显示插件和自动重载页面，代码如下（改的vimrc文件）
	```
	nnoremap <leader>t :call Preview() <CR>
	func! Preview()
		if &filetype == 'markdown' ||  &filetype == 'md'
			exec "firefox %"
		endif
	endfunc
	```
	5. 运行报错Running Firefox as root in a regular user's session is not supported。我估计那两个插件没有料到我会遇到这样的问题，毕竟是浏览器打不开插件运行是正常的。
	6. 只能改掉blog目录下所有文件的拥有者
	```
	chown -R 我的用户名 blog目录
	```
	7. 重新进入可以使用了，一切恢复正常


# vim-plug插件管理器问题

- 大部分插件是可以直接安装的但是第一次安装失败后退出安装界面，再进入就显示安装完成了
- 怀疑是不是只检测是否有这个文件目录就算安装了插件
- 解决办法
	1. 最有效的方式是
	```
	删除或者注释掉.vimrc中未安装成功的插件相关的内容
	执行:PlugClean清除插件（可能清除失败，目录没删掉）
	因为我用的是vim所以目录为~/.vim/plugged/中，删掉文件夹即可
	之后重新安装依赖或者重新安装
	```
	2. 直接找到依赖包安装，说不定插件是安装好的只是少依赖再或者就如markdown-preview中的问题，插件安装成功依赖也是完整的，只是用户组问题这样的bug插件本身无法检测也无任何报错导致插件打不开。（文档读着都累，而且markdown-preview还不知道怎么查文档的我，一步步慢慢试水分析原因浪费了大量时间）
	3. 依赖安装不成功很可能是依赖的环境变量没有设置好或者只是局部变量没办法在全局引用中查找到（所以安装中 -g 很重要）。再或者就是我之前的问题root用户和自己的用户在vim中未作区分，导致有些无法执行。有些就算区分了在vim中也没办法执行,下面的方法我用了之后可以在vim中使用firefox了，但是对插件你仍不知道去哪里改插件问题
	```	
	nnoremap <leader>t :call Preview() <CR>
	func! Preview()
		if &filetype == 'markdown' ||  &filetype == 'md'
			exec "!sudo -u lmfalcon firefox %"
		endif
	endfunc
	```
	
