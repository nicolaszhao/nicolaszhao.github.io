---
layout: post
title: 前端技术日志|在生产环境中使用原生 JavaScript 模块
excerpt: 分享定期收集的前端前沿技术、文章、工具和资源。
---

> 本期刊专注于 Web 前端前沿技术，收集的内容来自于国外各大前端技术周刊，这里把自己感兴趣的，并值得分享的内容做了整理。
> 部分链接可能无法直接打开，你需要通过**科学上网**的方式来解决。

## 本期热文

### [在生产环境中使用原生 JavaScript 模块](https://philipwalton.com/articles/using-native-javascript-modules-in-production-today/)

归功于打包技术的发展，现在，你可以将生产代码部署为 ES2015 模块了——包括静态和动态导入，而且比目前的非模块方式能获得更好的性能。

*https://philipwalton.com/articles/using-native-javascript-modules-in-production-today/*

*PHILIP WALTON*

### [Web Template Studio 2.0](https://blogs.windows.com/windowsdeveloper/2019/08/21/growing-web-template-studio/)

Web Template Studio 是来自微软的 Visual Studio Code 的一个扩展，可以从 VS Code 以“向导”式风格生成新的全栈应用程序。 支持 Angular，Vue 和 React。

*https://blogs.windows.com/windowsdeveloper/2019/08/21/growing-web-template-studio/*

*LEA AKKARI (MICROSOFT)*

### [2019年8月的 JavaScript 框架状态](https://www.youtube.com/watch?v=6Ievupll1ng)（视频）

每隔半年，*Tracy Lee* 就会与几位不同框架的代表坐下来，来简单了解他们的工作状况。这一小时的剧集包含了 *Evan You*（Vue.js），*Minko Gechev*（Angular），*Michael Dawson*（Node.js），*Jen Weber*（Cardstack），*Manu Mtz.-Almeida*（Ionic）和 *Marvin Hagemeister*（Preact）。

*https://www.youtube.com/watch?v=6Ievupll1ng*

*TRACY LEE*

### [你应该知道的 React 中的 JavaScript](https://kentcdodds.com/blog/javascript-to-know-for-react)

在学习和使用 React 时，您应该要熟悉的 JavaScript 特性示例。

*https://kentcdodds.com/blog/javascript-to-know-for-react*

*KENT C DODDS*

### [Node v12.9.0 发布，推出了 V8 7.6](https://nodejs.org/en/blog/release/v12.9.0/)

升级到 V8 7.6 后开辟了一些新机会，比如 `Promise.allSettled()`、`JSON.parse` 和 frozen/sealed 的数组性能改进，`BigInt` 现在有一个 `toLocaleString` 的方法可用于大数字的本地格式化。

*https://nodejs.org/en/blog/release/v12.9.0/*

*NODE.JS FOUNDATION*

### [微软推出“可供日常使用”的基于 Chrome 的 Edge 浏览器的测试版](https://blogs.windows.com/windowsexperience/2019/08/20/introducing-microsoft-edge-beta-be-one-of-the-first-to-try-it-now/)

适用于 Windows 和 macOS ，这个 Edge 的测试版，是微软基于 Chromium 的新浏览器的第三个也是最后一个预览版本，尽管微软宣布它已经为这个版本做好了“可供日常使用”的准备。 它还包括与 IE 11 兼容的“ Internet Explorer 模式”。现在是时候测试它的性能了。

*https://blogs.windows.com/windowsexperience/2019/08/20/introducing-microsoft-edge-beta-be-one-of-the-first-to-try-it-now/*

*JOE BELFIORE (MICROSOFT)*

### [谷歌将在 Chrome 中弃用 FTP 的支持](https://www.neowin.net/news/google-chrome-82-will-remove-ftp-support-set-to-affect-01-of-users)

82 版本将在 2020 年的第二季度发布，所有 FTP 的支持将会从 Chrome 中移除。 预计这一改动将会影响约 0.1％ 的用户，但如果你现在仍然仅以 FTP 的形式提供下载，那么现在是时候升级一下了。

