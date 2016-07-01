+++
categories = ["技术"]
date = "2016-07-01T16:38:07+08:00"
Description = "Git 常用命令介绍 "
tags = ["git"]
title = "Git 常用命令介绍  Git Command"

+++

Git由于其灵活 速度快 离线工作等特点而倍受青睐,下面一步步来总结下git的基本命令和常用操作

### 1、检出仓库
远程克隆

	git clone <server>
	git clone https://github.com/klj123wan/blog.konglingjian.com.git

### 2、创建仓库	
创建一个本地的local repository

	git init
	
### 3、local changes

查看哪些文件存在差异性.执行add、commit操作之前和之后最好都要查看下当前提交的一些状态信息,防止漏添加,错提交.

	git status

查看和对比修改的内容

	git diff 
	git diff <filename>
	
添加工作区(working dir)新的或改动的文件到暂存区(Index或stage)

	git add .  提交所有(不建议使用)
	git add -p <filename>
	
文件重命名 

	git mv <filename> <new filename>
	
删除文件 添加到下次commit

	git rm <filename>

提交到当前分支master HEAD区

	git commit -m "提交信息"
	
### 4、Commit History  

查看提交记录

	git log   
	git log -p <filename>	

从暂存区删除添加或改动的的文件

	git rm --cached <filename>
	
### 5、branchs 分支
 
查看所有branch  当前分支

	git branch -a   
	git branch   

切换分支

	git checkout <branch>

创建分支

	git branch <branch>
	
删除本地分支  和 删除远程分支

	git branch -d <branch>
	git push origin --delete <branch>
	
合并指定分支到当前分支
	
	git merge <branch>
	
### 6、更新 发布
查看远程信息

	git remote -v
	
从远程获取最新版本到本地仓库,并自动merge到本地分支

	git pull origin master | <branch>
	
推送到远端仓库

	git push origin master | <branch>

### 7、标签 (可以理解为版本库的快照)
创建标签
	
	git tag <tagname>

还可以创建带有说明的标签,用-a指定标签名,-m指定说明文字

	git tag -a v1.1 -m "version 1.1 released" 3628164
	
查看标签
	
	git tag


查看标签信息

	git show v1.0


删除本地标签

	git tag -d v1.1


推送标签到远程

	git push origin <tagname>


一次性推送全部未推送的标签

	git push origin --tags


删除远程标签(先删除本地,再删除对应的远程tag)

	git tag -d v1.1
	git push origin :refs/tags/v1.1
	
### 8、多人协作的工作模式

* 首先,先用 git pull试图合并
* 如果合并有冲突,则解决冲突,并在本地提交
* 随后 git push origin <branch>推送自己的修改

### 9、git工作流程图
说了这么多,来张工作图,可能更加通俗易懂

![](/img/291705321847415.png)



掌握上面的命令后基本上可以轻松使用git来管理项目和参与团队开发了,当你欣赏到git的过人和可爱之处后,你可能再也不想使用svn来管理代码了,妈妈也不用担心我如何使用git了,熟悉操作后你就可以遨翔于github、gitcafe、gitlab的天空,为开源生态圈贡献自己的一份力量.

引用:   http://hcy2367.github.io/2014/12/29/git-usage.html

