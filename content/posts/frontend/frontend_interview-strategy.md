---
title: "前端面试策略"
date: 2020-01-04T21:53:03+08:00
draft: true
tags: ["interview"]
categories: ["前端"]
featured_image: 
description: 
---

### 面试题

1.写出以下打印结果

```
var str = '123hello'
console.log(typeof(str++))
console.log(str)
```

2.写出以下打印结果

```
['1','3','10'].map(parseInt)
```

3.实现一个两侧固定宽度，中间自适应的布局

```
<div class="container">
  <div class="container-left"></div>
  <div class="container-middle"></div>
  <div class="container-right"></div>
</div>
```
4.写出以下打印结果

```
var number = 10;
function fn(){
    console.log(this.number);
}

var obj = {
    number:2,
    show:function(fn){
        this.number = 3;
        fn();
        arguments[0]();
    }
};
obj.show(fn);
```
this指向6种
- 直接调用指向window
- 对象调用指向对象
- new 指向生成的实例
- call,apply
- 箭头函数 
- 事件处理

5.写出以下打印结果
```
var foo = test()
var a = 'window'
function test(){
    console.log(a)
    this.a = 'function'
    var self = this
    var fa = self.a
    return function(){
        console.log(this.a)
        console.log(self.a)
        console.log(fa)
    }
}
foo()
```
考察作用域链

6.写出以下打印结果
```
function test(){
    console.log(1);
}

function init(){
    if(false){
        function test(){
            conosle.log(2);
        }
    }
    test();
}

init();
```
考察词法作用域

### 面试建议

- js基础，红宝书，es6至少一遍
- css基础，bfc格式化上下文，flex布局等要讲明白
- leetcode 按算法分类做题

一面  注重基础，知识网络，空杯心态
- css 
  - bem命名规范
  - css2，选择器，bfc,层叠上下文，伪类，伪元素，响应式开发原理
  - css3，flex布局，grid布局，变形，3d
  - 预处理器，sass,less,stylus
  - css-next语法
  - css houdini
- js
  - 原型链
  - 作用域链
  - 继承 es5,es6
  - this
  - 浏览器/node异步实现机制
  - es6 api 装饰器 ，promise，async/await
- 网络协议
  - osi 7层网络协议
  - tcp/ip 4层协议
  - http 1-3
  - https,密钥协商，证书验证
  - tcp,3次握手，超时重传，滑动窗口，拥塞窗口

二面 考察项目中的框架使用情况，多读框架源码，把简历中的技术栈吃透，不要写不熟悉的技术（i.e. typescript)。
- react生命周期
  - react15/react16
  - 为什么会废弃，fiber解决了什么问题，怎么实现
- dom diff算法
  - react/vue实现优缺点，优化方案
- react状态管理
  - 发布订阅模式
  - 中间件执行顺序问题

三面 在懂原理的基础上，考察对项目的思考，平常多练习、多思考、多总结。
- 你做过的最厉害的项目是什么
  - 遇到什么问题，怎么思考和解决的
  - 和同类项目相比的优势
- react有什么优点
- react有什么缺点

hr面 考察沟通表达能力、自学能力、职业规划和对公司的意向程度。
- 诚实、自信、乐观
- 谈薪技巧

### 面试思路

#### 技术一面：重点考察基础和知识广度（专业80%+软素质20%）

- 计算机基础：算法，数据结构
- 前端基础： 框架，浏览器原理，安全，跨端原理
- 编码能力：逻辑是否清晰，边界是否考虑，思维是否活跃
- 技术视野：行业技术现状，新技术的了解和实践

#### 技术二面：工程能力，设计能力，规划能力（专业60%+软素质40%）

- 工程能力：效率，质量，性能
- 设计能力：抽象能力，健壮性，扩展性
- 规划能力：做事的思路是什么
- 沟通和推动能力：是否有一套自己的项目推动方法和成功案例
- 产品意识： 学习能力，责任心

#### 面试评价

- 候选人信息
- 技术能力
  - 计算机基础
  - 前端基础
  - 编码能力
  - 技术视野
- 软实力
- 综合评价

#### 计算机基础题

- 进程和线程
- tcp和udp区别
- osi七层模型
- tcp/ip四层模型

#### 前端基础

- web前端应该从那些方面来有优化网站
  - 页面级别优化
    - 资源合并
    - 减少请求数
    - 图片懒加载
    - 图片合并压缩
    - 脚本后置
    - css前置
    - inline的脚本defer
    - 域名配置时防止发生跳转
    - 避免重复打包模块代码
  - 代码级别优化
    - 减少dom操作，virtual-dom的目标
    - css减少reflow
    - 避免使用eval和Function
    - 减少作用域链查找
    - css选择符，浏览器对选择符的解析是从右到左
- 从输入url到页面加载的过程 重要
- 如何在web端实现异步请求结果的复用，即只产生一次ajax请求并保证所有调用方式获取到数据
- 设计并实现一个jsonp函数
- 文件上传如何做断点续传/大文件上传
- http2.0了解多少
- http2.0的多路复用和http1.x中的长链接复用有什么区别
- http3.0用udp协议会有什么好处和坏处
- http缓存协议头部字段
  - cache-control
  - last-modified
  - etag
- etag和last-modified区别
- defer和async的区别
- es6 module，common.js,cmd,amd区别
- xss和csrf攻击原理，防御方法
- loadmore.js实现
- dom中property和attribute区别
- 为什么[] == (![])为true
- reverse一个字符串
- for,foreach,for...in,for...of区别
- bind实现
- 对象深拷贝
- 实现debounce(节流)和throttle(防抖)
- 异步经典
- promise的使用与实现，generator（异步编程，yield,next(),await,async)
- event loop
- css 
  - bfc规范
  - flex布局
  - 垂直居中
