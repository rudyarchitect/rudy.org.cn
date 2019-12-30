---
title: "后起之秀Vue Chapter01-Section04"
date: 2019-10-28T18:12:39+08:00
draft: true
tags: ["book"]
categories: ["作书"]
featured_image: 
description: 
---

- 后起之秀Vue 10页
  - 初识Vue
    - 发展历程
    - 特点？
  - 核心原理
    - 双向绑定
      - 实现区别
      - 一步步深挖
    - 事件系统
  - 数据流
  - 版本优化
  - 服务端渲染
  - 和React对比
    - 一直模仿

## 素材

vue核心api、组件化机制、通讯机制、数据驱动 npm i -g @vue/cli

- 数据绑定
  - 插值绑定{{}}
  - 属性绑定 ：
- 条件 v-if
- 循环 v-for
- 用户交互
 - 输入 input 
 - 事件 @
- 组件化思想 堆积木思想
 - 通用组件
 - 基础组件
 - 业务组件
- 通信机制 如何解耦？总线模式
 - $emit 派发事件
 - $on 监听事件
- 数据持久化 localStorge
- 计算属性 compute
- 监听属性 watch 浅/深拷贝
- element-ui 
  - 思考组件如何设计？
    - 粒度划分
    - 功能划分
    - 父子通信
    - 数据流
  - e.g. 表单
    - 划分功能
    - 双向绑定 v-model = 绑定 v-bind + 事件 v-on
    - 插槽 slot
    - provide/inject 依赖注入？隔代传值 dispatch？
    - es6计算属性
    - $parent/$children
    - 异步 利用 promise async/await
  
vue全家桶 vue-router vuex

- 路由 vue add router
  - router-link a标签
  - router-view
  - 嵌套 children属性
    - 传参 :params
    - 获取参数 $route.params/props
    - 查询参数 $route.query
  - 路由hooks 
    - beforeEach(to,from,next) 全局
    - beforeEnter属性 单个路由
    - 组件内部
  - meta 元数据
  - 默认事件阻止 prevent

- vuex 单向数据流 vue add vuex
  - 异步 dispatch 利用promise
  - 变化只能是mutation
  - 数据存储store
  - 状态属性 state
  - 动作 actions
  - 利用计算属性做映射 map
  - 原理 利用vue本身的数据响应机制
  - 实现简化版本，源码 store.js 考虑了模块化，插件
  - 和redux最大区别是vuex强依赖vue，vue-router同理

  - nginx 代理  解决跨域问题

  vue源码解析

  - vue 工作机制
    - object.defineProperty getter/setter 数据劫持 实现响应式、依赖收集
    - 编译
      - parse 抽象语法树 ast
    - 递归，解决对象数据嵌套
    - 代理，简化层级调用
    - 正则，获取标签

  项目思考
  - 任何一个UI库，都不能满足全部的业务开发需求，都需要定制和扩展，组件化设计思路至关重要。
  - 权限控制 令牌机制 token(有时效) ，存储在localstorage VS Session
    - bearer token
    - json web token
  - 请求/响应拦截器 
  - 接口mock node
  - 数据管理 vuex
  - 代理 服务器
  - 动画设计
    - vue css动画 
    - javascript钩子
  - 全局组件
    - 将生成的dom元素挂载到body

SSR
  - vue ssr
  - nuxt.js
  - 实现原理
  - 应用场景

  


<br>

<center>  ·End·  </center>