---
layout: post
title: 前端技术日志：2020年8月14日
excerpt: 你的开源项目，可能无意中会得到一笔额外的巨款捐赠！
---

> 本技术日志，每周定期分享，欢迎关注、转发。

### Salesforce 向 ESLint 项目捐款了 10,000 美元

### Google 正在测试“信任令牌”，以替代第三方广告 Cookie

### Angular 发布了未来规划路线图

[https://angular.io/guide/roadmap](https://angular.io/guide/roadmap)

### 低开销的 Node.js Web 框架 Fastify 3.2.0 发布

### 小型的纯 JavaScript 的 JS 解析器 Acorn 7.4.0 发布

## 文章教程

### 充分利用 Google 字体中的可变字体

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image5.gif)

[https://css-tricks.com/getting-the-most-out-of-variable-fonts-on-google-fonts/](https://css-tricks.com/getting-the-most-out-of-variable-fonts-on-google-fonts/)

### 使用 Canvas 模拟对象碰撞

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image1.png)

[https://joshbradley.me/object-collisions-with-canvas/?utm_campaign=CSS%20Animation%20Weekly&utm_medium=email&utm_source=Revue%20newsletter](https://joshbradley.me/object-collisions-with-canvas/?utm_campaign=CSS Animation Weekly&utm_medium=email&utm_source=Revue newsletter)

### 100% 在 CSS 中的含义

这是一篇讲述 CSS 百分比单位的文章，它用可视化的方式来讲解，让你一目了然。

[https://wattenberger.com/blog/css-percents](https://wattenberger.com/blog/css-percents)

### 表单设计最佳实践指南

[https://gerireid.com/forms.html](https://gerireid.com/forms.html)

### 使用 Promise 的 3 个常见错误

[https://dev.to/mpodlasin/3-most-common-mistakes-when-using-promises-in-javascript-oab](https://dev.to/mpodlasin/3-most-common-mistakes-when-using-promises-in-javascript-oab)

## 工具资源

### Inclusive Dates

一个人性化的日期选择库，允许用户使用自然语言短语（例如：“明天”、“下周”，或“在5天内”）选择日期。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image2.png)

[https://github.com/fymmot/inclusive-dates](https://github.com/fymmot/inclusive-dates)

### Super Expressive

一个零依赖的 JavaScript 库，用于以自然语言（语义化）的方式构建正则表达式。如果你对简洁神秘的正则表达式字符感到畏惧，那么可以尝试下这个库。

```js
const SuperExpressive = require('super-expressive');
const myRegex = SuperExpressive()
  .startOfInput
  .optional.string('0x')
  .capture
    .exactly(4).anyOf
      .range('A', 'F')
      .range('a', 'f')
      .range('0', '9')
    .end()
  .end()
  .endOfInput
  .toRegex();

// Produces the following regular expression:
/^(?:0x)?([A-Fa-f0-9]{4})$/
```

[https://github.com/francisrstokes/super-expressive](https://github.com/francisrstokes/super-expressive)

### Forge Icons

一个收集了 300+ 的 SVG 图标库网站，适合用于电商、旅游、社交类网站等。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image3.png)

[https://icons.theforgesmith.com/](https://icons.theforgesmith.com/)

### AudioMass

一个免费的基于 Web 的音频和波形编辑器，它完全在浏览器中运行，不需要后端或者插件支持。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image4.png)

[https://audiomass.co/](https://audiomass.co/)

### GitHub Profile README Generator

一个向导式的创建 Github 个人资料自述文件的生成器，懒人专属！

[https://rahuldkjain.github.io/gh-profile-readme-generator/](https://rahuldkjain.github.io/gh-profile-readme-generator/)

## 内容来源

- [Frontend Focus](https://frontendfoc.us/): *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/): *https://javascriptweekly.com/*
- [Web Tools Weekly](https://webtoolsweekly.com/): *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/): *https://weekly.cssanimation.rocks/*

关注公众号，关注前端技术

![赵不寒的网络日记](/assets/qrcode-clean.jpg)

