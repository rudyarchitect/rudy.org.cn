---
title: "编辑器01"
date: 2019-10-14T19:18:13+08:00
draft: false
tags: ["editor"]
categories: ["前端"]
featured_image: 
description: 
---

页面 = HTML Tree (DOM) + 静态Data + 动态逻辑Javascript

页面可视化编辑本质上是用可视化的方式对页面的DOM、静态Data和动态逻辑javascript进行操作，从而完成页面的生成。

前端服务化，为前端小白，运营/产品人员,以及后台开发人员提供开发前端页面的能力。

- 系统粒度
  + HTML Tree编辑
  + Component Tree编辑
  + 静态Data编辑
  + 动态逻辑Javascript编辑
- 面向群体
  + 前端小白
  + 运营/产品人员
  + 后台开发人员 
- 编辑自由度
  + 页面
  + 组件

核心原理：模板 + 配置数据 = 页面

最佳实践
- 数据格式Json Scheme
- 组件化和模板化
- 编辑与组件、模板和框架解耦
- 框架负责数据管理
  + 数据包括组件数据和业务数据，管理包括保存数据和读取数据方式。
- 分析数据管理的简单场景和复杂场景，确定边界
- 组件暴露所有属性和事件
- 渐进式体验
- 数据驱动
  + 数据现在是什么样子
  + 数据在哪里被修改了

<br>

<center>  ·End·  </center>