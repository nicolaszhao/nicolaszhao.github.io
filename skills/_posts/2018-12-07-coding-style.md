---
layout: post
title:  如何更好的约束团队的代码风格
---

代码风格一直是我们程序员永不厌倦的话题，特别是前端，由于 JavaScript 是解释型语言，如果缺少代码审查机制，在不注重代码风格的情况下，很容易把隐藏的 bug 带到生产环境，给产品带来隐患，也会给后来的项目维护者（包括自己）增加难度。近年来，出现的 [TypeScript](https://www.tslang.cn/) 虽然可以解决很多这类低级问题，但它并不适合所有项目，特别是中小型项目，有时候反而增加了开发成本。下面是根据我自己的经验，介绍几种编码风格约束方式，这几种方式的约束要求是由低到高的。

## EditorConfig

最简单的方式，是在项目根目录下创建一个 `.editorconfig` 文件，[EditorConfig](https://editorconfig.org/) 可以在保持在不同的编辑器中（开发者都有各自的喜好）拥有一致的基本编码风格，比如：代码缩进、换行符、在最后一行之后保留空行等。由于 EditorConfig 得到了大部分编辑器和 IDE 的支持，像 WebStorm、IntelliJIDEA 等都不需要配置就可以直接使用，而像 VisualStudio Code 这样的编辑也只需要安装一个[插件](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)。

另外，EditorConfig 还可以对不同的文件类型设置不同的配置项，以下是我个人的 `.editorconfig` 的配置项：

```
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

```

具体更详细的配置参数，可以参考 [EditorConfig](https://editorconfig.org/) 官方文档。

## Code Review 会议

如果开发团队不大，团队 Leader 也有一套通过个人经验总结的代码规范，可以召集大家，在一个固定的时间召开非正式的 Code Review 会议。由于，代码规范文档是字面的，团队成员很容易疏忽或者没有严格遵守。通过 Code Review 会议，可以更好的告知大家，团队需要遵守的代码风格的一些要点。

当然，如果在没有其他审查工具机制的情况下，全靠人工去干预比较低级的代码风格问题，效率是非常低的，而且时间成本也很大。还有，反复 review 一些低级问题，也会比较无趣。

## ESLint 自定义规则

在前 2 者的基础之上，可以把自己的一些代码规范，提炼到 [ESLint](https://eslint.org/) 规则中。ESLint 想必我无需再介绍了，是由我的偶像 [Nicholas C. Zakas](http://nczonline.net/) 开发并开源，如果有不了解的可以到[官网](https://eslint.org/)去详细阅读文档。

当然，每次都从一个项目中拷贝 `.eslintrc` 文件有点低效，我们可以通过 ESLint 的 [Shareable Configs](https://eslint.org/docs/developer-guide/shareable-configs) 模式，把你的规则发布到 NPM（或者公司私有 NPM 库）。这样，你只需要在新的项目中，通过 NPM 安装即可，而如果要调整规则，也只需要在这个共享配置模块中修改并发布版本，在使用到的项目中，进行重新安装即可。注意，共享配置的模块名必须是 `eslint-coinfig-` 的前缀，当然也同样支持 [scoped modules](https://docs.npmjs.com/misc/scope)，比如，`@scope/eslint-config-`。

个人建议，可以先继承 ESLint 的推荐规则，然后根据自己团队的规范，用不同的规则类型（最佳实践、代码样式等）分割成不同的模块进行管理，比如，以我个人的 [eslint-config-nz](https://github.com/nicolaszhao/eslint-config-nz/tree/master/rules) 为例，在 rules 目录下分割成了不同的类型进行管理：

```shell
.
├── index.js
└── rules
    ├── best-practices.js
    ├── errors.js
    ├── es6.js
    ├── styles.js
    └── variables.js
```

通过这样的方式，虽然有一定约束，但总体还是比较宽松的，所有规则，只需要团队成员接受并认可，有不同意见时，只需要调整下规则配置就成。

## ESLint 流行规则

ESLint 在初始化（`eslint --init`）时，如果你想用业内流行的规则创建 ESLint 配置文件， 会有 3 种通用规则供你选择：

- [Airbnb](https://github.com/airbnb/javascript)
- [Standard](https://github.com/standard/standard)
- [Google](https://github.com/google/eslint-config-google)

这 3 种规则有各自的代码约束要求，具体可以查看上面规则的各自链接来阅读。不过，个人比较喜欢 Airbnb 的规范，也是社区和业界一致认为的最合理的 JavaScript 编码规范。

当然，这些规范都比较严谨，如果团队还不成熟，而且项目周期比较紧张，可以视情况从前面的规则慢慢过渡过来。

## ESLint + precommit

因为 ESLint 的规则，只会在本地的编辑器中进行审查和提示。团队成员在提交代码时，在有 ESLint 的错误提示的情况下，仍然可以忽略和无视，然后把有问题的代码提交到代码仓库中。

也有团队选择在持续集成阶段（CI）做代码检查，但实际操作下来，由于反馈流程比较长，效率并不理想。

根据实际经验，在本地用 [lint-staged](https://github.com/okonet/lint-staged) + ESLint，而且只检查每次提交时修改的代码，这种解决方案，成本低而且效率高，带来的效果也好。

以下是 lint-staged 最简单实用的配置方式，不过，首先需要根据 [lint-staged 文档](https://github.com/okonet/lint-staged)安装好依赖。

`package.json`：

```json
"scripts": {
  ...
  "precommit": "lint-staged"
},
```

创建 `.lintstagedrc` 文件：

```json
{
  "src/**/*.js": "eslint"
}
```

## 总结

其实，前面总结的编码风格方案，也是我的团队经历成长的过程。大家可以根据自己的团队情况，可以一步到位，也可以循序渐进。当然，也有人说，IDE 都自带 code format 功能，可以按下快捷键一步搞定。但我不推荐这么做，这样不容易养成自己的编码习惯，我常常告诉自己的团队，写代码时要“自带代码格式化”。最后，代码风格不分好坏，而是要注重统一，统一的代码风格很容易找到代码缺陷和问题所在，就像一个艺术品，我们不希望出现任何瑕疵。

