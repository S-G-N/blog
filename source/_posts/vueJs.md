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
>boweserify-simple -拥有基础功能的Browserify + vueify 用于快速原型开发.
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
npm run dev
```
参考[这里](http://www.open-open.com/lib/view/open1476240930270.html#articleHeader1)


