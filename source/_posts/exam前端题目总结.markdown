---
layout:     mark
title:      "exam前端题目总结"
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

#### HTML
+ <img标签> alt和title同时设置的时候，title作为图片的替代文字出现，alt是图片的解释文字。
+ <i、em标签>都表示斜体，区别`<em>`表示强调、可以被设备识别，`<i>`单纯表示斜体、不能被识别。
+ <audio标签> 定义声音，比如音乐或其他音频流。
+ <canvas标签> 定义图形，比如图表和其他图像。
+ <menu标签> 定义命令的列表或菜单。用于上下文菜单、工具栏以及用于列出表单控件和命令。
+ <command标签> 可以定义命令按钮，比如单选按钮、复选框或按钮。
+ <pre标签> 定义预格式文本，保持文本原有的格式。
+ <meta标签> 可提供有关页面的元信息，位于文档的头部，不包含任何内容。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">浏览器模式<span>
  + 浏览器模式有两种呈现模式：`标准模式`和`混杂模式`。在标准模式中，浏览器根据规范呈现页面；在混杂模式中，页面以一种比较宽松的向后兼容的方式显示。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">DOCTYPE模式<span>
  + DOCTYPE 有两种风格，`严格`（ strict ）和`过渡`（ transitional ）。过渡 DOCTYPE 是帮助开发人员从老版本迁移到新版本。
  + DOCTYPE 不存在或格式不正确会导致文档以`兼容模式`呈现。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">元素继承</span>
  + 所有元素可继承：visibility和cursor。
  + 内联元素可继承：letter-spacing、word-spacing、white-space、line-height、`color`、`font`、`font-family`、`font-size`、font-style、font-variant、font-weight、text-decoration、text-transform、direction。
  + 终端块状元素可继承：text-indent和text-align。
  + 列表元素可继承：list-style、list-style-type、list-style-position、list-style-image。

#### CSS
+ css属性`overflow`属性定义溢出元素内容区的内容会如何处理。如果值为 scroll，不论是否需要，用户代理都会提供一种滚动机制。
+ css属性`border: none`表示边框样式无, 浏览器不进行渲染，不占用内存。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">CSS Sprites<span>
  + 它允许将一个页面涉及到的所有零星图片都包含到一张大图中。
  + 利用CSS的“background-image”，“background- repeat”，“background-position”的组合进行背景定位，避免图片载入缓慢的现象。
  + 它能减少图片的字节。
  + 它能很好地减少网页的http请求，从而大大的提高页面的性能。
  + 但是：图片合并麻烦、图片适应性差、图片定位繁琐、可维护性差。

#### JavaScript
+ `onload方法` 是某个页面的css js html 文档结构和图像被完全加载。
+ `escape方法`： 返回对一个字符串编码后的结果字符串。
+ `eval方法`：将某个参数字符串作为一个JavaScript执行。
+ `parseFloat方法`：将一个字符串转换成对应的小数。
+ flash和js通过`ExternalInterface`类进行的交互。
+ `call（）`，第一个参数是 运行函数的作用域，其余传递给函数的参数必须逐个列举出来。
+ `apply（）`，第一个参数是 运行函数的作用域 ，另一个参数是参数数组, 可以是Array实例或arguments对象。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">继承</span>
  + 6种方式： `原型链`继承、借用`构造函数`继承、`组合`继承、`原型式`继承、`寄生式`继承、`寄生组合式`继承。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">异步编程模式</span> 
  + 4种方法： `回调函数`、`事件监听`、`发布/订阅`、`Promises`对象：。

#### 跨域
+ 只要 协议 、 域名 、 端口 有任何一个 不同, 都被当作是 不同 的域
+ js可以使用jsonp进行跨域
+ 通过修改document.domain来跨子域
+ 使用window.name来进行跨域

#### 栈内存和堆内存
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">栈(stack)和堆（heap）</span>
  + stack为`自动分配`的内存空间，它由系统自动释放；而heap则是`动态分配`的内存，大小也不一定会自动释放
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">数据类型</span>
  + `基本数据类型`：Number、String、Boolean、Null、Undefined、Symbol（ES6）、Null，可以直接操作保存在变量中的实际值。
  + `引用数据类型`：Object（在JS中除了基本数据类型以外的都是对象，Array，Function，Date，RegExp都是对象）。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">栈内存</span>
  + 存储`基本数据类型`的变量以及`引用数据数据类型变量的指针`,像一个线性排列的空间，每个小单元大小基本相等，内存空间大小可以分配，数据大小确定，按值存放，按值访问。
