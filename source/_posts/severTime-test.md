---
title: severTime-test
date: 2017-09-21 14:41:08
tags:
---
```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>设备像素比</title>
    <style>
        html{
            background: #fff;

        }
        p{
            color:#000;
        }
    </style>
</head>
<body>
<p id="devicePixelRatio"></p>
<p id="device-width"></p>
</body>
<script>
    document.getElementById('devicePixelRatio').innerHTML='本设备像素比 : '+window.devicePixelRatio;
    document.getElementById('device-width').innerHTML=" 屏幕分辨率的宽："+ window.screen.width+"<br/>"
    + " 屏幕分辨率的高："+ window.screen.height+"<br/>"
    + " 屏幕可用工作区宽度："+ window.screen.availWidth+"<br/>"
    + " 屏幕可用工作区高度："+ window.screen.availHeight+"<br/>"
    + " 屏幕设置是 "+ window.screen.colorDepth +" 位彩色"+"<br/>"
    + " 屏幕设置 "+ window.screen.deviceXDPI +" 像素/英寸"
    + " 屏幕availHeight "+ window.screen.availHeight
    + " 屏幕availWidth "+ window.screen.availWidth
</script>
</html>
```