---
title: nginx.md
date: 2016-12-26 09:37:46
tags: server
---
# Note For Learning nginx
## 邮件传输协议
1. POP3 (Post office Protocol 3)邮局协议第三个版本
规定个人计算机连接到Internet的邮件服务器和下载电子邮件协议，因特网上第一个离线协议标准，允许用户下载服务器上的邮件并删除服务器上的邮件。允许用户在客户端操作邮件但不会反馈到服务器上。POP3更易丢失邮件或多次下载相同的邮件。
2. IMAP （Internet Mail Access Protocol）交互式邮件存取协议，提供webmail与电子邮件客户端之间的双向通信，客户端操作会反馈到服务器上，支持下载，更好的支持在不同设备中随时访问新邮件。
3. SMTP （Simple Mail Transfer Protoco）简单邮件传输协议，一组用于从源地址到目的地址传输规范，通过他来控制邮件的中转方式，SMTP 协议属于 TCP/IP 协议簇，它帮助每台计算机在发送或中转信件时找到下一个目的地，SMTP 认证的目的是为了使用户避免受到垃圾邮件的侵扰。


## 什么是nginx
服务器软件之一，发布程序功能，实现负载均衡（分担服务器压力），代理邮件服务器；
> IIS只能运行在windows上
> Tomcat 面向Java，重量级
> nginx 轻量级 跨平台 支持百万级TCP链接 十万以上并发链接（高并发）部署简单 内存消耗少 成本低 rewrite功能不够强大 没有Apache模块多
> apache 稳定 开源 跨平台 不支持高并发
## linux系统下安装
1. 官网下载
2. 解压 tar -zxvf
3. ./cinfigure
常见错误1
error: C compiler cc is not found
c++未安装
解决：root权限，根目录下安转c++
```bash
yun -y install gcc-c++ autoconf automake
```