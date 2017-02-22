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