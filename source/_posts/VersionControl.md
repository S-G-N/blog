---
title: VersionControl
date: 2018-05-25 10:36:11
tags:
---
## 波浪符号（~）
更新到当前minor version中最新的版本。

## 插入符号（^）
更新到当前major version中最新的版本。

## 总结
~1.15.2 :=  >=1.15.2 <1.16.0     

^3.3.4 := >=3.3.4 <4.0.0



## minor verision & major version：

    1.  15 .2
MAJOR.MINOR.PATCH

MAJOR：这个版本号变化了表示有了一个不可以和上个版本兼容的大更改。

MINOR：这个版本号变化了表示有了增加了新的功能，并且可以向后兼容。

PATCH：这个版本号变化了表示修复了bug，并且可以向后兼容。

因为major version变化表示可能会影响之前版本的兼容性，所以无论是波浪符号还是插入符号都不会自动去修改major version，因为这可能导致程序crush，可能需要手动修改代码。