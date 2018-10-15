---
title: git随记
date: 2016-10-13 09:39:30
tags: tools
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
//获取远程tag
git fetch origin tag tag_name
// 删除远程tag
V1.1
git push origin --delete tag V1.1 
//删除标签的命令
git tag -d 0.1.3
//删除远端服务器的标签
git push origin :refs/tags/0.1.3
//删除远程分支
git push --delete origin 分支名
// 
```
<!-- more -->
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

# node 安装
1. 官网下载安装（npm已经集成其中）
2. 配置环境变量 
NPM_HOME  C:\Program Files\nodejs\node_modules\npm
NVM_SYMLINK   C:\Program Files\nodejs
3. GIT BUSH:
node -v
npm -v

# npm 
```bash
//切换镜像源
npm install -g nrm 
nrm ls
nrm test //测试速度
nrm use cnpm //指定使用的镜像源
```
```bash
//增加镜像源
nrm add <registry> <url> [home]
//删除镜像源
nrm del <registry>
```
https://segmentfault.com/a/1190000000368906
## 安装Vue-Cli开发模板
这个模板可以快速生成vuejs的运行配置环境,可以使新手快速免除配置搭建出运行界面
```bash
npm install -g vue-cli
```

## npm 更新自身版本
```bash
npm install -g npm //更新到最新版本
```

## node 版本更新
node的n模块专门用来管理node.js版本，安装n模块如下：
```bash
npm list //列出已经安装的模块
npm show express //显示模块详情
npm install -g n //安装n
n stable //升级node.js到最新稳定版
//或后面跟版本号
n v0.10.26
npm update  //升级当前目录下的项目的所有模块
npm update express    //升级当前目录下的项目的指定模块
 
npm update -g express  //升级全局安装的express模块
 
npm uninstall express  //删除指定的模块
```



/**
 * Created by suguannan on 2018/4/23 9:45.
 *
 */
import {OPENCHANNELS} from 'common/consts'
export function platform() {
    var json = {
        userAgent: navigator.userAgent.toLowerCase(),
        isAndroid: Boolean(navigator.userAgent.match(/android/ig)),
        isIphone: Boolean(navigator.userAgent.match(/iphone|ipod/ig)),
        isIpad: Boolean(navigator.userAgent.match(/ipad/ig)),
        isMobile: Boolean(navigator.userAgent.match(/Mobile/ig)),
        isWeChat: Boolean(navigator.userAgent.match(/MicroMessenger/ig)),
        isFacebook: Boolean(navigator.userAgent.match(/FB/ig)),
        isTwitter: Boolean(navigator.userAgent.match(/twitter/ig)),
        isSamsung: Boolean(navigator.userAgent.match(/samsung/ig)),
        isChrome: Boolean(navigator.userAgent.match(/chrome/ig) || navigator.userAgent.match(/crios/ig)),
        isSafari: Boolean(navigator.userAgent.match(/safari/ig))
    }
    return json
}
export function isPCOrPad() {
    if (platform().isMobile && !platform().isIpad) {
        return false
    } else {
        return true
    }
}
export function openChannels() {
    if (!platform().isMobile || platform().isIpad) {
        return OPENCHANNELS.PCPad
    } else if (platform().isWeChat) {
        return OPENCHANNELS.WECHAT
    } else if (platform().isFacebook) {
        return OPENCHANNELS.FACEBOOK
    } else if (platform().isTwitter) {
        return OPENCHANNELS.TWITTER
    } else if (platform().isSamsung) {
        return OPENCHANNELS.SAMSUNG
    } else if (platform().isChrome) {
        return OPENCHANNELS.CHROME
    } else if (platform().isSafari) {
        return OPENCHANNELS.SAFARI
    }
}







