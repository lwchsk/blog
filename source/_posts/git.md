---
title: git简易教程
tags:
  - 参考
  - 教程
---

**这里贴一篇文章**https://blog.csdn.net/qq_55106682/article/details/122038284
```
idea中安装git以后，代码文件出现了不同的颜色  
它们分别表示的含义：

绿色，已经加入控制暂未提交  
红色，未加入版本控制  
蓝色，加入，已提交，有改动  
白色，加入，已提交，无改动  
灰色：版本控制已忽略文件。
```

```
1、工作区
包含.gt文件夹的目录，主要用存放开发的代码
2、仓库
分为本地仓库和远程仓库，本地仓库是自己电脑上的gt仓库(gt文件夹)；远程仓库是在远程服务器上的gt仓库
gt文件夹无需我们进行操作，只需要执行相关命令即可。
3、暂存区
git文件夹中有很多文件，其中有一个index文件就是暂存区
```
## .gitignore
避免某些文件被上传到远程仓库，避免敏感信息
```

```

## 冲突
### 撤销操作
```
### `git reset`

`git reset` 是一个用于重置当前分支的命令。它可以改变 HEAD 的位置和工作目录的状态，具有多种模式（soft、mixed、hard）。它通常用于撤销提交或修改分支的历史。

### `--hard`

`--hard` 是 `git reset` 命令的一个选项，表示强制重置工作目录和索引。具体效果如下：

- **HEAD** 将被重置到指定的提交（在这个例子中是 `ORIG_HEAD`）。
- **索引**（暂存区）将被重置到匹配 HEAD 的状态。
- **工作目录** 将被重置到匹配 HEAD 的状态，即所有的本地修改都会被丢弃。

### `ORIG_HEAD`

`ORIG_HEAD` 是 Git 中的一个特殊引用。它通常指向上一次重大的操作（如 `git pull`、`git merge` 或 `git rebase`）之前的 HEAD 状态。在执行这些操作时，Git 会自动将之前的 HEAD 状态保存到 `ORIG_HEAD`，以便在必要时能够恢复。

### 综合解释

`git reset --hard ORIG_HEAD` 这个命令的作用是：

- 将当前分支的 HEAD 重置到 `ORIG_HEAD` 指向的提交。
- 同时将索引和工作目录也重置到 `ORIG_HEAD` 指向的提交的状态。

这意味着所有在 `git pull` 之后的更改（包括合并引入的更改）都会被丢弃，你的工作目录会回到 `git pull` 之前的状态。
```
### 分支
远程推送被拒绝
远程删除了东西，本地还原了
### 合并分支

## 远程
添加存储库
```
git remote add <name>
```

显示存储库列表
```
git remote
```

创建分支并推送
```
git push <repository> <refspec>
```
## 分支
增删改查
创建分支
```
git branch <branchname>
```
#### 分支命令
二、分支管理
```
1、列出所有本地分支
git branch
2、列出所有远程分支
git branch -r
3、列出所有本地分支和远程分支
git branch -a
4、建一个分支，并停留在当前分支
git branch[分支名]
5、建一个分支，并切换到该分支
git checkout-b[分支名]
或
git switch-e[分支名]
6、建一个分支，与指定的远程分支进行关联
git branch-track[本地分支名][远程分支名]
7、现有分支与指定的远程分支之间建立追踪关系
7、现有分支与指定的远程分支之间建立追踪关系
ait branch-set-upstream[本地分支名][远程分支名]
8、切换到指定分支
git checkout[分支名]
或
git switch[分支名]
9、切换到上一个分支
sit checkout
10、重命名分支
git branch-m[I旧分支名][新分支名]
11、合并带指定分支到当前分支
git merge[分支名]
12、选择某个commit,合并进当前分支
ait cherry-pick [commitID]
sit show [commitId]
commitld可以通过git log命令淡取
13、删除本地分支
git branch-d[本地分支名]
14、删除远程分支
git push origin-delete[远程分支名]
```
#### 创建仓库
二、从本地仓库提交代码到远程仓库
```
一)在当前工作目录中初始化新仓库
1、初始化本地仓库
git init
2、添动加文件到本地暂存区中
git add.
3、提交暂存区到本地仓库
git commit-m"提交说明”
4、连接远程仓库
git remote add origin仓率地址
5、提交之前洗pu川
it pul1 origin远程分支名：本地分支名
如果远程分支是与当前分支合并，则冒号后面的部分可以首路
git pul1 origin分支名
6、提交到远程仓库
git push origin本地分支名：远程分支名
如果本地分支名与远程分支名相同，则可以首路冒号
git push origin分支名
强制推送可以使用-force参数
git push-force origin分支名
```
### git版本控制
如何回退到上一个版本
1. idea控制
2. git命令控制 git reset --hard ff6d8f39f1fc964a0099ff3dd7abdf7f1ea1efab
#### 问题
1.
```
github文件夹显示白色箭头并且不能打开。
原来是因为这个文件夹里面有.git隐藏文件，github就将他视为一个子系统模块了。
解决办法就是：
1、删除文件夹里面的.git文件夹
2、执行git rm --cached[文件夹名]
3、执行git add文件夹名]
4、执行git commitQ-m"msg"
5、执行git push origin[branch_name]
```
2.
```
IDEA提示的git警告
可以通过以下命令在Git中设置core.autocrlf以确保在所有存储库中都使用正确的行分隔符:
git config --global core.autocrlf true
```
3.git中文乱码问题
![[Pasted image 20240618222106.png]]
git复制粘贴问题
![[Pasted image 20240618222929.png]]
第一行和最后一行跟默认相反
4.
```
! [remote rejected] master -> master (push declined due to email privacy restrictions)
[贴个地址](https://blog.csdn.net/qq_26819733/article/details/78374129)
```
命令提示符上面的用户名修改
![[Pasted image 20240618223432.png]]