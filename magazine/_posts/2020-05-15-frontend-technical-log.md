---
layout: post
title: 前端技术日志 - 2020年5月15日
excerpt: Jest 26 发布; CSS 盒模型4的草案发布; Web Vitals 的介绍; Firefox 76
---

> 本技术日志，每周定期分享，欢迎关注、转发。

### Jest 26 发布

 Jest 是一个流行的测试框架，该版本主要减少了依赖项的安装和安装包的大小。另外还有，一个新的伪计时器的实现，放弃了 Node 8 的支持，以及最初实验性的 ESM 支持。

[https://jestjs.io/blog/2020/05/05/jest-26](https://jestjs.io/blog/2020/05/05/jest-26)

### CSS 盒模型 4 的草案

CSS 工作组发布了第一个公开的 CSS 盒模型 4 的工作草案。两个主要的变化是引入 `margin-trim` 属性和与书写模式相关的内容。

[https://www.w3.org/blog/news/archives/8452](https://www.w3.org/blog/news/archives/8452)

### Firefox 76：音频工作包和其他特性

Web 平台的支持在此版本中增加了一些很棒的新功能，例如 JavaScript 方面的 Audio Worklets 和 `Intl` 的改进，还有 DevTools 中的改进。

[https://hacks.mozilla.org/2020/05/firefox-76-audio-worklets-and-other-tricks/](https://hacks.mozilla.org/2020/05/firefox-76-audio-worklets-and-other-tricks/)

### Web Vitals 的介绍：健康网站的基本指标

*Web Vitals* 是 Google 的一项新举措，旨在提供有关质量信号（例如首次输入延迟，加载速度等）的指南，这些信号对于在网络上提供良好的用户体验至关重要。

[https://blog.chromium.org/2020/05/introducing-web-vitals-essential-metrics.html](https://blog.chromium.org/2020/05/introducing-web-vitals-essential-metrics.html)

## 文章和教程

### ES2020 之 `Promise.any`

[https://mariosfakiolas.com/blog/es2020-promise-any/](https://mariosfakiolas.com/blog/es2020-promise-any/)

### 纯 CSS 游戏

用 JavaScript 开发的游戏见多了，纯 CSS 的见过没？

[https://medium.com/cssclass-com/how-to-create-pure-css-games-2a29c777bf4](https://medium.com/cssclass-com/how-to-create-pure-css-games-2a29c777bf4)

### 有关 CSS 的文本选择

一篇有关 CSS 文本选择的研究，涵盖了 `::selection` 伪元素和 `user-select` 属性。

[https://ishadeed.com/article/selection-in-css/](https://ishadeed.com/article/selection-in-css/)

### CSS 函数完全指南

这个指南非常详尽，几乎包括了 CSS 函数的所有知识。

[https://css-tricks.com/complete-guide-to-css-functions/](https://css-tricks.com/complete-guide-to-css-functions/)

### Canvas 引擎对比：PixiJS vs Two.js vs Paper.js 

这是个对三种流行 2D 渲染引擎的测试。请随时注意你的 CPU ^_^。

![Canvas 引擎对比](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image3.png)

[https://benchmarks.slaylines.io/](https://benchmarks.slaylines.io/)

## 实用工具

### NeutralinoJS

一个可以用 JS、HTML 和 CSS 构建跨平台应用的开发框架。类似于 Electron，但它更快更小，因为它未完全内置完整的浏览器。

[https://github.com/neutralinojs/neutralinojs](https://github.com/neutralinojs/neutralinojs)

### Majestic 1.7：一个 Jest 的零配置 GUI

一个可以简化你的 JavaScript 测试工作的工具。

[https://github.com/Raathigesh/majestic](https://github.com/Raathigesh/majestic)

### Selecto.js

Selecto.js 允许你可使用鼠标或触摸，在给定拖动区域内选择元素的一个组件。

![Selecto.js](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image4.png)

[https://github.com/daybrush/selecto](https://github.com/daybrush/selecto)

### Notyf

一个极小的（只有 3KB），用于 Toast 通知的 JavaScript 库。响应速度快、无障碍访问、无依赖，且易于和 React、Angular、Vue 集成。

[https://carlosroso.com/notyf/](https://carlosroso.com/notyf/)

### emoji-regex

一个很有意思的正则表达式匹配库，可以根据 Unicode 标准来匹配 emoji 符号(包括文本表示的表情符号)。

[https://github.com/mathiasbynens/emoji-regex](https://github.com/mathiasbynens/emoji-regex)

### Eruda

一个可以测试和调试移动浏览器的控制台工具，类似于 `vConsole`，但看起来更为专业，界面已经很接近 DevTools 了，就如它的迷你版一样。

[https://github.com/liriliri/eruda](https://github.com/liriliri/eruda)

### Will it CORS?

在线测试某个 URL 对 CORS 是否友好，比如，即可以安全发送，又可以读取响应。

[https://httptoolkit.tech/will-it-cors/](https://httptoolkit.tech/will-it-cors/)

### vue-virtual-scroll-list

一个 Vue 高性能长列表渲染组件，已更新到 v2.2 了。

[https://github.com/tangbc/vue-virtual-scroll-list](https://github.com/tangbc/vue-virtual-scroll-list)

## 内容来源

- [Frontend Focus](https://frontendfoc.us/): *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/): *https://javascriptweekly.com/*
- [Responsive Design Weekly](https://responsivedesign.is/): *https://responsivedesign.is/*
- [Web Tools Weekly](https://webtoolsweekly.com/): *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/): *https://weekly.cssanimation.rocks/*

关注公众号，关注前端技术

![赵不寒的网络日记](/assets/qrcode-clean.jpg)

