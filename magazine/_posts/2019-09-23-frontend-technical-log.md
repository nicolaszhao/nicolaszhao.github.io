---
layout: post
title: 前端技术日志 | 图解 CSS Grid
excerpt: 分享定期收集的前端前沿技术、文章、工具和资源。
---

> 本期刊专注于 Web 前端前沿技术，收集的内容来自于国外各大前端技术周刊，这里把自己感兴趣的，并值得分享的内容做了整理。

部分链接可能无法直接打开，你需要通过**科学上网**的方式来解决。

## 本期热文

### [图解 CSS Grid](https://dev.to/mustapha/css-grid-illustrated-introduction-52l5)

用详细的，直观地插图来掌握 CSS Grid。

*https://dev.to/mustapha/css-grid-illustrated-introduction-52l5*

*MUSTAPHA AOUAS*

### [使用 Tensorflow 让前端开发者进行机器学习](https://www.smashingmagazine.com/2019/09/machine-learning-front-end-developers-tensorflowjs/)

*Charlie Gerard* 介绍了如何使用 JavaScript 和 Tensorflow.js 之类的框架开始机器学习，并着重介绍了在前端进行机器学习的局限性。

*https://www.smashingmagazine.com/2019/09/machine-learning-front-end-developers-tensorflowjs/*

*SMASHING MAGAZINE*

### [Firefox 进入更快的 4 周发布周期](https://hacks.mozilla.org/2019/09/moving-firefox-to-a-faster-4-week-release-cycle/)

我们只需不到几年的时间就能达到 Chrome 100，而 Firefox 似乎也希望采取行动， Firefox 的发布节奏从 Firefox 71 开始，将从每个版本大约 6-8 周调整为 4 周。

https://hacks.mozilla.org/2019/09/moving-firefox-to-a-faster-4-week-release-cycle/

*MOZILLA HACKS*

### [为什么 `0.1 + 0.2 === 0.30000000000000004`：在 JS 中实现 IEEE 754](https://www.youtube.com/watch?v=wPBjd-vb9eI)（视频）

访问您的 JavaScript 控制台，然后输入 `0.1 + 0.2`。 如果答案使你感到困惑，那么你可以在这个视频中找到答案。

*https://www.youtube.com/watch?v=wPBjd-vb9eI*

*LOW LEVEL JAVASCRIPT*

### [维基百科在有限开支下的 JavaScript 初始化](https://phabricator.wikimedia.org/phame/live/7/post/175/wikipedia_s_javascript_initialisation_on_a_budget/)

维基百科每分钟获得 363,000 次页面浏览， 本文介绍了他们如何将 JS 有效负载从 36kb 下降到 28kb，仅在文件上节省了 8kb，相当于每天节省 4.3 TB 流量。 这意味着，每天约相当于 30.4 吨的二氧化碳，或者 159,805 公里（绕地球 4 圈）的长途汽车旅行。

*https://phabricator.wikimedia.org/phame/live/7/post/175/wikipedia_s_javascript_initialisation_on_a_budget/*

### [Chrome 77 的新功能](https://developers.google.com/web/updates/2019/09/nic77)

从 Chrome 77 开始，在浏览器中内置了原生懒加载功能。 只要 `<img/>` 上增加 `loading="lazy"`，您的图片就只会在进入视口时加载。 视口的接近程度取决于以下几个因素：

1. 正在获取的资源类型（图像或 iframe）
2. 是否在 Android 版的 Chrome 上启用了精简模式
3. 有效连接类型

*https://developers.google.com/web/updates/2019/09/nic77*

## 文章 & 教程

### [如何分析 React App 的性能](https://kentcdodds.com/blog/profile-a-react-app-for-performance/)

了解如何使用 React DevTools 和 React 的 *profiling* 构建来开始对生产应用进行性能分析。

*https://kentcdodds.com/blog/profile-a-react-app-for-performance/*

*KENT C DODDS*

### [`Console.log()` —调试时应使用的 8 种方法](https://t.co/HSVgSHEPVV)

其中包括了 `console.assert`，`console.count`，`console.group` 和两种计时方法。

*https://t.co/HSVgSHEPVV*

*MARCO ANTONIO GHIANI*

### [4 个迭代器和生成器的指南](https://jfet97.github.io/JavaScript-Iterators-and-Generators/)

*https://jfet97.github.io/JavaScript-Iterators-and-Generators/*

*ANDREA SIMONE COSTA*

### [从 jQuery 转换为普通 JavaScript 的备忘清单](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/)