- react相关问题
- vue相关问题
- 算法基础
- node相关问题
- typescript相关问题
- webpack相关问题

#### 面试题库

- js 中 module 的了解
- 写一个单例模式
- 跨域方法
- get 与 post 的区别
- http 与 tcp 的区别
- 业务的了解
- 浏览器的缓存问题
- vim 的优势是什么
- react 和 vue有什么不同
- IFC
- BFC
- 内联元素与块级元素的区别
- react 单向数据流与传统 MVC，MVP的区别
- String.prototype.trim
- 把短横线字符转化为驼峰式字符
- 三列布局
- getComputedStyle
- N个数和为M
- 你最满意的项目，你觉得有哪些地方做的比较好
- 自适应的正方形
- 如何实现一个轮播图
- 基本数据类型
- 事件流冒泡和捕获，捕获用在什么地方
- 跨域和跨域的解决方法
- 你最满意的项目，你觉得有哪些地方做的比较好
- setInterval 与 setTimeout 的区别
- react 和 vue 的区别
- 跨域和跨域的解决方法
- http 的状态码有哪些
- html5 有哪些新的东西
- localStorage 和 sessionStorage 的区别
- setInterval 与 setTimeout 的区别
- webpack 有哪些东西，有哪些loader 和 plugin
- 你最满意的项目，你觉得有哪些地方做的比较好
- 数组去重，就地
- react的声明周期，各在里边做些什么操作
- react 请求发出去时组件已经卸载，fetch 如何取消
- async 会返回什么，如果发送多个async，多个 async 预制失败
- 如何做一些网站的性能优化
- 如何优化 webpack 体积
- 简单介绍下 grid layout，与table有什么不同
- 简单介绍下 redux ，它会不会循环
- 简单介绍一下CI，写一个脚本还是写一个程序
- 状态码和方法，101
- 502 和 504的区别
- 事件传播的阶段，以及addEventListener的执行顺序，绑定一个函数会执行几次
- virtual DOM 是什么以及是如何实现的
- dom diff 是什么
- get 和 post 请求
- 如何进行 CI 以及测试的，是否使用 ESLint
- Accept 头部的作用什么，如果服务器不支持怎么办
- tcp 如何做拥塞控制
- 事件代理是什么，如何实现
- 如何判断一个对象的类型，
- 如何把一个类数组转化为数组
- inline，inline-block，block元素有什么区别，其中inline-block元素有哪些，img是inline-block吗
- position 的取值
- 四分布局flex与float有什么区别
- 移动端一像素边框问题
- 移动端如何禁止屏幕缩放
- 移动端如何适配屏幕
- 移动端如何调试
- 数组去重问题
- 如何判断一个 DOM 节点包含另一个 DOM 节点，html5 如何做，兼容性怎么处理
- 如何筛选出一个祖父节点下的所有指定class的元素，html5如何做，兼容性怎么处理，如何判断一个节点是指定的class，正- 则表达式如何提取(漏了querySelectorAll)
- 如何提取 path 路径中的文件名，正则表达式如何提取
- 如何实现模板字符串
- suggestion 下拉列表如何做，应该使用什么事件，input，keyup, keypress 与 change 有什么不同
- 301 与 302 的区别
- 如何实现图片的懒加载
- 如何使用 canvas 处理图片
- 从浏览器输入 url 到页面展现的过程
- csp 是什么，xss 与 csrf 是什么，原理以及预防
- 如何实现一个 animate.js
- 如何实现一个模板引擎，并且能处理嵌套数据
- 如何实现两个函数的继承
- 好像做不到继承属性，util.inherits 也不继承属性
- 如何替换一个文件中的内容
- shell 中如何做循环
- for in 与 Object.keys 的区别
- 找出数组中最小的n个数
- bloom filter 是什么
- - Function.prototype.bind 的实现
- 一道 setTimeout/Promise 输出顺序问题的题
- 什么是事件循环
- async 与 generator 的关系以及实现原理
- react 和 vue 有什么区别
- vue 的双向绑定怎么实现的，在 3.0 后呢
- react 的生命周期是什么
- react 中的 key 用来做什么
- 有没有看过 fiber 的代码，原理是什么
- 什么是 virtual DOM
- webpack 的原理是什么，loader 和 plugin 的作用是什么
- 如何使用 webpack 优化体积
- 网站性能优化有哪些方面
- 有没有了解过 shell
- 对一个文件如何只查看特定行的内容
- 你们的 node 的服务端应用如何部署
- docker 部署有什么好处
- 部署时如何利用服务器的多核
- 你们有没有对服务端的异常进行监控
- 你如何看待前端和后端
- 如何查看一个 node 的服务端应用的内存和CPU
- 当一个地址从输入到展示在浏览器中有哪些步骤
- TCP 的三次握手是什么
- TCP 为什么要三次握手
- TCP 与 UDP 的区别是什么，既然 TCP 是可靠的，那它有啥缺点
- TCP 的拥塞控制是怎么做的
- 什么是防抖和节流
- 写一段关于防抖的代码
- graphql 有什么好处和劣势
- 什么是 serverless，如何看待它的发展
- 服务端渲染的原理是什么
- 服务端渲染会遇到哪些问题，与客户端渲染如何取舍
- 除了服务端渲染，还有哪些做 SEO 的方案
- react hooks 有什么好处
- 如果给 log 都加上 requestId，应该怎么做
- async hooks 是用来干嘛的
- 有没有看过 libuv 代码
- 什么是IO多路复用
- rpc 与 rest 相比有什么优势与劣势
- 什么是TCP粘包
- 如何设计一个消息队列，要注意什么地方
- 
- <br>

<center>  ·End·  </center>