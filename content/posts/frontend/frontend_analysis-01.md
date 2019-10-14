---
title: "前端监控平台analysis-01"
date: 2019-10-14T17:33:53+08:00
draft: false
tags: ["analysis"]
categories: ["前端"]
featured_image: 
description: 
---
## 背景

为了定位Web线上问题，需要对页面异常信息进行收集，分析和定位问题原因，以提升用户体验和产品运营效率。

## 维度
前端监控的维度主要分为以下3个方面：

- 性能
- 异常
- 用户行为

## 原理

- 监听window对象的onerror事件。
- 使用try catch语句。

## 案例

- [开源] 腾讯 [badjs](https://betterjs.github.io/)
文档说明详细，提供完整解决方案，项目落地10+。
  + 日志功能
  + 上报功能
  + 统计功能
  + 邮件功能
- [收费] [sentry](https://sentry.io)
  + 代码开源
  + [价格](https://sentry.io/pricing/)
- [收费] [fundebug](https://www.fundebug.com/)
  + [价格](https://www.fundebug.com/price)
- [收费] 阿里云ARMS-[前端监控](https://help.aliyun.com/document_detail/58652.html?spm=5176.8064714.976547.2.251cIEc0IEc0Ro)
  + 主动监控
  + 慢会话追踪
  + 搜索报错明细
  + 出错行为还原
- [收费] 蒲公英 [frontjs](https://www.frontjs.com) 
  + [价格](https://www.frontjs.com/pricing)
- [无维护] 淘宝 [JSTracker](https://github.com/CurtisCBS/monitor)
  + 参考README
- [未开源] 阿里 FdSafe
- [无维护] 支付宝 [saijs](https://github.com/saijs/sai.js)
  + [javascript异常文档](https://github.com/saijs/wiki)

## 需求分析
- 错误收集
  + 错误信息
    + 资源加载错误
    + 运行时错误
  + 性能指标
    + 页面加载时长
    + 首次渲染时长
    + 首次内容渲染时长
    + 首次有效渲染时长
    + ...
  + 日志数据
  
- 上报策略
  + ajax
  + 跨域 CORS协议
  + image对象
  
- 日志采集与存储
  + 数据过滤
  + 节流

- 告警功能
  + 最大最小值
  + 错误累计数
  + 异常等级
  + 自定义

- 邮件短信通知
- 错误定位与复现
- 管理后台数据可视化

<br>

<center>  ·End·  </center>