*https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/*

*TOBIAS AHLIN*

### [使用 CSS 变量的逻辑运算](https://css-tricks.com/logical-operations-with-css-variables/)

如何通过 `calc()` 函数使用算术运算在 CSS 中模拟 `not(var(—i))` 之类的函数。

*https://css-tricks.com/logical-operations-with-css-variables/*

*ANA TUDOR*

### [如何安置表单按钮](https://adamsilver.io/articles/where-to-put-buttons-in-forms/)

好的表单设计非常困难。该教程专门研究按钮的位置，以及创建它们的最佳方法。

*https://adamsilver.io/articles/where-to-put-buttons-in-forms/*

## 工具 & 资源

### [Sortable 1.10](https://sortablejs.github.io/Sortable/)

一个可重新排序的拖放列表。在触摸屏和现代浏览器上表现良好，可在列表间拖动项目、定义拖动手柄，可用于 Angular 和 React。

*https://sortablejs.github.io/Sortable/*

*SORTABLE*

### [Vue Select](https://vue-select.org/)

Vue 的一个功能丰富的 `<select>` 组件

*https://vue-select.org/*

*JEFF SAGAL*

### [Emittery](https://github.com/sindresorhus/emittery)

一个简单的现代异步事件发射器。

*https://github.com/sindresorhus/emittery*

*SINDRE SORHUS*

### [HTML Minifier](http://kangax.github.io/html-minifier/)

一个高度可配置化的，基于 JavaScript 的 HTML 压缩程序。已更新到版本 4+

*http://kangax.github.io/html-minifier/*

### [MySigMail Card](https://landing.card.mysigmail.com/)

一个无需编码和设计，可拖放式的电子邮件模板构建器。

*https://landing.card.mysigmail.com/*

### [React Spaces](https://github.com/aeagle/react-spaces)

可以让你将页面或容器划分为可嵌套的锚定，或可滚动和可调整大小的空间的 React 组件。

*https://github.com/aeagle/react-spaces*

### [React 数据表格组件](https://github.com/jbetancur/react-data-table-component)

一个简单的，可排序的，灵活的 React 表格库。

*https://github.com/jbetancur/react-data-table-component*

### [react-textarea-autocomplete](https://github.com/webscopeio/react-textarea-autocomplete)

增强的 `textarea`，用于自动完成功能，例如在 GitHub 注释中（比如：表情符号 和 @）。

*https://github.com/webscopeio/react-textarea-autocomplete*

## 创意

### [ThreeJS Moon](https://codepen.io/g12n/pen/vYBryJW?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter)

NASA 科学可视化工作室创造的月亮纹路。基于月球表面的真实照片，并使用 ThreeJS 处理的动画。

![ThreeJS Moon](/assets/post-images/2019-09-23/1.gif)

*https://codepen.io/g12n/pen/vYBryJW?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter*

### [具有悬浮效果的 CSS 按钮](https://codepen.io/JeremyWink/pen/LYPMLLV?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter)

![具有悬浮效果的 CSS 按钮](/assets/post-images/2019-09-23/2.gif)

*https://codepen.io/JeremyWink/pen/LYPMLLV?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter*

## 版本发布

* [Relay 6.0](https://github.com/facebook/relay) — 用于构建数据驱动的 React 应用程序的框架，*https://github.com/facebook/relay*
* [PapaParse 5.1](https://github.com/mholt/PapaParse/releases/tag/5.1.0) — CSV 快速解析器，*https://github.com/mholt/PapaParse/releases/tag/5.1.0*
* [Glide 3.4](https://github.com/glidejs/glide) — 无依赖的滑块和轮播，*https://github.com/glidejs/glide*
* [ESLint 6.4.0](https://eslint.org/blog/2019/09/eslint-v6.4.0-released)，*https://eslint.org/blog/2019/09/eslint-v6.4.0-released*

## 内容来源

- [Frontend Focus](https://frontendfoc.us/), *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/), *https://javascriptweekly.com/*
- [Responsive Design Weekly](https://responsivedesign.is/), *https://responsivedesign.is/*
- [Web Tools Weekly](https://webtoolsweekly.com/), *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/), *https://weekly.cssanimation.rocks/*

## 往期回顾

* [2019 年最佳的 10 个 CSS 框架](/magazine/2019/09/17/frontend-technical-log.html)
* [D3.js 简介](/magazine/2019/09/11/frontend-technical-log.html)
* [JavaScript 是如何成长并成为一门“真正的”语言的](/magazine/2019/09/04/frontend-technical-log.html)

关注我的公众号，关注前端技术

![赵不寒的网络日记](/assets/qrcode-clean.jpg)