+ <span style="color: #40B8FA;border-bottom: 1px solid #3BAAFA;">堆内存</span>
  + 存储`引用数据类型`值的变量，每个空间大小不一样，要根据情况进行特定的配置
<img src="/img/knowledge/stack.jpg" width="60%">

#### 浅拷贝和深拷贝
  + 文章转载：
    + [深浅拷贝1](https://www.cnblogs.com/c2016c/articles/9328725.html)
    + [深浅拷贝2](https://juejin.im/post/5d0a48d86fb9a07ea803cf23)
  + 目标：是相对于`引用类型`而言的。
  + 定义：
    + 浅拷贝： 指复制后两个js 对象 `指向同一个内存地址`，其中一个改变会影响另一个。
    + 深拷贝： 指复制后的新对象重新 `指向新的内存地址`，两个对象改变互不影响。
  + <span style="color: #ff502c;border-bottom: 1px solid #ff502c; font-weight: bolder">浅拷贝 - 常用方法</span>
    + <span style="color: #ff502c; font-weight: bolder">1、赋值</span>
    ````
    let a = [1, 2, 3, 4, 5]
    let b = a         //  指针相同，指向同一个对象
    b[0] = 0
    console.log(a)     //  [0, 2, 3, 4, 5]
    console.log(b)     //  [0, 2, 3, 4, 5]
    console.log(a==b)  //  true
    console.log(a===b) //  true

    ````
    <img src="/img/knowledge/copy.jpg" width="60%">

  + <span style="color: #ff502c; font-weight: bolder">2、Object.assign() `[ES6]`</span>
    + 定义： 把任意多个的源对象自身可枚举属性拷贝给目标对象，然后返回目标对象
      ` let obj = Object.assign({目标对象}, {源对象1}，{源对象2}，... )`

      ````
      let obj1 = {
        study: {
          name: 'math'
        },
        age: 16 
      }
      let obj2 = Object.assign({}, obj1)
      obj2.study.math = 'chinese'
      console.log(obj1)  // { study: {name: 'chinese'}, age: 16 }
      console.log(obj2)  // { study: {name: 'chinese'}, age: 16 }
      console.log(obj1.study.name == obj2.study.name)  //  true
      console.log(obj1.study.name === obj2.study.name) //  true

      ````

  + <span style="color: #ff502c; font-weight: bolder">3、extend() `[递归思路]`</span>
    + ` $.extend(参数1，{}, obj)`： 参数1`不写`或为`false`表示浅拷贝， `true`表示深拷贝

      ````
      let obj1 = {
        study: {
          name: 'math'
        },
        age: 16 
      }
      let obj2 = $.extend({}, obj1)
      obj2.study.name = 'chinese'
      console.log(obj1)  // {study: {name: 'chinese'}, age: 16}
      console.log(obj2)  // {study: {name: 'chinese'}, age: 16}
      console.log(obj1.study.name == obj2.study.name)  // true
      console.log(obj1.study.name === obj2.study.name) // true

      ````
  + <span style="color: #ff502c; font-weight: bolder">4、Array.prototype.concat() `[数组]`</span>
    + 数组concat返回一个新数组，不影响原数组

      ````
      let arr1 = [[1, 2], 3, 4]
      let arr2 = arr1.concat()

      arr1[0][0] = 0
      console.log(arr1)          // [[0, 2], 3, 4]
      console.log(arr2)          // [[0, 2], 3, 4]

      ````

  + <span style="color: #ff502c; font-weight: bolder">5、Array.prototype.slice() `[数组]`</span>
    + 数组slice返回一个新数组，不影响原数组
    
      ````
      let arr1 = [[1, 2], 3, 4]
      let arr2 = arr1.slice()

      arr1[0][0] = 0
      console.log(arr1)          // [[0, 2], 3, 4]
      console.log(arr2)          // [[0, 2], 3, 4]

      ````

  + <span style="color: #ff502c; border-bottom: 1px solid #ff502c; font-weight: bolder">深拷贝 - 常用方法</span>
    + <span style="color: #ff502c; font-weight: bolder">1、赋值`[一维数据]`</span>

      ````
      let obj1 = {
        a: 10,
        b: 20
      }
      let obj2 = {
        a: obj1.a,
        b: obj1.b
      }
      obj2.b = 100
      console.log(obj1)   // { a: 10, b: 20}
      console.log(obj2)   //  { a: 10, b: 100}
      console.log(obj1 == obj2)    //  false
      console.log(obj1 === obj2)    //  false

      ````

    + <span style="color: #ff502c; font-weight: bolder">2、Object.assign() `[一维数据、ES6]`</span>

      > ps：不是真正意义上的深拷贝

      ````
      let obj1 = {
        study: {
          name: 'math'
        },
        age: 16 
      }
      let obj2 = Object.assign({}, obj1)
      obj2.study.age = 5
      console.log(obj1)  // { study: {name: 'math'}, age: 16 }
      console.log(obj2)  // { study: {name: 'math'}, age: 5 }
      console.log(obj1 == obj2)  //  false
      console.log(obj1 === obj2) //  false

      ````

    + <span style="color: #ff502c; font-weight: bolder">3、Array.prototype.concat() `[一维数据、数组]`</span>

      > ps：不是真正意义上的深拷贝

      ````
      let arr1 = [[1, 2], 3, 4]
      let arr2 = arr1.concat()

      arr1[1] = 66
      console.log(arr1)          // [[1, 2], 66, 4]
      console.log(arr2)          // [[1, 2], 3, 4]

      ````

    + <span style="color: #ff502c; font-weight: bolder">4、Array.prototype.slice() `[一维数据、数组]`</span>

      > ps：不是真正意义上的深拷贝

      ````
      let arr1 = [[1, 2], 3, 4]
      let arr2 = arr1.concat()

      arr1[1] = 66
      console.log(arr1)          // [[1, 2], 66, 4]
      console.log(arr2)          // [[1, 2], 3, 4]

      ````

    + <span style="color: #ff502c; font-weight: bolder">5、JSON.parse(JSON.stringify(obj))`[二维数据]`</span>
      + a、能够处理JSON格式的所有数据类型。
      + b、会抛弃对象的`constructor`，即：不管该对象原来构造函数是什么，深拷贝后都会变成`Object`。
      + c、`正则表达式`类型、`函数类型`等无法进行深拷贝，且会直接丢失相应的值。
      + d、如果对象中存在循环引用的情况也无法正确处理。

      ````
      let obj1 = {
      study: {
        name: 'math'
        },
        age: 16 
      }
      let obj2 = JSON.parse(JSON.stringify(obj1))
      obj2.study.name = 'chinese'
      console.log(obj1)  // { study: {name: 'math'}, age: 16 }
      console.log(obj2)  // { study: {name: 'chinese'}, age: 16 }
      console.log(obj1 == obj2)  //  false
      console.log(obj1 === obj2) //  false

      ````

    + <span style="color: #ff502c; font-weight: bolder">6、extend() `[二维数据、递归思路]`</span>
      ` $.extend(true, {}, obj)`

      ````
      let obj1 = {
        study: {
          name: 'math'
        },
        age: 16 
      }
      let obj2 = $.extend(true, {}, obj1)
      obj2.study.name = 'chinese'
      console.log(obj1)  // {study: {name: 'math'}, age: 16}
      console.log(obj2)  // {study: {name: 'chinese'}, age: 16}
      console.log(obj1 == obj2)  // false
      console.log(obj1 === obj2) // false

      ````
    + <span style="color: #ff502c; font-weight: bolder">7、lodash中的_.clone(obj, true)等价于_.cloneDeep(obj) `[二维数据、递归思路]`</span>

      ````
      let obj1 = {
        study: {
          name: 'math'
        },
        age: 16 
      }
      let obj2 = _.cloneDeep(obj1)
      obj2.study.name = 'chinese'
      console.log(obj1)  // {study: {name: 'math'}, age: 16}
      console.log(obj2)  // {study: {name: 'chinese'}, age: 16}
      console.log(obj1 == obj2)  // false
      console.log(obj1 === obj2) // false

      ````

  + <span style="color: #ff502c;border-bottom: 1px solid #ff502c; font-weight: bolder">深拷贝不同方法的性能对比</span>

    > <p style="font-size: 16px; font-weight: bolder">`一维数据`结构的深拷贝方法`性能最佳`为: `Object.assign()`</p>
    > <p style="font-size: 16px; font-weight: bolder">`二维数据`结构的深拷贝方法`性能最佳`为: `JSON.parse(JSON.stringify())`</p>

#### 原型 / 继承
  + 构造函数：
    + 定义： 构造函数本身就是一个函数，与普通函数没有任何区别，不过为了规范一般将其`首字母大写`。构造函数和普通函数的区别在于，使用 new 生成实例的函数就是构造函数，直接调用的就是普通函数。