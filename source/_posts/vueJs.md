---
title: vueJs
date: 2017-01-11 13:54:11
tags: Frame
---

# vue.js的探索初衷

# 模板
```code
{{mag}} //数据更新模板变化
{{*mag}} //数据只绑定一次，更新模板不变化
{{{msg}}} //数据更新模板变化，HTML转移输出
```
<!-- more --> 

# 过滤器（过滤模板数据）
```code
单过滤器：{{msg|filterA}}
多过滤器：{{msg|filterA|filterB}}

lowercase 小写
uppercase 大写
capitalize 首字母大写
currency 货币
eg:
{{"welcome"|uppercase}}//输出WELCOME
{{"WELCOME"|lowercase|uppercase}}//输出Welcome
{{12|currency}}//输出$12.00
{{12|currency "￥"}}//输出￥12.00
```
# 交互
angular ：$http
vuejs:vue-resource

当script引用了vew-resource,new Vue 实例对象即绑定了一个方法 

```html
<body>
<div id="div">
    <input type="button" value="点击获取数据" @click="get()"/>
</div>

</body>

```
以此控件实现点击交互案例，分别用GET、POST、JSONP实现：
## get
1. 获取一个普通文本数据
```bash
window.onload=function () {
        new Vue({
            el:"#div",
            data:{

            },
            methods:{
                get:function () {
                    this.$http.get('data.txt').then(function (res) {
                    //.then(successFUN，failFUN)延迟
                        alert(res.data);
                    }),function (res) {
                       alert(res.status);
                        //res.status失败返回状的态码
                    }
                }
            }
        });//new vue
    };//onload
</script>
```
2. 给服务器发数据
```bash
window.onload=function () {
        new Vue({
            el:"#div",
            data:{

            },
            methods:{
                get:function () {
                //.get(server,param)
                    this.$http.get('data.php',{a:1,b:2}).then(function (res) {
                        alert(res.data);
                    }),function (res) {
                       alert(res.status);
                    }
                }
            }
        });//new vue
    };//onload
</script>
```
## post
```bash
 new Vue({
            el:"#div",
            data:{

            },
            methods:{
                get:function () {
                //post(server,param,{emulateJSON:true})
                    this.$http.post('post.php',{
                        a:1,b:20
                    },{emulateJSON:true}).then(function (res) {
                        alert(res.data);
                    }),function (res) {
                        console.log(res.status);

                    }
                }
            }
        });//new vue
```
## jsonP (跨域访问)
实现步骤：
1.打开好搜网页，输入a ,f12 捕获接口地址
https://sug.so.360.cn/suggest?callback=suggest_so&word=a
```bash
  /*********************json********************/
        new Vue({
            el:"#div",
            data:{

            },
            methods:{
                get:function () {
                    this.$http.jsonp('https://sug.so.360.cn/suggest',{
                        word:"a"  //关键字
                    },{
                        emulateJSON:true
                    }).then(function (res) {
                        alert(res.data.s);
                        console.log(res.data);
                    }),function (res) {
                        console.log(res.status);

                    }
                }
            }
        });//new vue
    };//onload
```
![接口图片](/images/jiekou.png)

## 事件
```bash
v-on:click=""
等同@click
```
## 事件对象
```bash
@click="show($event)"
```
## 事件冒泡
### 阻止冒泡：
1)原生： ev.consolebuble
2)vue： @click.stop=""
### 默认行为
1) 原生：ev.preventDefault()
2) vue: @contextmenu.prevent="show()"
例：
```js
new Vue =({
    el:"#box",
    data:{},
    methods:{
        show:function(ev){
        ev.preventDefault();
        alert(1);
        }
    }
})

```
```html
<div id='box'>
<input type="button" value="按钮" @contextmenu="show($event)">
</div>

```
### 键盘事件
1) 原生：ev.keyCode==13
2) vue: @keydown.13="show()"
        @keydown.enter="show()"
        @keydown.up="show()"
        @keydown.down="show()"
        @keydown.left="show()"
        @keydown.right="show()"
        @keydown.delete="show()"
常用键简写：
    13是键码


## 属性

v-bind:src 绑定属性 不用加{{}}
简写为 :src
例：
```js
new Vue =({
    el:"#box",
    data:{
        url:'https://ss0.bdstatic.com/5aV1bjqh_Q23odCf/static/superman/img/logo/bd_logo1_31bdc765.png'
    },
    methods:{
        }
})

```
```html
<div id='box'>
<img src="{{url}}" alt=a">//图片正常显示，<vue报错404></vue报错404>推荐下面方法
<img v-bind:src="url" alt=a">
</div>

```

