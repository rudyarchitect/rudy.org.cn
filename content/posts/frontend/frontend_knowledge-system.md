---
title: "前端知识体系"
date: 2019-12-30T11:00:10+08:00
draft: false
tags: ["system"]
categories: ["前端"]
featured_image: 
description: 
---

<br>

- es5 知识点
  - 原始类型 //值
    - boolean
    - undefined
    - null
    - number
    - string
    - symbol ?
  - 对象类型 object //内存地址（指针）<--> 值
  - typeof null // 'object' is bug
  - 0.1+0.2=0.30000000000000004 // number 浮点类型
  - typeof 判断原始类型
  - instanceof 判断对象类型
  - 类型转换
  - this指向
    - 函数直接调用 指向window
    - 对象 谁调用指向谁
    - new 指向实例
    - bind/箭头函数 多次调用，this指向取决于第一次调用上下文
  - == vs === //==涉及类型转换
  - 闭包 存在的意义就是可以访问外部函数的变量
  - 对象拷贝
    - 浅拷贝 object.assign() / 展开运算符 ...  //拷贝属性值，属性中有对象的话，拷贝的是地址
    - 深拷贝 lodash.cloneDeep() //自己实现一个
  - 原型 //重点
    - Object
    - Function
    - __proto__
  - 函数提升优先于变量提升
- es6知识点
  - let,const 暂时性死区
  - 继承
    - 原型
    - class
  - 模块化
    - commonjs 服务器端/同步/值拷贝
    - es module 浏览器端/异步/地址拷贝
  - proxy
    - 数据响应式
  - map,filter,reduce
- js进阶
  - 回调函数 callback
  - generator
  - promise 实现
  - async/await
  - requestAnimationFrame
  - call , apply , bind , new 实现
  - 垃圾回收机制
- event loop
  - 执行栈 call stack 先进后出 同步执行的js代码
  - 任务队列 task queue 异步执行的js代码
    - 宏任务 macro task //setTimeout , setInterval , xhr ...
    - 微任务 micro task // promise , mutation observer ...
  - 浏览器
  - node 
- 浏览器
  - 事件机制
    - 注册
    - 触发
    - 代理
  - 跨域
    - 同源策略
    - 解决方案
      - jsonp
      - cors
      - document.domain
      - postMessage
  - 存储
    - cookie
    - localStorage
    - sessionStorage
    - service worker
  - 缓存机制
    - 缓存位置
    - 强缓存
    - 协商缓存
  - 渲染原理
  - 从url到页面渲染的整个流程
- 安全
  - xss
  - csrf
- 性能优化
  - js
  - webpack
- react
- vue
- angular
- 监控
  - 行为
  - 性能
  - 异常
- http
  - 请求方法
  - 首部
    - 通用
    - 请求
    - 响应
    - 实体
  - 状态码
  - tsl
    - 加密
      - 对称
      - 非对称
    - 3次握手
      - udp
      - tcp
  - http2
- 设计模式
- 数据结构
- 算法
- css




<center>  ·End·  </center>