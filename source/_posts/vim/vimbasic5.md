---
title: vimbasic5
date: 2019-07-31 14:22:50
tags: vim
---

# vim配置

## noremap

- 无递归配置使用<C-u> 将一个带有下划线单词改为全大写 并回到insertmode<Esc>viwU<Esc>i
- 通过手动配置vim比插件更容易记忆自己配置过什么，并且可以快速定位配置位置修改，注意使用noremap用于设置防止与插件冲突

## 编辑时修改vimrc

- 例子:nnoremap <leader>ev :vsplit $MYVIMRC<cr>	以上代码可以通过leader键加ev实现纵向分屏打开配置文件，并直接添加某个映射到vimrc文件中, 命令中的<cr>相当于回车等同于执行命令。
- 之后nnoremap <leader>sv :source $MYVIMRC<cr>	可以重读配置文件使刚刚的配置生效，按leader键加sv即可

## 自定义纠错

- :iabbrev mlfalcon lmfalcon  将错误的拼写改为正确的拼写
- 可以在insert，command，replace 三个模式下生效
- inoremap 会在任意时候更换错误拼写，而iabbrev 只会在前后字符非字母时进行替换

## localleader or leader

- localleader更适合做插件给他人使用的时候设置，这样具有更好的可移植性
- leader自己使用时设置就好了，这样自己可以熟悉使用leader按键。

## <buffer>

- nnoremap <buffer> <leader>x dd	这个设置只会在进行这个设置文件中生效其他文件不会拥有这个缓冲区，所以不会生效
- localleader 可以使用特定缓冲区
- 如果在一个文件的缓冲区设置了相同按键的两个指令一个有<buffer>另一个没有，结果只会执行有<buffer>的指令

## setlocal

- 这个命令只会在当前的文件生效
- 例如:setlocal nowrap 只会在当前文件不折叠

## autocmd

- 如果建立一个文件后未保存退出，vim默认不会帮你创建文件
- 修改方法 autocmd BufNewFile * :write 自动命令会自动执行，bufNewFile是创建新文件，*是任意文件名的通配符，：write 是写入保存。这个命令会在你创建文件时执行并保存
- autocmd BufWritePre *.html :normal gg=G 可以将BufWritePre 将在保存任何字符前触发:normal gg=G 将html文件的格式改为和第一行的相同，即所有行都没有缩进
- autocmd BufNewFile,BufRead *.html setlocal nowrap 这个命令的作用是将编辑html文件的换行取消。
- autocmd FileType javascript nnoremap <buffer> <localleader>c I//<Esc> 在处理javascript文件时将用localleader加ｃ注释掉当前光标所在行
- autocmd FileType Python nnoremap <buffer> <localleader>c I#<Esc>作用类似上面的注释方法

### 自动命令和缩写

- 自动命令搭配纠错可以通过缩写实现自动补全
- 例： autocmd FileType javascript :iabbrev <buffer> iff if:<left>autocmd FileType Python :iabbrev <buffer> iff if()<left>	这样就通过iff实现了自动补全功能

###　自动执行组

1. :augroup testgroup
2. :autocmd BufWrite * :echom "Foo"
3. :autocmd BufWrite * :echom "Bar"
4. :augroup END
- 顺序执行完上面步骤保存会打印Foo,但是不会打印Bar.如果继续在相同的组添加指令Bar也会出现，但是新指令不出现。
- 在组中添加:autocmd!后可以清楚之前创建的所有指令，但是这条指令后添加其他指令，其他的指令依然会执行，说明组仍存在未完全清除。只有单独添加:autocmd!才会清除整个组

## Operator-Pending映射

- 在normalmode下使用
- Operator 是操作
	- d 删除
	- c （change)修改
	- y 复制
- Movement 是移动范围
	- w		到下一个单词 
	- i(	i==inside，在括号内 
	- in(	移动到下一个(n==nex)t的括号内
	- il(	移动到上一个括号内，l==last
	- t,	到逗号
	- F)	向后移动到最近的）字符
	- vi(	进入可视模式选中括号内的所有内容
- 可以组合上面的O-M语句实验效果

### Movement 映射修改创建

- :onoremap p i( 将p改为进入括号中，normalmode中使用dp即可将括号内的语句删除
- :onoremap 自定义按键 /希望搜索的字符
- 
