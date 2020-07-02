---
layout: post
title: 前端技术日志 - 2020年7月3日
excerpt: Safari 14 测试版发布说明; ECMAScript 提案：类中的私有静态方法和访问器
---

> 本技术日志，每周定期分享，欢迎关注、转发。

### 用可选链重构大型代码库的经验教训

**Mavo** 的作者 Lea Verou，决定使用可选链 `?.` 将 Mavo 重构一下，这里是她遇到的一些问题和总结。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image3.jpg)

[https://lea.verou.me/2020/06/refactoring-optional-chaining-into-a-large-codebase-lessons-learned/](https://lea.verou.me/2020/06/refactoring-optional-chaining-into-a-large-codebase-lessons-learned/)

### Safari 14 测试版发布说明

Safari 14 将于今年晚些时候与 iOS 14 和 macOS 11 一起发布。以下是一些主要的更新功能：

* 添加对 WebP 图像和 HDR 视频播放的支持；
* 支持 HTTP/3；
* 抛弃 Flash；
* 将同时支持 `:is()`和  `:where()` 伪类选择器；
* 在 macOS 的版本上支持 Web 扩展

[https://developer.apple.com/documentation/safari-release-notes/safari-14-beta-release-notes](https://developer.apple.com/documentation/safari-release-notes/safari-14-beta-release-notes)

### ECMAScript 提案：类中的私有静态方法和访问器

一个即将发布的语言功能，该功能处于第 3 阶段，目前已经得到了 Babel 等工具的支持。

[https://2ality.com/2020/06/private-static-methods-accessors-in-classes.html](https://2ality.com/2020/06/private-static-methods-accessors-in-classes.html)

## 文章和教程

### 少量原生 JavaScript 也可以做很多事情

[https://jvns.ca/blog/2020/06/19/a-little-bit-of-plain-javascript-can-do-a-lot/](https://jvns.ca/blog/2020/06/19/a-little-bit-of-plain-javascript-can-do-a-lot/)

### TypeScript 4 会带来什么？

[https://httptoolkit.tech/blog/whats-coming-in-typescript-4/](https://httptoolkit.tech/blog/whats-coming-in-typescript-4/)

### CSS《疯狂杂志》折叠效果

[https://thomaspark.co/2020/06/the-mad-magazine-fold-in-effect-in-css/?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter](https://thomaspark.co/2020/06/the-mad-magazine-fold-in-effect-in-css/?utm_campaign=CSS Animation Weekly&utm_medium=email&utm_source=Revue newsletter)

### 滚动技术概述

[https://css-tricks.com/an-overview-of-scroll-technologies/](https://css-tricks.com/an-overview-of-scroll-technologies/)

### CSS 影印杂志效果

[https://codepen.io/lynnandtonic/pen/YzwVJYp](https://codepen.io/lynnandtonic/pen/YzwVJYp)

### WebP 真的比 JPEG 好吗？

[https://siipo.la/blog/is-webp-really-better-than-jpeg](https://siipo.la/blog/is-webp-really-better-than-jpeg)

### 了解 JavaScript 中的生成器

[https://www.taniarascia.com/understanding-generators-in-javascript/](https://www.taniarascia.com/understanding-generators-in-javascript/)

## 实用工具

### Tabulator 4.7

一个交互式表格和数据网格库。支持所有主流浏览器，也可以和 Angular，Vue 和 React 框架一起使用。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image4.jpg)

[http://tabulator.info/](http://tabulator.info/)

### Basic.css

一套无类的，可提供基本的 CSS 格式，并且仅使用 HTML5 语法即可创建基本的网格。也可使用它来设置默认样式。

[https://github.com/vladocar/Basic.css](https://github.com/vladocar/Basic.css)

### knopf.css

一个现代的、模块化的和可扩展的 CSS 库，可以轻松地构建一组多样化的按钮样式。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image2.png)

[https://knopf.dev/](https://knopf.dev/)

### Vuesax

一套基于 Vue 的组件库，设计还是蛮精美的。

[https://vuesax.com/](https://vuesax.com/)

### React Query 2

一套用于获取、缓存和更新异步数据的 React Hooks。

[https://github.com/tannerlinsley/react-query](https://github.com/tannerlinsley/react-query)

### useReactiveForm

一个 React Hook，用于收集和验证表单数据，而无需重新渲染。

[https://github.com/Michaeladze/useReactiveForm](https://github.com/Michaeladze/useReactiveForm)

#### React Placeholder

一个 React 组件，可以在内容加载时，非常方便的用漂亮的占位复制你的页面。

[https://github.com/buildo/react-placeholder](https://github.com/buildo/react-placeholder)

### React PDF Reader

一个可充当 PDF 阅读器的 React 组件，基本属于 Mozilla 的 PDF.js 库的 React 包装器。

[https://github.com/ZEISS/react-view-pdf](https://github.com/ZEISS/react-view-pdf)

### react-simple-keyboard

一个虚拟键盘 React 组件，可定制，且响应迅速轻巧

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image1.png)

[https://github.com/hodgef/react-simple-keyboard](https://github.com/hodgef/react-simple-keyboard)

### Rando.js

一个随机函数库，可以获取一个范围内的随机整数、浮点数，还可从给定项中返回随机元素等。

[https://github.com/nastyox/Rando.js](https://github.com/nastyox/Rando.js)

## 内容来源

- [Frontend Focus](https://frontendfoc.us/): *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/): *https://javascriptweekly.com/*
- [Web Tools Weekly](https://webtoolsweekly.com/): *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/): *https://weekly.cssanimation.rocks/*

关注公众号，关注前端技术

![赵不寒的网络日记](/assets/qrcode-clean.jpg)

