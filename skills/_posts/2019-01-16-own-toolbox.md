---
layout: post
title: 打造属于自己的前端工具箱
---

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-top.jpg)

在开发中，我们经常会编写或者使用很多常见的小功能，就拿前端来讲，解析 URL 查询字符串、时间格式化、日期格式化，这些功能或者说方法再常见不过了。当然，现在很多常用的小功能，大多都能在 [NPM](https://www.npmjs.com/) 上找到。但这些模块的功能通常都比较全面，功能全面的模块，代码体积（size）也是可想而知的，而且可能还包含了你并不需要的功能。所以，有时候整理下你自己写过的代码，你会发现，你也可以整出个小工具箱来，而且对于一些小项目特别适用。

可能你会认为，接下来的内容是要开始讲“如何创建 JavaScript 库”了，对不起，可能要让你失望了。因为，这篇文章意在提高我们平时的开发效率，是一些使用常用的、可封装代码的方式的总结，让自己写过的代码也可以开箱即用。

## 代码片段

最简单的方式，是直接使用**代码片段**（code snippets）。现在大多数代码编辑器都带有代码片段功能，比如 Visual Studio Code。

在 Visual Studio Code 中内置了很多默认的代码片段，比如在编辑器中输入 `forof`：

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-3.png)

在弹出的提示列表中，只要列表项左侧的图标是一个底部是点线，其他边是实线的矩形方块，都是可以直接使用的代码片段。

除了内置的代码片段，你还可以创建**用户代码片段**（Code - 首选项 - 用户代码片段），新建或者选择一个代码片段的类型，然后，在打开的一个 `*.json` 文件中会显示带有注释的、预设的部分代码片段（`console.log`），比如像下面这个：

```json
{
  // Place your snippets for javascript here. Each snippet is defined under a snippet name and has a prefix, body and
  // description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
  // $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the
  // same ids are connected.
  // Example:
  "Print to console": {
    "prefix": "log",
    "body": [
      "console.log('$1');",
      "$2"
    ],
    "description": "Log output to console"
  }
}
```

其中，需要设置的字段也很容易看懂，比如 `prefix` ，就是在你写代码时输入的代码片段快捷指令，选择后，就可以生成 `body` 中的代码。像上面这段，当输入 `log` 时，编辑器会自动弹出帮助提示列表，然后，选择你预设的代码片段指令，并按下回车，代码片段就会立刻自动生成。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-1.png)

下面是一个创建 React 标准组件的代码片段：

```json
{
  "React standard class component": {
    "scope": "javascript,typescript",
    "prefix": "rc",
    "body": [
      "import React, { Component } from 'react';",
      "",
      "class $1 extends Component {",
      "  render() {",
      "    return (",
      "      <div>$1</div>",
      "    );",
      "  }",
      "}",
      "",
      "export default $1;"
    ],
    "description": "init React standard class component"
  },

  ...
}
```

当你在编辑器中输入 `rc`，就会出现如下提示：

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-2.png)

## Gist

自定义的用户 Code Snippets 只能在本地使用，如果换一台电脑，你就无能为力了。也许你也曾经历过，把 WebStorm 等编辑器的配置导出，并保存起来（云端、U 盘等），等下次换一台电脑时，可以重新导入。尽管如此，也还是相当麻烦的，而且也不那么科技。

所以，[GithubGist](https://gist.github.com) 就可以登场了。

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-4.png)

Gist 的功能非常简单实用。如上图所示，输入描述、文件名（可包含文件类型）、代码内容，另外，还可以设置代码缩进格式等。

当我们需要创建一组代码片段时，可以点击**“Add file”**按钮增加文件。

Gist 还可以创建私密的（无法被搜索到的）和公开的代码片段，可以登录 Github ，也可以匿名使用。

创建的代码片段，Gist 还会帮你生成一个 JS 文件地址，可以在 HTML 中直接引用以方便调试。而且，你可以创建无限数量的代码片段，非常 Cool。

## 代码仓库

当你常用的代码片段有足够多，并且可以归类时，创建一些可以直接使用的 JS 文件，或者模块可能更为合适。这时候，我们需要有一个可以归档的 Git 代码仓库。

有了这个代码仓库，我们可以随时 `clone` 下来，寻找并复制一些需要的文件或者模块，然后在项目中可以直接使用（引用），比如：

```js
// toolbox.js
var Toolbox = {};
Toolbox.formatDate = function(date) {
  ...
};
```

```html
<html>
  <body>
    ...
    <script src="toolbox.js"></script>
  </body>
</html>
```

虽然这样的方式，可以收集和归类成你的工具库，但现在已经 2019 年了，直接写 ES5 的代码，显然很不现代。这时候，你需要制作一个 Library，也就是我们在开头提到的。

## Library

JavaScript Library 有别于代码片段，使用场景也有些不同。但开发一个 Library 有一个明显的好处，除了可以像上面那样，直接 `src` 引用完整的包之外，还可以在现代的前端项目中，通过 ESModule 方式导入。

```js
import { formatDate } from 'toolbox';
```

当然，前提是你需要发布你的 Library 到 NPM。

现在，制作一个 Library 也有很多方式，如果是个比较简单的 Library，可以参考下 webpack 的官方教程 [Authoring Libraries](https://webpack.js.org/guides/author-libraries/)。但现代化的前端项目，工程化要求越来越高，在导入模块后，最终构建生成的 bundle 不希望把未使用的代码打包进来，开启 [Tree Shaking](https://webpack.js.org/guides/tree-shaking/) 功能是个非常不错的选择。但用 webpack 构建的 Library 无法生成 ESModule 的包，也就没办法体验 Tree Shaking 的价值了。

使用 [rollup.js](https://rollupjs.org/) 构建 Library 就酷很多，而且，该工具的构建配置也相当简单。下面是一个生成 ESModule bundle 的配置示例：

```js
// rollup.config.js
export default {
  input: 'src/main.js',
  output: {
    file: 'bundle.js',
    format: 'esm'
  }
};
```

和 webpack 比起来是不是简单的令人发指？目前，已经有很多流行的 Library 都使用了 Rollup 来构建项目，比如：React。

当然，Rollup 和 webpack 都有各自的优缺点和使用场景。但 Rollup 就是为 Library 而生的，而且，生成的 ESM 可以直接支持 Tree Shaking。这里，墙裂推荐一个内置 Rollup 的 CLI 脚手架生成器：[create-react-library](https://github.com/transitive-bullshit/create-react-library)。

虽然比起代码片段来讲，Library 的开发成本有点小高，但随着自己的经验积累，自己手边可拿来使用的代码也会越来越多，如果制作一个按模块类型分类的、开箱即用的 Library 对自己还是非常有帮助的。

下图是我自己个人用的一个 Library —— [tote-box](https://github.com/nicolaszhao/tote-box) 的模块分类截图：

![](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-5.png)

## 总结

程序员平时的时间，会被无数的工作和项目需求堆满。当我们项目经历的越多，就会积累很多好用的、可封装再利用的代码。通过代码片段、代码仓库、Library 等开箱即用的方法可以在一定程度上提高我们的开发效率，从而腾出时间来学习更多技能，让自己变的更加优秀。
