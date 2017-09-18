---
title: ECMA6
date: 2017-09-18 14:49:45
tags:
---
"use strict";
  
# let 块级里有效

# 恒量声明以后就不能再重复定义，但是可以添加值不能改变他的值 

# 解构数组
```bash
function breakfast()
{
    return ["cake", "tea", "fruit"]
};
let [ds, dr, fr] = breakfast();
console.log(ds, dr, fr)
```
# 解构对象
```bash
function lunch()
{
    return {ds: "cake", dr: "tea", fr: "fruit"}
};
let {ds: ds, dr: dr, fr: fr} = lunch();
console.log(ds, dr, fr)
```
# 模板字符串
```bash
let eat = 'bread',
    drink = 'coffe'
let dinner = `今天的晚饭是${eat}和${drink}`
console.log(dinner)
```
# 带标签的模板字符串
```bash
let eat = 'bread',
    drink = 'coffe'
let dinner = kitchen`今天的晚饭是\n${eat}和${drink}!`
console.log(dinner)

function kitchen(string, ...values) {
    console.log(string);
    console.log(values);
    let result = ''
    for (var i = 0; i < values.length; i++) {
        result += string[i]
        result += values[i]
    }
    result += string[string.length - 1]
    return result
}

console.log(dinner);
```
# 判断字符串是否包含其他字符串
```bash
let eat = 'bread',
    drink = 'coffe'
let dinner = `今天的晚饭是\n${eat}和${drink}!`
console.log(dinner.startsWith('今天'));
console.log(dinner.endsWith('今天'));
console.log(dinner.includes('今天'));
```
# 默认参数
```bash
function breakfast(dessert='cake',drink='tea') {
return `${dessert} ${drink}`
}

console.log(breakfast());
console.log(breakfast('甜甜圈','啤酒'));
```
# 展开操作符： ...
```bash
// spread
// let fruits = ['apple', 'Kiwi'],
//     foods = ['bread', 'cake', ...fruits]
// console.log(fruits);
// console.log(...fruits);
// console.log(foods);
// console.log(...foods);

// rest 剩余操作符
// function breakfast( dessert, drink ,...foods) {
//     console.log(dessert, drink ,foods)
//     console.log(dessert, drink ,...foods)
// }
// // 剩余将放进foods里
// breakfast('cake', 'bread','apple', 'Kiwi')
```

# 解构参数
```bash
// function breakfast( dessert, drink ,{location,restaurant}) {
//     console.log(dessert, drink ,location,restaurant)
// }
// // 剩余将放进foods里
// breakfast('cake', 'bread', {location: 'Beijing', restaurant: '东来顺'})
```


# 函数名字
```bash
// let breakfast = function (argument) {
//
// }
// let lunch = function superLunch(argument) {
//
// }
// function dinner(argument) {
//
// }
// console.log(breakfast.name)
// console.log(lunch.name)
// console.log(dinner.name)
```
# 箭头函数
```bash
let breakfast = dessert => dessert
let dinner = (dessert, food, drink) => dessert + food + drink
let lunch = (dessert, food, drink) => {
    return dessert + food + drink
}

// 命令行运行
// babel index.js --watch --out-file index-compile.js
//编译结果：
// var breakfast = function breakfast (dessert) {
//     return dessert
// }
// var dinner = function dinner (dessert,food, drink) {
//     return dessert + food + drink
// }
// var lunch = function lunch (dessert,food, drink) {
//     return dessert + food + drink
// }

    ```
# 对象表达式
```bash
let dessert = 'cake', drink = 'coffee';
let food = {
    dessert: dessert,
    drink,// 可以直接写变量名
    breakfast: function () {},
    lunch() {} // : function 可直接去掉
};
```
# 对象属性名
```bash
let food ={}
let Chinese = 'hot pot'
food.dessert = 'cake'; // 直接点属性
food['hot drink'] = 'tea'; // 带空格的属性用['']
food[Chinese] = 'tea'; // [] 中可用变量
```
# 对比两个值
```bash
console.log(+0 == -0)// true
console.log(+0 === -0)// true
console.log(NaN === NaN)//false
console.log(Object.is(NaN, NaN))// true
console.log(Object.is(+0, -0))// true
```

# 把一个对象复制到另一个对象里
```bash
let breakfast = {};
Object.assign(
    breakfast,
    {drink: 'milk'}
)

console.log(breakfast)
```


# 设置对象的prototype
```bash
let breakfast = {
    getDrink(){
        return 'milk'
    }
}
let dinner = {
    getDrink(){
        return 'tea'
    }
}

let Sunday = object.create(breakfast);
console.log(Sunday.getDrink()); // milk
console.log(Object.getPrototypeOf(Sunday) === breakfast); // true

Object.setPropertyof(Sunday, dinner);
console.log(Sunday.getDrink()); // tea
console.log(Object.getPrototypeOf(Sunday) === dinner); // true
```