*https://www.neowin.net/news/google-chrome-82-will-remove-ftp-support-set-to-affect-01-of-users*

*PAUL HILL*

### [可选的 HTML：您需要知道的一切](https://meiert.com/en/blog/optional-html/)

虽然您可以从页面中省略某些 HTML，但这是一种我从根本上就反对的方法。 一些 HTML 标签，例如 `<body>` `<head>` `</li>` 等等，对于文档在浏览器中的正确呈现不是必须的，但它们为我们提供了基于网页如何组合的基本构建块和规则。 我知道省略的每个字符在技术上都会有助于提高性能，但也有助于提供一种标准的方法来构建我们都可以遵循它们的页面。 除此之外，确实有更好的方法来改善您的网站性能。

*https://meiert.com/en/blog/optional-html/*

*JENS OLIVER MEIERT*

### [iframes 太糟糕了，来让我们看看如何让他们进行改进](https://medium.com/@bluepnume/iframes-are-just-terrible-heres-how-they-could-be-better-974b731f0fb4)

PayPal 的首席工程师 *Daniel Brian* 强调了使用 `<iframe>` 的一些问题。 “我真的希望浏览器厂商开始将基于用户界面的 iframe 视为网络上的一等公民，并帮助修复现在还不可聚合的一些问题。”

*https://medium.com/@bluepnume/iframes-are-just-terrible-heres-how-they-could-be-better-974b731f0fb4*

*DANIEL BRAIN*

### [沉浸式 Web 的自定义元素](https://blog.mozvr.com/custom-elements-for-the-immersive-web/)

介绍两个为 360° 图像和视频而设计的新的自定义元素：`<img-360>` 和 `<video-360>`。

*https://blog.mozvr.com/custom-elements-for-the-immersive-web/*

*FERNANDO SERRANO*

## 文章 & 教程

### [ES2019 新特性](https://css-tricks.com/all-the-new-es2019-tips-and-tricks/)

新版ES2019功能的可访问，以及示例的重点综述。

*https://css-tricks.com/all-the-new-es2019-tips-and-tricks/*

*LAURIE BARTH*

### [高效的加载第三方 JavaScript](https://web.dev/efficiently-load-third-party-javascript/)

如何在使用第三方脚本时，避免常见陷阱，以改善加载时间和用户体验。

*https://web.dev/efficiently-load-third-party-javascript/*

*MILICA MIHAJLIJA*

### [为什么 ``('b'+'a'+ + 'a' + 'a').toLowerCase()`` 会返回  ``banana``？](https://stackoverflow.com/questions/57456188/why-is-the-result-of-ba-a-a-tolowercase-banana)

*https://stackoverflow.com/questions/57456188/why-is-the-result-of-ba-a-a-tolowercase-banana*

*STACK OVERFLOW*

### [使用生成器进行深度递归](https://jasonhpriestley.com/array-distance-and-recursion)

*https://jasonhpriestley.com/array-distance-and-recursion*

*JASON H PRIESTLY*

### [CSS Grid 的三种编写方法](https://www.viget.com/articles/getting-started-with-css-grid-three-part-2/?mc_cid=a649c756ce&mc_eid=e1e4216411)

用 Grid 的灵活语法，手把手的教你理解和构建二维布局。

*https://www.viget.com/articles/getting-started-with-css-grid-three-part-2/?mc_cid=a649c756ce&mc_eid=e1e4216411*

### [CSS 居然可以做到这一点…… 真是太可怕了](https://www.aaron-powell.com/posts/2019-08-14-css-can-do-this-and-its-terrifying/)

好奇地看一下你可以用 CSS 做的一些事情，也许你不应该这么做（比如密钥记录和用户跟踪）。

*https://www.aaron-powell.com/posts/2019-08-14-css-can-do-this-and-its-terrifying/*

*AARON POWELL*

