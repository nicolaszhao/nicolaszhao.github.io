---
layout: post
title:  移动端调试利器：spy-debugger
---

最近，有很多 H5 页面的奇怪问题需要修复，它们在公司的各种移动端 App 内的 webview 中访问。要在 Android 中调试的页面（比如：[chrome://inspect](chrome://inspect)），需要进入 App 中隐藏的调试入口，并开启开发调试，步骤繁琐而冗长。而 iOS 设备，要在 Safari 中调试，需要客户端同学单独为你打个包。而调试前的准备工作也非常惊险，不同的设备，设置项可能要找半天。

除了上面的线上问题，平时在开发过程中，需要调试特殊机型的兼容性问题时，也没有那么轻松。一般情况下，我们都使用 Charles 来开启代理，并在移动端调试本地页面。当需要解决些疑难杂症时，大多都是通过 `alert` 来弹出调试日志，或者借助可以注入到页面的第三方调试组件，但都非常麻烦，调试非常费时。

今天发现个非常好用的调试工具——spy-debugger，安装把玩了一下，觉得非常不错，虽然已经上线挺久了，可我最近才使用上，很值得再推荐一下。

[spy-debugger](https://github.com/wuchangming/spy-debugger) 是一个不需要 USB 连接设备的页面调试、抓包工具，直接通过命令行启动。可以远程调试任何手机的浏览器页面，甚至包括移动端中 webview 的页面，而启用 https 的抓包功能也相当简单。下面来简单介绍一下 [spy-debugger](https://github.com/wuchangming/spy-debugger)  的安装和基本使用。

## 安装

因为 [spy-debugger](https://github.com/wuchangming/spy-debugger)  是基于 NodeJS 实现的，可以直接通过 NPM 来全局安装：

```shell
$ npm i -g spy-debugger
```

## 使用

[官方文档](https://github.com/wuchangming/spy-debugger)的上手步骤只需 5 步，但熟悉移动端代理调试的我们，只需要关注输入命令之后的提示：

```
$ spy-debugger
正在启动代理
本机在当前网络下的IP地址为：10.xx.xx.xx
node-mitmproxy启动端口: 9888
浏览器打开 ---> http://127.0.0.1:63637
```

然后，根据提示信息，设置好移动设备的网络代理，然后在手机上的 App 中访问你要调试的页面。

在输入命令后，在 chrome 中自动打开的页面，就像 Chrome 的 devTool 工具。你可以看到你手机上访问的页面的所有信息，包括 JavaScript 错误堆栈和输出的 `console.log` 调试日志都可以在控制台中查看。

另外，为了更方便的在手机上调试本地开发环境的页面，还可以结合 Charles 一起使用：

```shell
$ spy-debugger -e http://127.0.0.1:8888
```

设置好后，打开 Charles。这可以用来调试 Map remote 之后的页面，比如用 Charles 把 `localhost:3003` map 到一个自定义域名：`local.com` 上，用手机访问的时候就会非常方便。

更多详细功能，可以阅读 spy-debugger 的[官方文档](https://github.com/wuchangming/spy-debugger)。

其他相关工具：[whistle](https://github.com/avwo/whistle)