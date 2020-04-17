---
layout:     post
title:      "Object"
subtitle:   "Whether:sunny / Mood:am-normal, pm-normal / Especially:0"
date:       2020-04-17 14:09:00
author:     "lsm"
catalog:    true
header-img: "post-bg-js-module.jpg"
tags:
    - 前端开发
    - 语法
---
#### 1 Object.assign()

将两个对象合并，返回新的对象。在产生冲突的时候后者的属性会覆盖前者。属于浅拷贝

```javascript
let obj = { name: '1' , age: '2' }
let obj1 = { name: '2' , age: '3' }
let obj2 = { title: 'sss' }
let objNew = Object.assign(obj, obj1)
console.log(objNew) // {name: "2", age: "3"}
let objNew1 = Object.assign(obj, obj1, obj2) // {name: "2", age: "3", title: "sss"}
```

#### 2 Object.create()

已对象为原型创建新的对象，第一个参数为原型对象，第二个参数为新描述符属性对象。

```javascript
let obj = {
    a: "a",
    b:"b"
};

let nobj = Object.create(obj, {
    name: {
        value: 42,
        writable: true,
        enumerable: true,
        configurable: true
    }
})
console.log(nobj)// { name: 42 }
```

#### 3 Object.seal()

封装对象，封装的对象无法增删属性，可以修改属性 Object.isSealed() 判断对象是否被封装

```javascript
var obj = {a: 1}
Object.seal(obj)
obj.b = 'el'
delete obj.a
console.log(obj) // { a: 1 }
obj.a = 2 
console.log(obj) // { a: 2 }
```

#### 4 Object.is()

判断两个对象是否相等

```javascript
var obj = {a: 2, b: 2}
var obj1 = {a: 2, b: 2}
console.log(Object.is(obj, obj)) // true
```

#### 5 Object.keys()

方法会返回一个由一个给定对象的自身可枚举属性组成的数组，数组中属性名的排列顺序和使用 for…in 循环遍历该对象时返回的顺序一致 。

```javascript
let obj = {a: 1, b: 2}
let obj1 = {2: 'a', 1: ''}
console.log(Object.keys(obj))// ['a', 'b']
console.log(Object.keys(obj1))// ["1", "2"]
```

#### 6 obj.hasOwnProperty()

判断对象是否存在属性
ES6简洁写法：key in obj

```javascript
var obj = {a: 1, b: 2};
console.log(obj.hasOwnProperty('a')); // ES5 true
console.log('a' in obj); //ES6 true
```

#### 7 Object.getOwnPropertyDescriptor()

查看对象属性描述符

```javascript
var obj = {a: 1, b: 2};
console.log(Object.getOwnPropertyDescriptor(obj, 'a')) 
<!-- {-->
<!--configurable: true-->
<!--enumerable: true-->
<!--value: 1-->
<!--writable: true-->
<!--}-->
```

#### 8 Object.values()

返回对象所有的属性值数组。

```javascript
var obj = {a: 1, b: 2}
console.log(Object.values(obj)) // [ 1，2 ]
```

#### 9 Object.entries()

返回对象所有属性与属性值的键值对列表。

```javascript
var obj = {a: 1, b: 2}
console.log(Object.entries(obj)) // [ ['a', 1], ['b', 2 ]
```

#### 10 Object.fromEntries()

```javascript
var arr = [['c', 1], ['d', 2]];
console.log(Object.fromEntries(arr))// {a:1.b:2}
```

#### 11 Object.getPrototypeOf()

获取对象的原型。相当于直接获取obj.prototype。

#### 12 Object.setPrototypeOf()

设置对象的原型。相当于直接设置obj.prototype。

#### 13 Object.toString()

返回当前对象的字符串形式。

```javascript
原型方法
1、apply()
可以修改this的指向，执行并返回改变指向后的函数的运行结果。
原函数的传参以数组的方式传入。
2、arguments
返回当前函数的实参列表。
get/set
3、bind()
可以修改this的指向，返回改变指向后的函数。
4、call()
可以修改this的指向，执行并返回改变指向后的函数的运行结果。
原函数的传参以多个参数的的方式传入。
get/set
5、caller()
返回函数的调用环境。
6、constructor()
返回当前对象的构造函数。
7、length
返回当前函数的形参个数。
8、name
返回当前对象的名称。
9、toString()
返回当前对象的字符串形式。
```

