---
title: git随记
date: 2016-10-13 09:39:30
tags:
---

```bash
//1.当前处于fixbug分支：
git add .
git commit -m ''
git push origin fixbug
//2.切换到master分支，合并fixbug，解决冲突，创建标签，提交到远程
git checkout master
git merge fixbug
    //resolve conflict
git add .
git commit -m ''
git tag -a 0.1.1 -m 'release version 0.1.1'
git push origin master
git push origin --tag
//3.切换到develop分支，合并fixbug，解决冲突，创建标签，提交到远程
git checkout develop
git merge fixbug
    //resolve conflict
git add .
git commit -m ''
git push origin master
```