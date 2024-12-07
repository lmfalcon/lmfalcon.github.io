---
title: vimbasic2
date: 2019-07-27 14:12:48
tags: vim
---

# vim配置

## .vimrc配置文件更改

- map 按键1 按键2 
- 特殊按键要<space>，组合键<C-d>
- 对应三个模式下的映射(不推荐)
	- nmap normal
	- imap insert
	- vmap visual
- 上种映射存在冲突可能，以下方式较好
	- nnoremap
	- inoremap
	- vnoremap
- " 表示注释，配置最好做好注释防止忘记对应功能
- 设置leader键
	- let mapleader = "," 常用逗号或者空格
- noremap 按键1 按键2	将按键一改为按键二
- map S :w<CR>			将大写S改为一键保存,CR表示Command模式
- map Q :q<CR>			将大写Q改为一键退出
- map R :source $MYVIMRC<CR> 一键修改设置
- syntax on				语法高亮 
- set number or nonuber		更改是否显示行号
- set norelativenumber	or relativenuber 更改行号是否关联
- map s <nop> 取消s按键在命令模式下替换功能
- set cursorline	下划线显示所编辑行
- set wrap			
- set showcmd		
- set wildmenu		自动补全命令
- set pastetoggle=<F2> F2进入粘贴模式
- set hlsearch	设置高亮搜索
- set foldmethod=indent	设置折叠方式
- "一些方便的映射
	- let mapleader=','
	- let g:mapleader= ','
- inoremap jj <Esc>`^	使用jj进入normal模式
- "使用leader+ w 直接保存（感觉还是大写S好用，但是vim中w是保存为了养成习惯一定要强迫自己使用leader键加w来保存）
	- inoremap <leader>w <Esc>:w<cr>
	- noremap <leader>w :w<cr>
- "切换buffer
	- nnoremap <silent> [b :bprevious<CR>
	- nnoremap <silent> [n :bnext<CR>
-"use ctrl+hjkl switch window
	- noremap <C-h> <C-w>h
	- noremap <C-j> <C-w>j
	- noremap <C-k> <C-w>k
	- noremap <C-l> <C-w>l
- "使用:h option-list 来看配置的各个符号具体功能
- "sudo to write
	- cnoremap w!! w !sudo tee % >/dev/null
- " json 格式化
	- com! FormatJSON %!python3 -m json.tool
- 笨方法学Vimscript 百度搜索电子书来看，里面有详细的配置方法

## 分屏设置

- <c-w> 用于分屏<C-w>表示Ctrl + w,不能直接分屏，只用于切换
- <c-w>w 用于分屏间的切换
- <c-w>l 用于分屏间互换位置
- <c-w>= 用于分屏,所有窗口等高
- <c-w>_ 用于分屏,当前窗口最大化活动高度
- [N]<c-w> 用于分屏,高度设为N
- [N]<c-w>l 用于分屏,纵向高度设为N
- :sp 横向分屏
- :vs 纵向分屏

## 标签页设置

- :h tabpage了解tap的相关用法，相当于设置工作区，全部用于存储同一文件类型
- :tabnew 用于打开新的工作区
- gt 用于不同的工作区之间的切换

