---
layout: post
title: 前端技术日志 - 2020年5月8日
excerpt: is-promise 的反思；无障碍字体大小最佳实践；CSS 的魔法：min()、max()、clamp()
---

> 本技术日志，每周定期分享，欢迎关注、转发。

### `is-promise` 的几行代码是如何把前端生态搞奔溃的？

一周前，有人反馈，`create-react-app` 被弄坏了。罪魁祸首是一个小小的依赖的微小变化：`is-promise`。幸运的是，它很快修复了。这篇文章是 `is-promise` 的作者对这个问题的反思。

[https://medium.com/javascript-in-plain-english/is-promise-post-mortem-cab807f18dcc](https://medium.com/javascript-in-plain-english/is-promise-post-mortem-cab807f18dcc)

### 无障碍字体大小最佳实践

网页中什么样的字体大小是易于访问的？Bootstrap 的核心团队成员 *Andres Galante* 介绍了关于字体大小的可访问性的一些最佳实践，从而让用户获得更好的阅读体验。

[https://css-tricks.com/accessible-font-sizing-explained/](https://css-tricks.com/accessible-font-sizing-explained/)

### CSS 魔法之：`min()`、`max()`、`clamp()` - 视频

min、max、clamp 函数，现在已获得广泛的浏览器支持。这是一段介绍如何使用这些属性来真正的开启响应式排版技术的视频。

[https://www.youtube.com/watch?v=U9VF-4euyRo](https://www.youtube.com/watch?v=U9VF-4euyRo)

### CSS 国际化

一篇用 CSS 的特性来实现国际化的指南。

[https://chenhuijing.com/blog/css-for-i18n/#%F0%9F%91%9F](https://chenhuijing.com/blog/css-for-i18n/#%F0%9F%91%9F)

## 文章和教程

### 10 个实用的 JavaScript 技巧

这类列表通常都很普通，但实际上这里包含了一些鲜为人知的，您可能从未见过的小帖士。

[https://dev.to/zandershirley/10-practical-javascript-tricks-2b7h](https://dev.to/zandershirley/10-practical-javascript-tricks-2b7h)

### `window.location` 指南

本篇文章涵盖了 `window.location` 对象上可用方法和属性的方方面面。

[https://dev.to/samanthaming/window-location-cheatsheet-4edl](https://dev.to/samanthaming/window-location-cheatsheet-4edl)

### CSS 中的间距

这是一篇你需要知道的关于 CSS 间距的一切，覆盖了网格布局、Flexbox、定位等等。

[https://ishadeed.com/article/spacing-in-css/](https://ishadeed.com/article/spacing-in-css/)

### 沉浸式过渡效果

一篇不一样的网页动画教程，实现在页面元素之间，体验身临其境的过渡效果。

[https://codyhouse.co/tutorials/immersive-section-transition-effect?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter](https://codyhouse.co/tutorials/immersive-section-transition-effect?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter)

## 实用工具

### I18n Ally

一个多合一 i18n 的 VS Code 扩展。I18n Ally 可为你提供行内注释、Google Translate 自动翻译、进度指示等，支持各种现在流行的前端框架。

[https://github.com/antfu/i18n-ally#readme](https://github.com/antfu/i18n-ally#readme)

### 1loc

一些实用又精巧的 JavaScript 单行代码片段集合，包括数组、日期/时间、DOM等。

[https://1loc.dev/](https://1loc.dev/)

### 98.css

一个很有复古风（Windows 98）的 CSS 库。

![98.css](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image3.png)

[https://github.com/jdan/98.css](https://github.com/jdan/98.css)

### PicsArt Photo Editor

十几种在线图片编辑工具，它们都有很多有用的功能，比如双色调效果、叠加、滤镜、背景编辑等等。

[https://picsart.com/photo-editor](https://picsart.com/photo-editor)

### markmap-lib

一个使用思维导图可视化 Markdown 的工具。

![markmap-lib](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image2.png)

[https://markmap.js.org/](https://markmap.js.org/)

### react-easy-state

一个用 ES6 Proxy 实现的 React 状态管理，其 API 非常简洁易用。

![react-easy-state](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image1.png)

[https://github.com/RisingStack/react-easy-state](https://github.com/RisingStack/react-easy-state)

### use-scroll-to-bottom

一个 React Hook，使用 IntersectionObserver 来检测用户是否已滚动到页面底部。

[https://github.com/tudorgergely/use-scroll-to-bottom](https://github.com/tudorgergely/use-scroll-to-bottom)

### React Table

一个用来构建轻量、快速和可扩展的数据网格的 React Hooks，现在已经是 v7.0 版本了。

[https://react-table.js.org/](https://react-table.js.org/)

### Public APIs

一个为开发者收集的开放的 API，网站还为它们分了类。

[https://public-apis.io/](https://public-apis.io/)

## 内容来源

- [Frontend Focus](https://frontendfoc.us/): *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/): *https://javascriptweekly.com/*
- [Responsive Design Weekly](https://responsivedesign.is/): *https://responsivedesign.is/*
- [Web Tools Weekly](https://webtoolsweekly.com/): *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/): *https://weekly.cssanimation.rocks/*

关注公众号，关注前端技术

![赵不寒的网络日记](/assets/qrcode-clean.jpg)

