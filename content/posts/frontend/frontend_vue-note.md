---
title: "vue学习笔记"
date: 2019-10-09T16:03:06+08:00
draft: false
tags: ["vue"]
categories: ["前端"]
featured_image: 
description: 
---
npm root -g

npm config set prefix [path]

npm list /ls

—save -S //生产环境 默认

—save-dev -D //开发环境

npm view [module] version/versions

npm get registry

npm config set registry [url]

V-model //vm

v-once

v-html

v-bind：属性 = 数据 // ：属性 = 数据

v-on：事件 = 函数 // @ 事件 = 函数

函数和计算属性区别
1. 计算属性有缓存
2. 支持双向绑定 get/set

Vue instance 
{
    el,
    data,
    methods,
    compute,
    watch
}

class,style使用v-bind绑定//string, object,array

v-show // css display属性实现，仍存在dom中，频繁切换使用，否则使用v-if

v-for // 使用时添加v-bind:key

$event//event原生事件

事件修饰符 .stop .prevent .once

v-on:keyup.按键名 //按键修饰符

v-pre // 忽略Vue编译，提升性能

v-text/v-clock //隐藏双大括号

directives //自定义全局或局部指令

<br>

<center>  ·End·  </center>