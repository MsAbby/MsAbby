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