---
title: "chrome插件简介"
date: 2019-10-23T09:44:42+08:00
draft: false
tags: ["plugin"]
categories: ["前端"]
featured_image: 
description: 
---

chrome extenstion是一个使用web技术开发、用来增强浏览器功能的插件，它实际上是一个由html,js,css,images等资源组成的.crx压缩包。

## manifest.json

用来描述插件的元数据

## 3种资源文件

- browser_action/page_action
   - 插件的popup窗口
   - browser_action针对所有页面，page_action针对指定页面

- background
  - 插件的js运行环境
  - 消息传递机制和其它页面通信 sendMessage/onMessage
  - 无限制跨域

- content_scripts

  - 在当前页面运行的js文件，负责操作页面DOM
  - 和当前页面js处于不同上下文

<img alt="chrome-extension-01" src="https://rudyarchitect.github.io/blog-images/frontend/frontend_chrome-extension-01.jpg">

## 长链接
  - background和popup 

    - 可以直接互相调用，不用消息传递

  - background和content
    - postMessage+connect

<br>

<center>  ·End·  </center>