## class
class不能用以上方法，class用法如下：
法一：
class为data数据
```js
new Vue =({
    el:"#box",
    data:{
       r:"red",
       b:"blue"  
    },
    methods:{
        }
})

```
```html
<div :class="[r,b]"></div>
```
法二：
class为类名
```css
.r{
color: red;
}
.b{
background-color: blue;
}
```
```html
<div :class="{r:true,b:false}"></div>
//:class等于一个json
```

## style
:style='[c,b]'
style等于一个json
```bash
c:{color:'red'},
b:{backgroundColor:'blue'}
//驼峰
```


# 创建一个vue项目的过程

## 搭建环境（Vue2.0）
### git安装
### nodejs安装（npm：Node.js包管理工具）
参考[git随记](/2016/10/13/git随记/ "node安装")
### webpack（解析.vue,并翻译打包成js文件）
```bash
npm install webpack -g
```
### vue-cli (生成模板的vue工程，vue的命令行工具)
```bash
npm install vue-cli -g
```
#### 官方模板
[vuejs-templates](https://github.com/vuejs-templates):
>boweserify -拥有高级功能的Browserify + vueify 用于正式开发.
>oweserify-simple -拥有基础功能的Browserify + vueify 用于快速原型开发.
>webpack -拥有高级功能的Webpack + vue-loader 用于正式开发.
>webpack -拥有基础功能的Webpack + vue-loader 用于快速原型开发开发.
```bash
vue init 模板名 项目名
```
#### 自定义模板
可以自定义并托管然后用vue-cli直接拉取
```bash
vue init username/repo my-project
```
## 初始化项目
```bash
vue init webpack-simple 项目名字 //英文小写
npm install //安装依赖（官方镜像）
```
关于镜像切换请参考[git随记/](/2016/10/13/git随记/ "nrm")这篇文章
## 安装vue路由模块vue-router和网络请求模块vue-resource
```bash
npm install vue-router vue-resource --save
```
## 启动项目
```bash
npm run dev //热加载方式运行，代码修改，浏览器自动刷新。实质上npm run dev 命令中“run”对应的是package.json文件中，scripts字段中的dev，也就是 node build/dev-server.js命令的一个快捷方式。
```
本文参考[这里](http://blog.csdn.net/u013182762/article/details/53021374)


## 项目目录



## 单文件组件的三大组成部分
### template
```html
<template>
    <div id="app">
        <img src="./assets/logo.png">
        <router-view></router-view>
    </div>
</template>
```
template下只能有一个根节点

### style
    组件的样式，可以用css的预处理器sass或者less，需要安装这些依赖包和设置狼属性，项目运行时style会生成style标签插入到html的head标签中，若组件没有样式则不要写style，否则也会生成一个空的style标签插入到html的head中。
     style设置scoped属相后，当前组件中的样式class即使与其他组件中class重名也不会相互影响。
![script图解](/images/vue_1.jpg)
### script
    实现组件功能代码。
 
    
    
### 路由
vue主要开发单页面应用，没有页面之间跳转，全部靠路由实现（vue-router自带两个组件router-view和router-link）使用vue-router控制路由则必须router-view作为容器。router-link有一个to属性，其属性值是目标路由，在运行项目的时候，router-link表现为a标签，to属性则表现为a标签的href属性
#### 单页面应用（APS）优缺点：
优点：
1. 分离前后端关注点，前端负责界面显示，后端负责数据存储和计算
2. 减轻服务器压力，服务器只负责出数据，不管展示逻辑和页面合成，吞吐能力提高
3. 一套后台支持多中客户端
4. 具有桌面应用及时性、网站可移植性和可访问性
5. 用户体验好，单页面应用为用户提供了更接近一个本地移动或桌面应用程序的体验
缺点：
1. 不利于SEO，可以通过Prerender等技术解决一部分
2. 前进后退地址栏需要程序进行管理
3. 首次加载耗时，一旦加载和执行单个页面应用程序通常会有更多的响应，这就需要返回到后端Web服务器

# webstom设置vue文件模板
setting>editor>file and code template
```bash
<template>
    <div id="app">

    </div>
</template>

<script type="text/ecmascript-6">
    export default {};
</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
```

# eslint 语法
1. 字符串使用单引号
2. 冒号后加空格
3. 文件结尾加空行（Newline required at end of file but not found
）
# 问题
## npm run dev 报错
有可能8080端口被占用，运行netstat -aon|findstr "8080"查看PID，运次tasklist|findstr PID 查看对应进程，关闭进程
## 接口访问
当修改了dev-srever.js时（node文件修改后需重新编译），需要重新启动服务npm run dev
## webpack配置文件修改后或eslint配置修改后不会触发热更新，需手动重启服务

# css sticky footer

# 内容滚动
容器需设置overflow: auto，否则不滚动

# postCss
根据官网can i use 
# ios背景模糊
backdrop-filter: blur(10px)
# 图片背景模糊
filter: blur(5px)


# better-scroll地址
https://github.com/ustbhuangyi/better-scroll

# 居中
```css 

.menu-item
                display: table
                width: 56px
                height:54px;
                padding: 0px 12px
                line-height: 14px
                border-1px(rgba(7, 17, 21, 0.1))
                &.current
                    position: relative;
                    margin-top: -1px
                    background-color: #fff
                    z-index:10
                    font-weight: 700
                    .text
                        border-1pxOFF()
                .text
                    display:table-cell
                    vertical-align: middle
                    font-size: 12px
                    font-weight: 200
                    line-height: 14px

```
# v-el
v-el:foods-wrapper
 this.$els.foodWrapper获取不到dom
使用this.$el.querySelector('.foods-wrapper')

# 发布服务器

安装服务器
$ npm install webpack-dev-server -g
$ webpack-dev-server --progress --colors
服务器可以自动生成和刷新，修改代码保存后自动更新画面
http://localhost:8080/webpack-dev-server/bundle





# sell项目在海信上拿不到数据
这里使用了vue插件vue-resource，其中有一个方法是用来发起http请求的，
```js
 this.$http.get('http://192.168.20.83:7000/data').then((res) => {
                console.log(res.body);//返回的数据类型为blob
                this.seller = res;
                console.log(this.seller);//object
    })
```    
### 测试1（请求外部服务器）
'http://192.168.20.83:7000/data'这里是在本地用node开启的服务，脚本如下：
```javascript
/**
 * Created by user on 2017/3/2.
 */
var express = require('express');
var cors = require('cors');
var bodyParser = require('body-parser');
var fs = require('fs');
var app = express();

app.use(cors());
app.use(bodyParser.urlencoded({extended: false}));
app.use(bodyParser.json());

const PORT = 7000;

app.listen(PORT, function() {
    init();
    console.log('Server listening on port %s', PORT);
});

const JSON_HEADER = {
    'Content-Type': 'application',
};
var data;
function init() {
    data = fs.readFileSync('./data.json', 'utf8');
}

app.get('/', function(req, res) {
    res.writeHead(200, JSON_HEADER);
    res.end(data);
});


```
请求脚本：
1. jquery ajax请求
测试浏览器chrome56.0.2924.87及opera12.16
```javascript
 $.ajax({
                type: 'get',
                url: 'http://192.168.20.83:7000',
                success: function(data) {
                    console.log(data);//返回blob
                    console.log(typeof data);//返回string
                }
            });
```
使用jquery ajax请求外部服务器，在两测试browers返回了string,通过对数据处理，可以再页面上渲染数据，处理步骤如下：
```javascript
    //striing->json
    //或在ajax里加dataType: 'json',
    var res = JSON.parse(data);
    //res.goods是一个普通数组
    console.log(res.goods);
    var goods = res.goods;
    for (let i in goods) {
        //将数组每一项转化为vue对象属性，使其拥有get和set刚方法
        vm.goods.$set(i, res.goods[i]);
    }
```
2. vue-resource请求
```javascript
 this.$http.get('http://192.168.20.83:7000').then((res) => {
                  console.log(res);//object
                  console.log(typeof res);//string
            });
```

使用vue-resource请求外部服务器，在两测试browers返回了Blob，所以均无法渲染数据,两浏览器返回object如下：
![Alt title](/images/vue_http1.png)


### 测试2（请求本地文件）
```javascript
  this.$http.get('/api/goods').then((res) => {
                console.log(res);//blob
                console.log(res.body);//chrome:Object{};opera12.16:blob
            });
```
使用vue-resource请求本地文件，在两测试browers返回了Object，但Object内容不同，
chrome 中body值为返回的json，但opera中body为blob类型，chrome中应用请求到的数据得到渲染，但opera中应用没有数据如图：
![Alt title](/images/vue_http2.png)

```javascript
    
```

# mixin
织入模式就是一些提供能够被一个或者一组子类简单继承功能的类,意在重用其功能。

# click事件不触发
使用 v-on:keyup.13.stop.prevent="addCart($event)


# 常见编程习惯
> 组件内部调用的方法一般命名格式为：_funName
> 组件外部调用的方法一般命名格式为：funName
> 
> vue中只有绑定属性里用-，其他用驼峰