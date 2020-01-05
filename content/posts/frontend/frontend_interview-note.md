---
title: "前端面试考点"
date: 2020-01-04T21:53:03+08:00
draft: true
tags: ["interview"]
categories: ["前端"]
featured_image: 
description: 
---

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

面试建议

- js基础，红宝书，es6至少一遍
- css基础，bfc格式化上下文，flex布局等要讲明白
- leetcode按算法分类做题

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

<br>

<center>  ·End·  </center>