### [JavaScript 中的作用域](https://www.youtube.com/watch?v=5LEuJNLfLN0)（视频）

如果您喜欢深入了解原生 JavaScript 的特性，那么您一定会感谢 Chrome 开发团队（特别是 HTTP 203 节目的 Jake 和 Surma）制作的视频。

*https://www.youtube.com/watch?v=5LEuJNLfLN0*

### [你为什么不需要 Utility-First CSS 的 BEM](https://www.youtube.com/watch?v=ab8RePo5ZYU)（视频）

*https://www.youtube.com/watch?v=ab8RePo5ZYU*

*ADAM WATHAN*

### [内容团队的可访问性策略](https://www.deque.com/blog/accessibility-strategies-for-your-content-team/?mc_cid=a649c756ce&mc_eid=e1e4216411)

无障碍对任何网站都非常重要。这篇来自 *Caitlin* 的文章涵盖了书面内容、链接文本、图像、缩写、语言、布局、题目、页面标题、PDF 等内容的可访问性。

*https://www.deque.com/blog/accessibility-strategies-for-your-content-team/?mc_cid=a649c756ce&mc_eid=e1e4216411*

### [4 个直观的用户体验规则](https://learnui.design/blog/4-rules-intuitive-ux.html?mc_cid=a649c756ce&mc_eid=e1e4216411)

不要再费心做大量的用户研究了，只要遵循这四个简单的规则，就可以获得更好的用户体验。

*https://learnui.design/blog/4-rules-intuitive-ux.html?mc_cid=a649c756ce&mc_eid=e1e4216411*

## 工具和资源

### [Reactide](https://reactide.io/)

为 React Web 应用程序开发的第一个专用 IDE，现在更新到 3+ 版本。

*https://reactide.io/*

### [Svelte-adapter](https://github.com/pngwn/svelte-adapter)

一个简单的实用工具，允许您在 React 或 Vue 组件中使用 Svelte 组件。

*https://github.com/pngwn/svelte-adapter*

### [NodeGUI](https://blog.atulr.com/nodegui-intro/)

一个类似于 Electron 的，使用 JavaScript 构建原生桌面应用的新工具，不过他更像是一个跨平台的部件工具包。

*https://blog.atulr.com/nodegui-intro/*

*ATUL R*

### [TSDoc](https://github.com/Microsoft/tsdoc)

TypeScript 的 doc 注释标准。 关于标准化 TypeScript 源文件中使用的 doc 注释的提议。 它允许不同的工具从注释中提取内容，而不会混淆彼此的语法。

*https://github.com/Microsoft/tsdoc*

### [pagemap](https://larsjung.de/pagemap/)

生成网页的“迷你地图”，在长页面上特别有用。 这会将整个页面的可点击/可导航概览添加到右上角。

*https://larsjung.de/pagemap/*

*LARS JUNG*

### [Quicklink](https://github.com/GoogleChromeLabs/quicklink)

通过预取可见链接加快后续页面加载的工具库，它旨在通过在空闲时间预取当前视口中的链接来更快地进行后续页面的加载。

*https://github.com/GoogleChromeLabs/quicklink*

*GOOGLE CHROME LABS*

### [date-fns 2.0](https://github.com/date-fns/date-fns)

一个类似于 Lodash 的日期工具库，它提供了广泛且一致 API，可以用于浏览器和 Node。 在进行 tree-shaking 和压缩后，date-fns 比 moment.js 更紧凑。

*https://github.com/date-fns/date-fns*

*DATE-FNS*

### [Codelines](https://codelines.dev/)

一个 VSCode 扩展，允许您通过将富文本与代码集成在 IDE 中创建编程文章。

*https://codelines.dev/*

### [Angular Console](https://marketplace.visualstudio.com/items?itemName=nrwl.angular-console)

VSCode 的 Angular 控制台。 Angular CLI 的用户界面应用程序。

*https://marketplace.visualstudio.com/items?itemName=nrwl.angular-console*

