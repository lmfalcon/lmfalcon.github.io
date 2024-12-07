---
title: git_to_remote
date: 2024-12-07 23:33:51
tags: git,hexo 
---

# 迁移hexo从旧电脑到新电脑

## github
在原有的分支上创建一个新的分支原有的分支是master

新的分支为hexo

之后将新的分支clone设置为默认分支default branch

## 旧电脑
clone新的分支到本地，这个步骤其实就是要里面的.git文件，其实可以通过git直接上传到这个分支的方式实现。
```
git clone ssh://git@ssh.github.com:443/lmfalcon/lmfalcon.github.io.git
下次访问限值22端口可以试试官方的443端口。
```

下载的文件夹里仅留下.git的文件夹，并复制到我们制作blog的文件夹中。

blog文件夹里增加.gitignore文件（就是设置不上传的文件，文件内容可以看看具体文件），不知道为啥里面原本就有这个文件。

如果原本的themes主题是clone下来的那么主题文件中可能有.git文件夹，如果有删掉。

```

git add .

git commit -m add_branch

git push
```
这里可以将文件推送到远程库分支hexo

其实新建一个仓库也是可以的，但是毕竟是一类放一起比较好。

后续文章的保存也是放到同一仓库，hexo分支即可。

hexo每次执行命令在git的命令行，执行完成后在vscode编辑，编辑完成后可以执行上面三个命令commit的内容修改一下即可。

hexo命令需要重新clean 并deploy

## 新电脑

clone 下来。新电脑需要改变的较多git，nodejs和npm淘宝源都需要重新设置

生成新的ssh key 后续过来完善这个部分，如果没有完善就搜索解决如何通过ssh上传的github。

新的blog文件夹下把clone的文件复制过来，之后

```
npm install hexo 
npm install
npm install hexo-deployer-git
hexo g
hexo s
hexo d
```

后续的步骤其实和旧电脑一样进行操作。其实新电脑的还没有尝试完。之后看效果吧


