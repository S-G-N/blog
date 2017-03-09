---
title: webpack
date: 2017-03-09 14:21:19
tags: 
---

# 简述
# 安装&环境
1. Node.js v0.6以上
2. npm全局安装 $ npm install webpack -g
3. 项目中使用本地安装的webpack npm install webpack --save-dev
4. webpack开发工具安装  npm install webpack-dev-server --save-dev

# 使用
1. 创建HTML文件和入口enter.js文件
2. 编译打包 enter.js文件到bundle.js文件  webpack entry.js bundle.js
webpack分析enter.js文件并将其包含和依赖的文件全部打包到bundl.js文件

# 资源转换loader
webpack只能处理js模块，loader是模块和资源的转换器，可以通过require加载任何类型模块和文件，如CoffeetScript、jsx、less、图片等。
1. 可以使用链式调用，最后一个loader必须返回js
2. 可以同步或异步执行
3. 运行环境 node.js
4. 支持传递参数
5. 支持通过正则或扩展名绑定给不同类型文件
6. 支持npm发布和安装
7. 可访问配置
8. 插件
9. 支持分发出附加的任意文件
10. 通常命名方式xxx-loader（引用时可用全名，也可配在 webpack 的 resolveLoader.moduleTemplates api 中定义【Default: ["*-webpack-loader", "*-web-loader", "*-loader", "*"]】后使用短名xxx）
11. loader使用
> 安装 npm install css-loader style-loader
> enter.js中引用 require("!style-loader!css-loader!./style.css") // 载入 style.css 【或将 entry.js 中的 require("!style!css!./style.css") 修改为 require("./style.css") ，然后执行：
$ webpack entry.js bundle.js --module-bind 'css=style-loader!css-loader'】

> 编辑style.css 
> 重新编译打包 $ webpack entry.js bundle.js

# 配置文件
默认搜索当前目录下--config.js（node.js模块），也可通过制定配置文件来执行
```javascript
{
  "name": "webpack-example",
  "version": "1.0.0",
  "description": "A simple webpack example.",
  "main": "bundle.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "webpack"
  ],
  "author": "zhaoda",
  "license": "MIT",
  "devDependencies": {
    "css-loader": "^0.21.0",
    "style-loader": "^0.13.0",
    "webpack": "^1.12.2"
  }
}
```
> 如果没有写入权限，请尝试如下代码更改权限
> chflags -R nouchg .
> sudo chmod  775 package.json
运行npm install 安装依赖

webpack.config.js中：
```javascript
// 加载packjson中配置的webpack参数中指定的依赖
var webpack = require('webpack')

module.exports = {
  entry: './entry.js',
  output: {
    path: __dirname,
    filename: 'bundle.js'
  },
  module: {
    loaders: [
    //简化了.css文件加载前缀
      {test: /\.css$/, loader: 'style-loader!css-loader'}
    ]
  }
}


```

# 插件
插件使用前需配置webpack.config.js的plugins
```javascript
module.exports = {
  entry: './entry.js',
  output: {
    path: __dirname,
    filename: 'bundle.js'
  },
  module: {
    loaders: [
      {test: /\.css$/, loader: 'style-loader!css-loader'}
    ]
  },
  plugins: [
    //打包后文件头部注释信息
    new webpack.BannerPlugin('This file is created by Cathy')
    //jquery插件配置
    new webpack.ProvidePlugin({
      jQuery: "jquery",
      $: "jquery"
    })
  ]
}
```

# 开发环境
1. 编译时显示进度和颜色 webpack --progress --colors
2. 热编译（监听模式，仅重新编译变化的模块） webpack --progress --colors --watch
3. 开发工具webpack-dev-server 启动一个express静态资源服务以监听模式运行webpack，实现热编译（存在内存中）和热刷新。
> 安装：
$ npm install webpack-dev-server -g
> 运行
$ webpack-dev-server --progress --colors


# 官方文档
http://webpack.github.io/docs/