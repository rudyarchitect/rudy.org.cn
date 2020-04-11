---
title: "前端灰度发布"
date: 2020-01-16T12:03:31+08:00
description:
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tags:
- 
series:
- "gray"
categories:
- "前端"
---

## 灰度发布

灰度发布，又称为金丝雀发布，即产品每次新功能的发布和旧功能的替换能够以平滑过渡的方式呈现给用户，就像金丝雀的羽毛一样，多种颜色能够平滑渐变。

### 原因

- 考虑用户使用反馈和代码未知异常，需要将新的功能逐步地推给一批又一批的用户
- 根据用户的接受程度（投诉情况）和代码是否存在上线前未发生的异常，来决定是否发布新功能
- 避免出现一次更新导致线上问题阻塞用户体验的情况发生

### 优点

- 提前收集用户使用意见，及时调整产品功能
- 控制代码异常出现的用户范围
- 出现未知风险时，可以及时回滚到旧版本

### 要素

- 规则
  - 用户按照特征分成不同群体，例如年龄，地区，以及用户注册时的id
  - 按照百分比，从小到大放量，直到完成
- 版本
  - 资源版本号
  - 资源访问新旧切换

  ### 实现策略

<img alt="gary-level-01" src="https://rudyarchitect.github.io/blog-images/frontend/frontend_gary-level-01.jpg">

- 方式
  - 服务器端
  - 浏览器端

