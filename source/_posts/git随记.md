---
title: git随记
date: 2016-10-13 09:39:30
tags:
---


# 标签应用
```bash
//1.当前处于fixbug分支：
git add .
git commit -m ''
git push origin fixbug
//2.切换到master分支，合并fixbug，解决冲突，创建标签，提交到远程
git checkout master
git merge --no-ff fixbugname
    //resolve conflict
git add .
git commit -m ''
git tag -a v0.1.1 -m 'release version 0.1.1'
git push origin master
git push origin --tags
//3.切换到develop分支，合并fixbug，解决冲突，创建标签，提交到远程
git checkout develop
git merge fixbug
    //resolve conflict
git add .
git commit -m ''
git push origin master

//删除标签的命令
git tag -d 0.1.3
//删除远端服务器的标签
git push origin :refs/tags/0.1.3
```
# 分支应用

```bash
//1. 切换到master，创建本地分支
git branch branchName
//2. 推到远程
git push origin branchName
//3.
//
```
# 账户设置
设置Git的user name和email：
```bash
$ git config --global user.name "xuhaiyan"
$ git config --global user.email "haiyan.xu.vip@gmail.com"
```
# 生成SSH密钥
1.查看是否已经有了ssh密钥：cd ~/.ssh
2.生成密钥：
```bash
$ ssh-keygen -t rsa
```
# 

# git 忽略文件
1. 项目根目录下创建 .gitignore文件
```bash
vim .gitignore
```
2. .gitignore中添加忽略文件或目录
.gitignore中#代表注释
```bash
# 忽略*.o和*.a文件，一般这类对象文件和存档文件都是编译过程中出现的，我们用不着跟踪它们的版本
 *.[oa]
# 忽略*.b和*.B文件，my.b除外
*.[bB]
!my.b
# 忽略dbg文件和dbg目录
dbg
# 只忽略dbg目录，不忽略dbg文件
dbg/
# 只忽略dbg文件，不忽略dbg目录
dbg
!dbg/
# 只忽略当前目录下的dbg文件和目录，子目录的dbg不在忽略范围内
/dbg
# 忽略所有以波浪符（~）结尾的文件，许多文本编辑软件（比如 Emacs）都用这样的文件名保存副本。
*~
```
以上方法是当.gitignore还没有被提交到仓库的情况下，如果已经被提交，使用如下方法：
先清除缓存中的'要取消跟踪的目录'
```bash
git rm -r --cached '要取消跟踪的目录'
git commit -m'提交缓存'
```
然后修改.gitignore文件




















