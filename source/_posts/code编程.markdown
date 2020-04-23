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

#### 进制parseInt

````

['1', '2', '3'].map(parseInt) ( ); // [1, NaN, NaN]

// 解析：
['1', '2', '3'].map((item, index) => {
  return parseInt(item, index)
})
parseInt('1', 0) // 1,   0默认十进制  1x10^0 = 1
parseInt('2', 1) // NaN, 1进制  1不在（2 ~ 36）所以NaN
parseInt('3', 2) // NaN, 2进制  二进制当中没有"3"这个数码
补充：
parseInt('11',2); // 3,  2进制 1x2^0 + 1x2^1 = 3
parseInt('17',8); // 15, 8进制 7x8^0 + 1x8^1 = 15
parseInt('1f',16); // 31,16进制 15x16^0 + 1x16^1 = 31

````
> 解析1: parseInt
> 1、只有字符串中的第一个数字会被返回 ` parseInt(' 12abc!6') => 12 `
> 2、开头和结尾的空格是会被允许的 ` parseInt(' 12x') => 12 `
> 3、如果字符串的第一个字符不能被转换为数字，那么会返回 NaN  `parseInt('s12x') => NaN`
> 4、`parseInt(string, radix)`: 表示当前的字符串`string` 是以 `radix进制(2 ~ 36)`表示的

#### 浅拷贝

````

let a = { c:1 }  // a指向{ c:1 }的地址
let b = a        // 浅拷贝，仅仅指向a所在的地址
a = 1            // a变成了Number数据类型， 但是 { c:1 }的地址还是存在
b.c = 2          // 改变{c:1} 这个地址中c的值为2
a.c = (?)        // a中没有c这个变量了， undefined

````

#### js执行机制

````
console.log(1);

setTimeout(() => {
  console.log(2)
}, 0);

console.log(3);

Promise.resolve(4).then(b => {
  console.log(b);
});

console.log(5);

// 结果： 13542

````
> 解析1： 
> `console.log()` -> 同步
> `promise` -> 异步，微任务
> `setTimeout` ->  异步，宏任务
> 执行顺序: 同步 > 异步,微任务 > 异步，宏任务

#### 原型链

````

function setname(name){
 this.name = name
}

setname.prototype.printName = function(){ 
  console.log(this.name) 
}

let a = new setname("cc")
a.name = "dd"
a.__proto__.name = "ee"

a.__proto__.printName()  // ee
a.printName() // dd

````
> 解析1：
> 调用 new 方法`生成对象`传参 “cc” 此时a对象上面的name属性为cc
> 通过a.name`修改属性` 此时a对象的name属性为 dd
> 通过a.name`修改属性` 此时a对象的name属性为 dd
> 通过a `修改构造函数中的属性` --proto--