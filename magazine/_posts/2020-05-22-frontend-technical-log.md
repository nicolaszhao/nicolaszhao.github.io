---
layout: post
title: 前端技术日志 - 2020年5月22日
excerpt: Deno 1.0 发布; npm v7; ESLint v7.0 发布; Next.js 9.4
---

> 本技术日志，每周定期分享，欢迎关注、转发。

### Deno 1.0 发布

Node.js 的创建者 Ryan Dahl 又出新作品了，在 2 年前他曾经提到过，如今已经准备就绪，至少你可以试一试。Deno ”无毒无害“、安全第一、无 NPM。

[https://deno.land/v1](https://deno.land/v1)

### Firefox 即将推出进程管理器

Mozilla 正在致力于将进程管理器集成到 Firefox 中，以提供详细的进程信息。

[https://www.ghacks.net/2020/05/11/this-is-firefoxs-upcoming-process-manager-aboutprocesses/](https://www.ghacks.net/2020/05/11/this-is-firefoxs-upcoming-process-manager-aboutprocesses/)

### TypeScript 3.9

3.9 提供了各种编辑器的改进、性能改进，以及对推断和 `Promise.all` 的调整。

[https://devblogs.microsoft.com/typescript/announcing-typescript-3-9/](https://devblogs.microsoft.com/typescript/announcing-typescript-3-9/)

### npm v7 的初次介绍

Github 被收购后，npm 将发布下一个主要版本的更新。这里介绍新的 npm 将提供的功能，Isaac Schlueter 表示，之后将会发布一系列帖子，以更详细的介绍。

[https://blog.npmjs.org/post/617484925547986944/npm-v7-series-introduction](https://blog.npmjs.org/post/617484925547986944/npm-v7-series-introduction)

### ESLint v7.0 发布

新版本的 ESLint 已不再支持 Node 8。

[https://eslint.org/blog/2020/05/eslint-v7.0.0-released](https://eslint.org/blog/2020/05/eslint-v7.0.0-released)

### React 驱动的网站构建框架 Next.js 9.4 发布

全新的“瞬时” 热重载体验，增强增量静态生成，当有流量访问时，可在后台生成或重新渲染。

[https://nextjs.org/blog/next-9-4](https://nextjs.org/blog/next-9-4)

### Bootstrap 4.5.0 发布

[https://blog.getbootstrap.com/2020/05/12/bootstrap-4-5-0/](https://blog.getbootstrap.com/2020/05/12/bootstrap-4-5-0/)

## 文章和教程

### 深入了解 CSS 包含属性

这是对 CSS 新属性的全面介绍，该属性浏览器支持性很不错，可帮助浏览器更有效地计算页面布局。

[https://css-tricks.com/lets-take-a-deep-dive-into-the-css-contain-property/](https://css-tricks.com/lets-take-a-deep-dive-into-the-css-contain-property/)

### Facebook 是如何为 Facebook.com 重建技术栈的

Facebook 完全重建了它的技术栈，以实现其性能和增长目标。这是关于他们如何使用 React、Relay、SVG，以及代码拆分等，对 facebook.com 进行技术改造的。

[https://engineering.fb.com/web/facebook-redesign/](https://engineering.fb.com/web/facebook-redesign/)

### 如何把滚动百分比显示在标题栏

这是一个巧妙的小把戏。使用 React 和 Gatsby 在浏览器标题栏/选项卡中显示您阅读（滚动）的页面量。

[https://www.knutmelvaer.no/blog/2020/05/how-i-put-the-scroll-percentage-in-the-title-bar/](https://www.knutmelvaer.no/blog/2020/05/how-i-put-the-scroll-percentage-in-the-title-bar/)

### 通过 Firefox DevTools 中的无效 CSS 规则指示器了解 CSS 为什么无效

这是个很棒的小功能，已经发布几个月了，推荐大家试一下。它使无效的 CSS 声明变成灰色，提供有关错误的提示，给出了解决建议，并提供了有用的链接以获取更多信息。

[https://elijahmanor.com/firefox-devtools-inactive-css/](https://elijahmanor.com/firefox-devtools-inactive-css/)

## 实用工具

### pwa-install

一个来自 [PWABuilder](https://pwabuilder.com/) 团队的 Web 组件，可以改进你的 PWA “安装” 体验，类似于在应用商店安装应用一样。

[https://github.com/pwa-builder/pwa-install](https://github.com/pwa-builder/pwa-install)

### CSS 截面分隔生成器

一种简单且有交互式的生成器，用于向页面添加花哨的截面分隔符。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image1.png)

[https://wweb.dev/resources/css-separator-generator](https://wweb.dev/resources/css-separator-generator)

### postcss-px-to-viewport

一个流行的 PostCSS 的插件，用来转换 px 单位为视口单位（vw, vh, vmin, vmax）。

[https://github.com/evrone/postcss-px-to-viewport](https://github.com/evrone/postcss-px-to-viewport)

### pattern.css

一个纯 CSS 图案库，非常漂亮，可用来填充你的页面背景。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image2.png)

[https://bansal.io/pattern-css](https://bansal.io/pattern-css)

### 图像颜色选取器

一个在线的图像颜色选取工具。你可以上传一个图像或提供图像 URL，把你的鼠标悬停在嵌入的图像上时，会自动选取图像的颜色。

[https://imagelr.com/](https://imagelr.com/)

### Vershd

一个创新的、流畅的 Git GUI，让你的 Git 使用更加容易，可以大大简化整个 Git 流程。

[https://vershd.io/](https://vershd.io/)

### a-Shell

它是一个 iOS 应用程序，称为"口袋中的终端"，可在手机上控制文件、网络连接、编写代码等，是不是很“黑客”！

[https://holzschu.github.io/a-Shell_iOS/](https://holzschu.github.io/a-Shell_iOS/)

## 内容来源

- [Frontend Focus](https://frontendfoc.us/): *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/): *https://javascriptweekly.com/*
- [Responsive Design Weekly](https://responsivedesign.is/): *https://responsivedesign.is/*
- [Web Tools Weekly](https://webtoolsweekly.com/): *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/): *https://weekly.cssanimation.rocks/*

关注公众号，关注前端技术

![赵不寒的网络日记](/assets/qrcode-clean.jpg)

