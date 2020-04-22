---
layout:     mark
title:      "code编程"
subtitle:   "Whether:sunny / Mood:am-normal, pm-normal / Especially:0"
date:       2020-04-22 14:24:00
author:     "lsm"
catalog:    true
header-img: "/img/banner2.jpg"
tags:
    - 前端开发
    - 语法
    - HTML/CSS
---

#### 闭包和引用类型对象
````
function Foo() {
    var i = 0;
    return function() {
        console.log(i++);
    }
}
 
var f1 = Foo(),
    f2 = Foo();
f1(); // 0 
f1(); // 1
f2(); // 0

````

> 解析1： i++ : 相当于 x = i+1,  先将 x = i = 0, 再 i++ 即 i = 1
> 解析2： 闭包形成， 变量就不会被销毁， 所以说闭包有延续变量作用域的功能。

#### 局部作用域和参数

````
var bb = 1;
function aa(bb) {
  bb = 2;
  alert(bb);
};
aa(bb); // 2
alert(bb); // 1

````

> 解析1： 函数声明的时候，带了一个参数bb，相当于在函数体内声明了var bb。所以，函数里的bb就是函数活动对象的属性
