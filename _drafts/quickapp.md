---
layout: post
title: 快应用上手简易指南
---

## 概述

快应用类似于微信小程序，但它的框架已被集成到手机操作系统，你不需要再安装额外的 App。

快应用开发标准，由国内安卓手机厂商大佬们制定，但只要你拥有前端技术的开发能力，就能够很快上手。

快应用具备如下特点：

> - 功能完备
> - 原生应用体验
> - 易于留存
> - 即点即用
> - 互联互通
> - 无版本碎片

## 创建项目

首先，你可以有 2 种方式来创建快应用项目：

1. 快应用开发工具
2. 命令行

### 快应用开发工具

用官方的开应用开发工具（IDE）创建项目比较简单，参考如下步骤：

1. [下载并安装 IDE](https://www.quickapp.cn/docCenter/post/97)
2. 打开后，点击左侧的“+”号图标按钮
3. 进入项目创建界面
4. 输入：项目路径、项目名称、应用名称和应用包名等信息
5. 等待自动打开新建的快应用工程

### 命令行

确保你的 NodeJS 版本是 8.0+ 的，推荐 10.0+，更快、更好、更稳定……

然后，你需要：

1、全局安装快应用命令行工具：

```
npm i -g hap-toolkit
```

2、用 `hap` 命令来创建一个项目模板：

```
hap init awesome-quick-app
```

3、安装 NPM 依赖：

```
npm i
```

### 开发与调试

推荐采用 VSCode（开发） + 快应用开发工具 IDE（调试），双剑合璧。

#### 开发

推荐安装 VSCode 对 `*.ux` 文件的语法高亮插件： `QuickApp for Highlighter`，当然，你也可以选择官方的 `Hap Extension`。但个人在使用中，发现 `Hap Extension` 会导致 VSCode 频频卡死的现象，当然你可以亲自尝试下。

官方 IDE 也不错，由于个人喜好，感觉 VSCode 更专业点，当然你可以自由选择。

#### 调试

快应用必须得真机调试。

调试前，请务必开启 `manifest.json` 中的日志输出配置：

```
"config": {
  "logLevel": "debug"
},
```

如果手机与电脑处于不同局域网内，需要开启快应用调试器的**开启 USB 调试**开关。

##### 自动模式

推荐使用快应用开发工具进行调试，你只需点击 IDE 左侧的“三角形”图标按钮，然后以下步骤会自动进行：

1. 检测并安装手机的：快应用预览版、快应用调试器、快应用调试内核
2. 开启调试服务器和代码更新的监听
3. 打开电脑端的调试窗口
4. 打开手机端的快应用

如果电脑端的调试窗口没有打开，你可以尝试点击 IDE 顶部的“刷新”图标按钮。

##### 手动模式

当然，如果你想要自由掌控，你也可以手动执行以上步骤来开启调试。

1、在手机上安装：[快应用调试器](https://www.quickapp.cn/docCenter/post/69)、[快应用预览版](https://www.quickapp.cn/docCenter/post/69)

2、开启调试服务器：

```shell
npm run server
```

3、自动编译项目并更新应用：

```shell
npm run watch
```

4、打开手机端的快应用调试器，扫码安装（同网），或者 USB 调试（非同网）

5、然后，点击**开始调试**按钮

因为，我是懒人，我还是比较喜欢自动调试模式！

### 测试与发布

#### 测试

进入测试流程，测试机同样需要安装：快应用调试器和快应用预览版。

然后执行如下命令来打一个测试包：

```shell
npm run build
```

测试包输出路径位于：`dist/<package>.debug.rpk`。

测试同学需要通过快应用调试器的“本地安装”按钮来安装这个 `rpk` 包。

#### 发布

如果你是第一次发布，你需要一个 release 签名证书，可以通过如下方式生成：

1. 打开开应用开发工具（IDE）
2. 点击左侧的“纸飞机”图标按钮，然后打开一个创建签名的窗口
3. 输入相关信息
4. 点击“完成”按钮，生成 release 签名
5. 最后会自动生成发布用的 `rpk` 包

发布包输出路径同测试包，输出后缀为 `*.release.rpk`。

如果你是第二次发布，直接执行如下命令即可生成发布包：

```shell
npm run release
```

注意，在生成发布包前，需要更新 `manifest.json` 的 2 个字段：`versionName` 和 `versionCode`，versionName 升级规则参考： [semver](<https://semver.org/lang/zh-CN/>)，versionCode 每次 release 时自增。

`hap` 命令行工具好像没有提供升级版本号的能力，你可以用 `shell` 自己写一个，比如：

```shell
sed -i '' "s/\(\"versionName\": *\).*/\1\"1.0.1\"/"
```

当然，上面代码中的 `1.0.1` 是需要写个逻辑来自动更新的，类似于 `npm version` 命令。

## 框架基本概念

### 基础目录结构

```
├── sign                      rpk 包签名模块
├── src
│   ├── Common                公用组件
│   ├── Home                  页面目录
│   |   └── index.ux          页面文件
│   ├── app.ux                APP 文件，可引入公共脚本，暴露公共数据和方法等
│   └── manifest.json         项目配置文件
└── package.json
```

### manifest.json

在配置文件中，你需要配置应用包名、版本信息、以及页面 UI 的显示样式等。

此外，所有用到的框架接口你需要在 `features` 字段中明确声明，否则会报错：

```
{
  "features": [{ "name": "system.fetch" }]
}
```

应用中用到的页面路由，也需要在配置文件中明确配置：

```
{	
	"router": {
    "entry": "Home",
    "pages": {
      "Home": {
        "component": "index"
      },
      "Detail": {
        "component": "index"
      }
    }
  }
}
```

### 应用入口： `app.ux`

在入口文件 `app.ux` 中可以用 2 个生命周期方法：`onCreate`、`onDestroy`。

也可以导入并暴露全局共享模块和方法。比如：

```js
// app.ux
import { method1, method2 } from 'someUtils';

export default {
  method1,
  method2
};

// home.ux
export default {
  onShow() {
    this.$app.$def.method1();
  }
};
```

如果调用的方法，会用到 `app` 实例中的属性，需要直接使用 `this.$app` 来调用：

```js
// app.ux
export default {
	onCreate() {
    this.name = 'Nicolas';
	},
  method3() {
    return this.name;
  }
};

// home.ux
export default {
  onShow() {
    this.$app.method3();
  }
};
```

此外，项目中有频繁用到的框架接口，可以在入口文件中导入并暴露到全局：

```js
// app.ux
import device from '@system.device';

export default {
  async getDeviceInfo() {
    try {
      const { data } = await device.getInfo();
      return data;
    } catch (err) {
      // 错误处理
    }
  },
};

// home.ux
export default {
  onShow() {
    this.$app.$def.getDeviceInfo().then((data) => {
      this.deviceInfo = data;
    });
  }
};
```

### 页面组件

类似于 Vue 和微信小程序，快应用的页面组件 `page.ux` 文件也分 3 个部分：`template`、`script` 和 `style`。

#### 模板

`template` 中除了事件方法的调用 `@event-name="handleEventName"`，其他一律用模板语法 `{{}}` 来解析 `ViewModel` 中的变量，包括：框架指令。

另外，文本内容只能出现在特定的组件中，比如： `text`、`span`、`label` 和 `a` 。

#### 数据模型

页面数据模型的声明分为 3 种：`public`，`protected` 和 `private`。

数据模型的声明类型，影响到页面之间传递数据的覆盖机制。`public` 和 `protected` 声明的数据可以被覆盖，只是，`protected` 只能被内部覆盖，比如：`router`，而 `public` 可以被外部覆盖，比如：Deeplink。

#### 生命周期

页面组件包括如下声明周期：

- `onInit`：`ViewModel` 的数据已可以使用，只执行一次
- `onReady`：可以获取 `DOM` 节点，只执行一次
- `onShow`：每次显示都执行，包括：从后台进程重新唤起、从另一个页返回等
- `onHide`：每次隐藏都执行，包括：隐藏到后台进程、打开另一个页等
- `onDestroy`：页面销毁时执行，如果这里包含了异步执行的逻辑，可能并不会执行
- `onBackPress`：返回 `true` 后可阻止返回（包括物理键和左上角返回键）
- `onMenuPress`

#### 样式和布局

页面样式统一使用 `border-box` 盒模型，和 `flex` 布局。你不需要额外声明。

单位长度，使用 `px`，设计稿的尺寸可在 `manifest.json` 中进行配置（默认 750），然后直接使用设计稿中标识的像素尺寸值即可，框架会自动做移动端屏幕适配。

```
{
  "config": {
    "designWidth": 1080
  }
}
```

NPM 安装下 `less-loader` 后，可以支持 `less` 预处理器的语法：

```
npm i --save-dev less less-loader
```

`font-size` 和 `color` 等很多属性，没有继承的概念，只能在 `text` 等包含文本的组件中一一声明。

有很多浏览器端的样式，框架中并不支持，以及写法和用法也有很多区别，你可以继续踩坑。

### 自定义组件

#### 声明自定义组件

类似于页面组件文件： `*.ux`，但数据模型只能通过 `props` 传入，或者定义在 `data` 中。

你也可以监听传入 `props` 属性的变化：

```js
export default {
  props: ['value'],
  onInit() {
    this.$watch('value', 'handleValueChange')
  }
};
```

生命周期也比较有限，只有：`onInit`、`onReady` 和 `onDestroy`。

如果自定义组件需要感知页面组件的显示和隐藏等生命周期，可以通过事件来处理，比如：

```js
// page.ux
{
  onShow() {
    this.$broadcast('pageShow');
  }
}

// component.ux
{
  onInit() {
    this.$on('pageShow', this.handlePageShow);
  }
}
```

#### 使用自定义组件

在页面组件或者其他自定义组件中导入即可：

```html
<import name="loading" src="../Common/Loading"></import>

<template>
  <div>
  	<loading text="Loading..."></loading>
  </div>
</template>
```

### 事件

#### 原生组件和页面的事件

原生组件的事件类似于 `DOM`，自带了很多通用事件，比如：`click`，`foucs` 等，在模板中需要加 `@` 或 `on` 前缀。

页面自定义事件，在 `onInit` 中绑定，然后进行手动触发：

```js
export default {
  onInit() {
    this.$on('customEventType', this.handleCustomEvent)
  },
  handleCustomEvent({ detail }) {
    // detail 为触发事件时传入的数据参数
  },
  onShow() {
    this.$emit('customEventType', { 
      // event detail data 
    });
  }
}
```

#### 自定义组件的事件

注册自定义组件的事件有 2 种方式：

- 模板中的组件节点
- 页面的 `onInit` 中用 `this.$on` 

在模板中使用时需要加 `@` 或者 `on` 前缀，类似于原生组件事件。在组件内部，通过 `this.$dispatch` 向上传播触发，使用方式类似于页面中的自定义事件。

```jsx
// page.ux
<import name="profile" src="../Common/Profile"></import>

<template>
  <div>
    <profile @name-change="handleProfileNameChange"></profile>
  </div>
</template>

// profile.ux
export default {
  handleNameChange() {
    this.$dispatch('nameChange', { name: this.name });
  }
};
```

页面还可以向下传播，来触发自定义组件的事件，参考本篇文章的[自定义组件](#自定义组件)一节。

## 参考文档

- [快应用技术开发文档](<https://doc.quickapp.cn/>)，快应用联盟