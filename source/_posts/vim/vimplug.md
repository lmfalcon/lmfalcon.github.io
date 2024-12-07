---
title: vimplug
date: 2019-07-30 18:34:55
tags: vim, vimplug
---

# vim插件

## vim的插件管理工具vim-plug

- github上搜索可找到安装
- 安装后github上还有具体的配置方法
- 修改好.vimrc后即可使用
- 添加插件	plug '插件名称'
- 保存配置文件,:source .vim/vimrc使用配置
- 保存配置文件后还是要重启vim编辑器才能安装插件
- :PlugInstall 安装插件，等待安装完成重启

## vim插件搜索方法

- Google
- https://vimawesome.com/
- 网上搜索别人的开源配置借鉴别人的插件

## YouCompleteMe

### 安装

- vim-plug安装
	- 之前安装好github上需求的cmake和python支持
	- Plug'/ycm-core/YouCompleteMe' 
	- PlugInstall等待，建议提前安装阿里的镜像goproxy，否则会安装失败。安装失败要到下面的目录删除文件夹重新安装
	- cd ~/.vim/plugged/YouCompleteMe/
	- python3 install.py --clang-completer
	- 安装完成，但是仍不能补全c
	- 以下是添加c的补全支持方法，由于插件管理器我用的是vim-plug所以应该全部替换为上方的地址
	- 下方引用blog地址为[引用的blog](https://www.cnblogs.com/alinh/p/6699789.html)
```
7、接着再次打开 .vimrc 配置YCM，添加内容如下：

filetype off                  " required!
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
Plugin 'Valloric/YouCompleteMe'
filetype plugin indent on     " required!
let g:ycm_global_ycm_extra_conf='~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp/ycm/.ycm_extra_conf.py'

　　注：
8、为了补全，我们还需要在 .ycm_extra_conf.py 文件中进行配置，vim ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp/ycm/.ycm_extra_conf.py；添加信息如下：

'-isystem',
'/usr/include',
'-isystem',
'/usr/include/c++/4.8.4',
'-isystem',
'/usr/include/c++/4.9.2',
'-isystem',
'/usr/include',
'/usr/include/x86_64-linux-gnu/c++',

　　实际上以上是vim自动补全时搜索路径，如果自动补全的内容位于/usr/local/include里面，则添加以下信息：
'-isystem',
'/usr/local/include',

　　根据实际的/usr/include/c++/中的文件夹名称(即C++版本号)修改：

'-isystem',
'/usr/include/c++/4.8.4',
'-isystem',
'/usr/include/c++/4.9.2',
```
- 发现markdown内仍不能使用这个插件	
```
"vimrc增加以下配置（把markdown从中移除了）
let g:ycm_filetype_blacklist = {
        \ 'tagbar': 1,
        \ 'notes': 1,
        \ 'netrw': 1,
        \ 'unite': 1,
        \ 'text': 1,
        \ 'vimwiki': 1,
        \ 'pandoc': 1,
        \ 'infolog': 1,
        \ 'mail': 1
        \}
```
- 发现markdown中仍不能补全其他语言的代码。查youcompleteme需要在.md文件用vim查看时输入:set ft=你想不全的语言的后缀（ft=filetype),保存也不会改变后缀，所以放心改咯！
