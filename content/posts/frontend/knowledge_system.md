---
title: "Knowledge_system"
date: 2019-12-30T11:00:10+08:00
draft: false
tags: [""]
categories: [""]
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
- es6知识点
- js异步
- promise
- event loop
- 浏览器缓存机制
- 浏览器渲染原理与机制
- v8 js性能优化
- webpack性能优化
- react
- vue
- angular
- 监控
- http
- 设计模式
- 数据结构
- 算法
- css




<center>  ·End·  </center>