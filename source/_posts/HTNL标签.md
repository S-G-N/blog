---
title: HTNL标签
date: 2017-02-10 16:07:26
tags: technology
---
# mata标签
```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, minimum-scale=1, user-scalable=no">
```
    viewport指定用用户是否可缩放web页面，content值表示缩放参数：
    width、height：视区逻辑宽高（device- width标记可以指示视区宽度应为设备的屏幕宽度）
    user-scalable:指定用户是否可缩放视区值为yes允许，no禁止
    initial-scale指令用于设置Web页面的初始缩放比例，比例因终端设备而异，设为1.0则显示原始比例。
    maximum-scale和minimum-scale指令用于设置用户对Web页面缩放比例的限制。值的范围为0.25至10.0之间。


### 微信video标签视频设置全屏属性
```html
<video src="m.mp4" playsinline="true" webkit-playsinline="true" 
x-webkit-airplay="true" x5-video-player-type="h5" x5-video-orientation="h5" 
x5-video-player-fullscreen="true" preload="auto" style="object-fit:fill;"></video>
```
preload="auto"   开启视频缓冲，页面加载完即加载视频

webkit-playsinline="true"  控制当前视频在当前设置的div里面播放，不脱离文档流

x-webkit-airplay="true"  支持Airplay的设备

x5-video-player-type="h5"  开启同层播放器，取消播放器的默认的播放按钮和播放器控制器控制面板，整个页面只保留微信默认自带的返回和关闭菜单

x5-video-player-type="h5"  x5-video-player-fullscreen="true"  同层播放器设置类型为h5和设置视频播放为全屏幕

 style="object-fit:fill;" css3样式设置填充整个屏幕
    