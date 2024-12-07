---
title: vimbasic6
date: 2019-08-03 21:27:43
tags: vim
---

# vim插件

## nerdtree

- 目录插件
- github搜索获取
- leaderev+Plug 'github目录'
- leadersv+PlugInstall
- 开vim自启动,autocmd vimenter * NERDTree
- 开关目录快捷键设置nnoremap <leader>n :NERDTreeTOggle<CR>
- 打开文件所在目录位置 快捷键设置为 <leader>f :NERDTreeFind<cr>

## vim-markdown插件

- 折叠相关
	- zo打开
	- zc关闭
	- zR解开全部折叠

## easymotion插件

- 功能快速跳转
- 快捷键ss
- 搜索之后光标快速移动到指定位置，相较于vim本身的斜杠更好用
- ss功能只能搜索到显示能看到的地方，不知道为啥，但是可以用来快速定位光标到所见未知也是不错的

## ctrlp插件

- 快捷键ctrlp模糊搜索文件

## instant-markdown

- 这个用不了，npm安装后，配置文件中找不到要用的插件位置

## vimsurround 更改成对出现的符号

- cs 将成对符号更改
	- 例 cs'" 将单引号改为双引号
- ys 
	- 例 ysiw" 将这个单词加双引号 
- ds
	- 例 ds"  删除双引号
- 安装过程
	- github搜索安装即可，同上

## fzf.vim模糊搜索

- [fzf.vim](https://github.com/junegunn/fzf.vim) 参考官方文档的command
- 常用命令
	- Ag[PATTERN]模糊搜索字符串,这个功能不会用！
	- Files[PATH]模糊搜索目录

## far.vim搜索替换插件

- :Far 被替换词 替换词 \\**/* 
	- \\**表示上层目录所有文件类型
	- \\*表示当前目录所有文件类型
	- 回车后会生成预览文件，没问题就可以替换
- 预览文件没问题需要执行Fardo命令进行替换

## vim-go

- 已经预装了，所以没有装，但是这台linux上没有golang的运行环境需要自己安装

## python-mode打造轻量级PythonIDE

- 需要注意的是安装库可能会花些时间
- :help pymode 查询帮助信息,注意设置了打开文件类型，只有Python文件才可以打开插件


- Support Python version 2.6+ and 3.2+
- Syntax highlighting
- Virtualenv support
- Run python code (<leader>r)-    
- Add/remove breakpoints (<leader>b)-    
- Improved Python indentation-     
- Python motions and operators (]], 3[[, ]]M, vaC, viM, daC, ciM, ...)-    
- Improved Python folding-     
- Run multiple code checkers simultaneously (:PymodeLint)-    
- Autofix PEP8 errors (:PymodeLintAuto)-    
- Search in python documentation (<leader>K)-    
- Code refactoring-    
- Intellisense code-completion-     
- Go to definition (<C-c>g)-    
- And more, more ...- - 

## vim tagbar

- 安装前需要先安装ctag
- 同样的插件github安装
- 更改配置文件快速切换
	- nnoremap <leader>tb :TagbarToggle<CR>

## vim-interestingwords

- 高亮单词
- 找到需要高亮的单词<leader>k,全文高亮需要单词
- <leader>K,用于高亮需要单词

## deoplete.nvim

- 实现代码补全功能
- <C-xo>代码补全 

## coc.vim

- 实现代码补全未安装，但是推荐说是很好用


## 代码格式检查

- 自动格式化
- 静态检查

### Neoformat 

- 这个插件有问题啊，没办法格式化，就算安装autopep8，也没办法格式化python代码

### vim-autoformat

- 相较于Neoformat这个更好用，刚开始也出现了无法使用的问题，解决方法不用pip安装autopep8，改用sudo apt install python-autopep8 
- 上面的Neoformat用了之后可以使用，但是有些缩进仍不规范

### 静态检查

- neomake
- ale
	- 可以参考官方文档自定义检查功能，让报的错少些


## 快速注释

- vim-commentary
	- gcc使用
	- gcgc取消
	-多行也是gc注释和取消

## git相关插件

### Fugitive

- 在vim里使用git

### vim-gitgutter

- 显示git文件变动

### gv.vim

- 查看命令行git项目提交记录
- :GV 即可打开gitbrowser



