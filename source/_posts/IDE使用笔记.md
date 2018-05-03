---
title: IDE使用笔记
date: 2017-02-06 15:39:02
tags: tools
---
# WebStorm2016.3 激活
在激活框，选择 License server， 输入：http://idea.imsxm.com/
或者 http://idea.iteblog.com/key.php
# webstom
## 缩进设置：
![Alt title](/images/tab1.png)
![Alt title](/images/tab2.png)

## 自定义代码模板
1. Ctrl+Shift+A查找设置live
2. 设置>Editor>Live Template
3. 选择语言 编辑模板 添加应用场景
![Alt title](/images/IDE1.png)

## webpack在webatom上热更新
webstrom settings的system settings默认勾选‘safewrite’,勾选去掉。


mac terminal 补齐功能
在命令行输入nano .inputrc
进入.inputrc的编辑界面，输入如下语句：
set completion-ignore-case on set show-all-if-ambiguous on TAB: menu-complete
Control+O保存。重启terminal即生效
