---
title: "前端面试考点"
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

<br>

<center>  ·End·  </center>