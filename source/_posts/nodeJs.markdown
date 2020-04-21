
---
layout:     mark
title:      "NodeJs学习"
subtitle:   "Whether:sunny / Mood:am-normal, pm-normal / Especially:0"
date:       2020-04-17 14:09:00
author:     "lsm"
catalog:    true
header-img: "/img/banner6.jpg"
tags:
    - 前端开发
    - 语言
---

## nodeJs

> 背景：
>
> 1、nodeJS是单线程非阻塞 I / O
>
> 2、nodejs运行环境是V8引擎，性能好，
>
> 3、利用事件驱动机制
>
> 4、学习成本低：网站开发、即时通信、小程序开发、跨平台开发等； 不适用于银行、证券等方向

##### 1、单线程

- 优点：
  - 高性能：不用反复创建线程、销毁线程，速度快，内存占用小
  - 安全：不用担心同一变量同时被多个线程进行读写而造成的程序崩溃
- 劣势：
  - 适合小型项目开发，一旦一个事件阻塞了I/O，整个nodeJs都会瘫痪

##### 2、单线程非阻塞I/O

- 特点：非阻塞I/O是在执行了数据库访问代码后立即执行后续的代码，把数据库返回的结果放在回调函数中，当函数执行完毕自动获取该结果，这就提高执行效率

##### 3、 事件驱动

- 特点： 将事件放入一个事件环中，不停的查看事件环来让回调函数（可能是磁盘I/O，网络通信、数据库查询等操作）对其进行处理。

##### 4、浏览器工作原理

+ 客户端： 发送请求 （性能无法控制）

+ 服务端： 接受请求，通过I/O从数据库数据 （性能控制有 “ 服务器宽带 ” 和CDN加速）

+ 服务端： 数据传输给客户端（算法优化和多线程优化）

+ 客户端： 数据解析，渲染


## NodeJ工作

##### 1、导入http

```javascript
var http = require('http');
```

##### 2、创建服务器

```javascript
// 创建一个服务器
let server = http.createServer(function(request, response) {
    // 发送http头部
    response.writeHead(200,  { 'Content-Type': 'text/plain' })
    // 告诉浏览器响应结束
    response.end()
});
// 服务器启动并监听指定端口
server.listen(8080);
// 终端打印信息
console.log(“Server running at http://127.0.0.1:8888”);
```

##### 3、运行

```javascript
node server.js
```

##### 4、fs文件系统

- 传统方法： 先把数据缓存到内存中，再回调，比较浪费内存，对大文件不友好，因此用流好一些

```javascript
const fs = require('fs');
// 1、读取文件
fs.readFile("文件名", (ex, data) => { });
// 2、创建文件
fs.writeFile("文件名", data, ex => {});
// 3、追加文件
fs.appendFile("文件名", data, ex => {});
// ps: data是buffer类型，内置了：toString() 和 toJSON()
```

- 流方法

```javascript
const fs = require('fs');

let rs = fs.createReadStream("aa.png");
let ws = fs.createWriteStream("bb.png");
rs.pipe(ws); // 创建一个管道，流从r端到w端

// 读取失败
rs.on("error", ex => {});
// 读取完成
rs.on("end", () => {});
// 写入失败
ws.on("error", ex => {});
// 写入完成
ws.on("finish", () => {});
```

##### 5、url

```javascript
const url = require('url');
// 想要解析`query`，可以多传一个参数
let jd_url = "https:www.baidu.com?keyword=11&bb=22";

str = url.parse(jd_url, true);
console.log(str); // 对query解析
```

##### 6、path

```javascript
const path = require('path');
let file_name = "./images/png/aa.png";

console.log(path.dirname(file_name)); // 文件路径 ./images/png
console.log(path.basename(file_name)); // aa.png
console.log(path.extname(file_name)); // .png

// 文件信息 {root: "", dir: "./images/png", base: "小明.png", ext: ".png", name: "小明"}
console.log(path.parse(file_name)); // 这个经常使用

console.log(path.resolve()); // 当前文件所在文件夹绝对路径
console.log(path.resolve(file_name)); // 文件的绝对路径
```