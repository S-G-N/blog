---
title: markdown学习记录
date: 2016-09-21 11:03:44
tags: 
---
## markdown语法
### 1.斜体
 *这是斜体效果,书写格式：*
 ```bash 
 *内容*
 ```
### 2.加粗 
 **这是加粗效果，书写格式：**
```bash
**内容**
```
### 3.特殊样式 
`这是特殊样式，书写格式：`
```bash
	内容
```

### 4.列表

* 这是无序列表1
* 这是无序列表2
* 书写格式：
```bash
* 列表1
* 列表2
 ```
1. 这是有序列表效果
2. 这时有序列表效果
3. 书写格式：
```bash
1. 列表1
2. 列表2
3. 列表3
 ```
'1.''2.''3.'数字可以不按顺序

### 5.引用
 > 这是引用效果
 ```bash
 >内容
 ```
 `*`等同于`+``-`


### 6.标题
 这是最高阶标题效果
 ===============
 这是第二阶标题效果
 ---------------
 ```bash
 标题
 ======
 标题
 ------
 ```
 `=`和`-`个数任意

### 7.类Atx形式标题
 # 一级标题效果
 ## 二级标题效果
 ### 三级标题效果
 ```bash
 # 一级标题
 ## 二级标题
 ### 三级标题
 ```
1-6个#分别对应1-6级

### 8.代码区块
	这是一个代码区块
	做到这样个效果只需要4个空格或1个制表符

### 9.分割线
用三个以上`*`、`-`、`_`建立分割线，中间不可插入其他内容,效果如下：
*****
```bash
***
----
_____
```
### 10.链接
> 行内链接效果：
请移步 [百度](http://baidu.com/ "baidu")
Title可以省略，链接到同样主机资源可以使用相对路径
```bash
	请移步 [百度](http://baidu.com/ "baidu")
```
参考式链接效果：
I get 10 times more traffic from [Google] （） than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"


```bash
I get 10 times more traffic from [Google] （） than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"<a href="dfasdf">sadf</a>
```