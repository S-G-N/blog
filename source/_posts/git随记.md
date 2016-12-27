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
git merge --no-ff fixbug
    //resolve conflict
git add .
git commit -m ''
git tag -a 0.1.1 -m 'release version 0.1.1'
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