#  __proto__
```bash
let breakfast = {
    getDrink(){
        return 'milk'
    }
}
let dinner = {
    getDrink(){
        return 'tea'
    }
}

let Sunday = {
    __proto__: breakfast
}

console.log(Sunday.getDrink());// milk
console.log(Object.getPrototypeOf(Sunday) === breakfast); //true

Sunday.__proto__ = dinner;
console.log(Sunday.getDrink());// tea
console.log(Object.getPrototypeOf(Sunday) === dinner); //true
```

# super
```bash
let breakfast = {
    getDrink(){
        return 'milk'
    }
}
let dinner = {
    getDrink(){
        return 'tea'
    }
}

let Sunday = {
    __proto__: breakfast,
    getDrink(){
        return super.getDrink() + "tea"//执行一下breakfast里的getDrink()方法,在进行其他操作
    }
}
```
# 迭代器 Iterators
```bash
{value: XX, done: true/false}
XX: 返回值
done:表示还有没有可迭代的东西,没有是true,表示完成迭代
next 没有可迭代的时候next的值就是undefind

function chef(foods) {
    let i = 0;
    return {
        next(){
            let done = (i >= foods.length)
            let value = !done ? foods[i++] : undefined
            return {
                value:value,
                done: done
            }
        }
    }
}

let wanghao = chef(['tomato','eggs'])
console.log(wanghao.next())
console.log(wanghao.next())
console.log(wanghao.next())
```

# 生成器
```bash
function* chef () {
    yield 'tomato';
    yield 'eggs';
}

let wanghao = chef()

console.log(wanghao.next())
console.log(wanghao.next())
console.log(wanghao.next())


// 改造
function* chef (foods) {
   for (var i = 0; i < foods.length; i++) {
       yield foods[i];
   }
}

let wanghao = chef(['tomato', 'eggs'])

console.log(wanghao.next())
console.log(wanghao.next())
console.log(wanghao.next())
```
# class 类
```bash
class Chef{
    constructor(food) {
        this.food = food;
    }

    cook() {
        console.log(this.food);
    }
}

let wanghao = new Chef('tomato')
wanghao.cook()
```
# get 与set
```bash
class Chef{
    constructor(food) {
        this.food = food;
        this.dish = []
    }
    get menu(){
        return this.dish
    }
    set menu(dish){
        this.dish.push(dish)
    }
}

let wanghao = new Chef()

console.log(wanghao.menu);
console.log(wanghao.menu = 'tomato');
console.log(wanghao.menu = ['bread', 'milk']);
console.log(wanghao.menu);
```


# 静态方法
```bash
// 静态方法就是不需要实例化类就能使用的方法

class Chef{
    constructor(food) {
        this.food = food;
        this.dish = []
    }
    get menu(){
        return this.dish
    }
    set menu(dish){
        this.dish.push(dish)
    }
    static cook(food) {
        console.log(food);
    }
}
Chef.cook('tomato')
```

# 继承 extends
```bash
class Person {
    constructor(name, birthday) {
        this.name = name;
        this.birthday = birthday;
    }
    intro(){
        return `${this.name},${this.birthday}`;
    }
}
class Chef extends Person{
    constructor(name, birthday) {
        super(name, birthday)
    }
}

let wanghao = new Chef('wanghao', '1984-02-01')

console.log(wanghao.intro());
```


# set
```bash
let dessert = new Set(['ice cream', 'cake', 'muffin'])

dessert.add('bread');
console.log(dessert);
console.log(dessert.size);
console.log(dessert.has('ice cream'));
dessert.delete('ice cream')
console.log(dessert);
dessert.forEach(dessert => {
    console.log(dessert);
});
dessert.clear();
console.log(dessert);
```

# map
```bash
let food = new Map();
let fruit =[], cook = function () {}, dessert ='甜点', drink = 'tea'
food.set(fruit,'lemmon')
food.set(cook,'forkAndKnife')
food.set(dessert,'doughnut')

console.log(food);
console.log(food.size);
console.log(food.get(fruit));
console.log(food.get(cook));
console.log(food.get(drink));

console.log(food.has(dessert))
food.forEach((value, key) => {
    console.log(`${key} = ${value}`)
})
food.delete(dessert)
food.clear()
console.log(food);
```

# nodule 模块
```bash
// 导出导入重命名
let fruit = 'Kiwi'
export {fruit as food}
export default {fruit as food}// 默认导出


import {fruit} from '../../user.........'
import {food sa dinner} from '../../user.........'
```





