### [Angular Essentials](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials)

适用于 Angular 开发人员的 VSCode 扩展包。

*https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials*

### [Nx](https://nx.dev/angular/)

用于 monorepos 的一组可扩展开发工具，可帮助您构建使用 Angular 和 Node.js 框架的全栈应用程序（如 Nest 和 Express）。

*https://nx.dev/angular/*

### [file-type](https://github.com/sindresorhus/file-type)

可以用来检测 Buffer/Uint8Array 的文件类型，例如，可以从 PNG 文件中获取原始数据，然后它会告诉你是一个 PNG 文件。

*https://github.com/sindresorhus/file-type*

*SINDRE SORHUS*

### [extra.css](https://extra-css.netlify.com/)

一个 CSS Houdini 库，有很多有趣的效果。

*https://extra-css.netlify.com/*

*UNA KRAVETS*

### [Lexend](https://thomasjockin.github.io/lexend/)

一个为提高阅读效率而设计的可变字体。这个新的字体系列是建立在阅读能力之上的，现在已经可以在 Google 字体中使用 。

*https://thomasjockin.github.io/lexend/*

*THOMAS JOCKIN*

### [React 动态图表](https://dsternlicht.github.io/react-dynamic-charts/)

一个基于动态数据创建动画图表的可视化的 React 库。

*https://dsternlicht.github.io/react-dynamic-charts/*

### [Chart.xkcd](https://timqian.com/chart.xkcd/)

一个基于 SVG 的 JavaScript 图表库，用于绘制“写生风格”、“卡通”或“手绘”样式图表。

*https://timqian.com/chart.xkcd/*

### [jQuery-csv](https://github.com/typeiii/jquery-csv)

一个完整的，可定制的，经过实战考验，性能优化的 CSV 解析器，遵循传统的 jQuery 语法。

*https://github.com/typeiii/jquery-csv*

### [Isometric](https://isometric.online/)

一系列免费，美观，SVG 等距插图，您可以在您的网站，应用程序或任何项目中使用。

*https://isometric.online/*

## 版本发布

* [ESLint 6.2.1](https://eslint.org/blog/2019/08/eslint-v6.2.1-released)，https://eslint.org/blog/2019/08/eslint-v6.2.1-released

* [d3 5.10 和 5.11](https://github.com/d3/d3/releases/tag/v5.10.0)  -  JavaScript 数据可视化库，https://github.com/d3/d3/releases/tag/v5.10.0

* [vue-cli 3.11](https://github.com/vuejs/vue-cli)，https://github.com/vuejs/vue-cli

* [AVA 2.3](https://github.com/avajs/ava/releases/tag/v2.3.0)  -  Node 的流行测试运行器，https://github.com/avajs/ava/releases/tag/v2.3.0

* [Lounge 3.2](https://github.com/thelounge/thelounge/releases/tag/v3.2.0)  - 一个由 JavaScript 驱动的 IRC 客户端，https://github.com/thelounge/thelounge/releases/tag/v3.2.0

## 内容来源

- [Frontend Focus](https://frontendfoc.us/), *https://frontendfoc.us/*
- [JavaScript Weekly](https://javascriptweekly.com/), *https://javascriptweekly.com/*
- [Responsive Design Weekly](https://responsivedesign.is/), *https://responsivedesign.is/*
- [Web Tools Weekly](https://webtoolsweekly.com/), *https://webtoolsweekly.com/*
- [CSS Animation Weekly](https://weekly.cssanimation.rocks/), *https://weekly.cssanimation.rocks/*

## 往期回顾

[第 2 期在公众号中不显示]

* [前端技术日志 | 19年8月21日 | 新的 React DevTools 介绍]()

欢迎关注微信公众号：zhao-buhan，获得定期的技术日志推送。

![赵不寒的网络日记](https://upload-images.jianshu.io/upload_images/17058619-bc1496fde3fdd5ae.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

