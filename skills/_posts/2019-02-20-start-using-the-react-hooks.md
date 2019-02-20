---
layout: post
title: 开始使用 React Hooks
---

React 的 Hooks 已经出来有一段时间了，不过正式发布是在最近的 16.8 的版本。

因为 Hooks 是完全向后兼容的，就像[官方文档](https://reactjs.org/docs/hooks-intro.html#no-breaking-changes)所说的，没有任何破坏性的更改：

> - **Completely opt-in.** You can try Hooks in a few components without rewriting any existing code. But you don’t have to learn or use Hooks right now if you don’t want to.
> - **100% backwards-compatible.** Hooks don’t contain any breaking changes.

所以你并不需要马上重构之前的组件。那既然这样，为什么我们还要使用它呢？

如果你是个有经验的 React 使用者，应该很清楚 React 组件的包装地狱和高阶组件的嵌套问题。[React 官方文档](https://reactjs.org/docs/hooks-intro.html#motivation)在这一点上解释的很清楚了，我也不再重复。接下来，我们通过几个简单的代码示例来了解下常用的 Hooks API，希望对你快速上手 React Hooks 会有一点帮助。

## 经典示例

初步上手，先来一个经典示例——Counter：

```react
import React, { useState } from 'react';

export default function HooksExample() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Clicked times: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

对，就是这么简单！只是，state 的用法和 class 组件有点区别。在组件方法内没有 `this`，所以也就没有 `this.state` 和 `this.setState`，state 的初始值，用 `useState` 的第一个，也是唯一一个参数来初始化。然后 `useState` 返回一个数组：成对的 state 和更新 state 的方法（我们可以叫它 `setState`，但你可以随意声明）。因为没有 class 组件一样的生命周期，在这里，通过 `setCount` 更新 `count` 后，组件重新渲染，接着在渲染后通过 `useState` 来获取更新后的数据。

因为现在的组件并不是纯渲染的**无状态组件**（stateless components）了，我们可以更好的称之为**函数组件**（function components）。

## 多个 state

只使用一个 state 是无法满足日常需求的，我们把上面的 Counter 示例再增加一个 state。

```react
export default function HooksExample() {
  const [incrementCount, setIncrementCount] = useState(0);
  const [decrementCount, setDecrementCount] = useState(100);

  return (
    <div className={style.wrapper}>
      <p>Increment Count: {incrementCount}</p>
      <p>Decrement Count: {decrementCount}</p>
      <button onClick={() => setIncrementCount(incrementCount + 1)}>
        Increment
      </button>
      <button onClick={() => setDecrementCount(decrementCount - 1)}>
        Decrement
      </button>
    </div>
  );
}
```

当更新其中一个 state 时，两个 state 的值可以互不影响。但你必须得注意它们的声明顺序。可能你会好奇，`useState` 和 state 又是怎么关联起来的，毕竟 `useState` 只有一个初始值的参数而已。

根据经验，我猜测模块内部有一个指针，类似数组的索引，当 Hook 调用时用来确定该 state 是属于哪个 Hook 的。当组件重新渲染，重置模块指针。[官方文档](https://reactjs.org/docs/hooks-faq.html#how-does-react-associate-hook-calls-with-components)的答案解释了更多细节，你可以继续深入了解。

所以，在声明 Hooks 时，顺序很重要，而且 Hooks 不能在循环、条件语句和嵌套方法中声明，为此，React 特别说明了一些[声明 Hooks 时的规则](https://reactjs.org/docs/hooks-rules.html)。为了减少错误，官方还单独开发了 ESLint 插件：[eslint-plugin-react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks)。

## 合并 state

当一个组件内的 state 太多时，可能会比较混乱。所以，你可以像 class 组件那样把 state 初始化为一个对象。

```js
const [state, setState] = useState({ count: 0, name: 'Nicolas' });
```

不过，在 state 更新时并不会像 class 组件的 `this.setState` 那样自动合并对象。好在 Hooks 的 `setState` 还可以通过传递 `function` 的方式更新数据，然后用 ES6 的对象扩展语法，让代码更加简练。

```js
setState(prevState => {
  return {
    ...prevState,
    count: prevState.count + 1
  };
});
```

## 副作用

之前，在手动更改 DOM，或者数据请求等操作时，同一逻辑功能的代码可能会分散到不同的生命周期方法内，这样很容易出现 bug。Hooks 的 `useEffect` 可以让这些代码集中到独立的 Effect 中，以便更好的维护。

```react
export default function HooksExample() {
  const [id, setId] = useState(0);
  const [name, setName] = useState('----');

  useEffect(() => {
    console.log(`fetch name with user ID: ${id}`);
    fetchName(id).then(name => setName(name));
  });

  return (
    <div className={style.wrapper}>
      <p>Name: {name}</p>
      <button onClick={() => setId(id + 1)}>
        Update User ID
      </button>
    </div>
  );
}
```

上面的示例代码中，数据请求 API `fetchName`，在第一次渲染和 `userId` 更新后重新渲染时，都会调用执行。在之前 class 组件中，需要在 `componentDidMount` 和 `componentDidUpdate` 中编写相似的重复逻辑。当然，我们也可以把重复逻辑提取到一个方法中，但不管怎么样，这个方法的调用还是需要在不同的地方编写。

不过上面的代码有一个问题，如果你打开 Chrome 控制台，你会发现，在每次更新 `id` 时，`useEffect` 中的 `console.log` 都会打印 2 次。

那是因为，每一个 state 的更新都会导致组件的重新渲染。当更新 `id` 后，重新渲染并调用Effect，在 `fetchName` 的请求响应后，又更新了 `name`，然后组件再次更新，当第二次调用 Effect 时，`id` 并没有变化，但 `fetchName` 又请求了一次。

这么显而易见的问题，React 团队早就考虑到了。如果你给 `useEffect` 传递第 2 个参数，在组件重新渲染时，Hooks 会根据它来判断是否需要跳过此次调用，判断依据是该值在组件渲染前后的变化。你可能会想到之前在 `componentDidUpdate` 中有相似的逻辑。

```js
componentDidUpdate(prevProps, prevState) {
  if (prevState.id !== this.state.id) {
    fetchName(id)
      .then(name => {
        // ...
      });
  }
}
```

而 Hooks，你只需要给 `useEffect` 的第 2 个参数传递一个数组，Hooks 会依次判断每一个数组项在组件渲染前后是否有变化。

```js
useEffect(() => {
  console.log(`fetch name with user ID: ${id}`);
  fetchName(id).then(name => setName(name));
}, [id]);
```

然而，还有一种常见情况。如果你的组件只在渲染时执行一次 Effect，那么你只需要给第 2 个参数传递一个空数组 `[]` 即可。

另外，在 class 组件中通常会在 `componentWillUnmount` 中做一些清理工作，现在使用 Hooks 会变得格外简单。

假设，我们在 `useEffect` 中要执行一个 `timer` 方法，该方法接受一个回调函数的参数，当 `timer` 执行后，每隔一秒就会自动调用这个回调。同时 `timer` 初始化时会返回一个 `clear` 方法。该方法用来停止 `timer`（`clearTimeout`）。

如果你为 Effect 返回一个 `function`，Hooks 会在每次渲染前（调用 Effect 时）自动执行清理工作。但在这里，我们只需要在组件卸载前清理下，我们只需要传入 `[]` 即可。

```js
useEffect(() => {
  const clear = timer(() => setCount(count => count + 1));
  return () => clear();
}, []);
```

## 封装 Hooks

假如你有多个组件，在这些组件中，有相同的处理状态的逻辑。之前，我们可以封装到高阶组件或者 Render Props 来解决。那么在 Hooks 中，你只需要把这些逻辑封装成自己的 Hook，以供多个组件重用。

```react
function useTimer(initialTime = 0) {
  const [count, setCount] = useState(initialTime);

  useEffect(() => {
    const clear = timer(() => setCount(count => count + 1));
    return () => clear();
  }, []);

  return count;
}

function HooksExample() {
  const time = useTimer(0);

  return (
    <div className={style.wrapper}>
      <p>Time: {time}</p>
    </div>
  );
}
```

但不管怎么封装，你始终应该把你的 Hook 定义为带 `use` 前缀的方法： `useSomething`。

还有很多细节，你可以到[官方文档](https://reactjs.org/docs/hooks-custom.html)中去了解。

## state 管理

前面在[合并 state](#合并-state) 一节中有讲到把一个 state 声明为对象来组织多个状态的方法。然而，React Hooks 为我们提供了更好的方案：

```react
function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    // ...
  }
}

function Counter({initialState}) {
  const [state, dispatch] = useReducer(reducer, {count: 0});
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
    </>
  );
}
```

使用 `useReducer` 可以很好的维护组件的多个状态，熟悉 `Redux` 的同学应该能很好的理解。如果你不希望在项目中引入 `Redux` 而让项目变得复杂，又想使用 `reducer` 来简单管理多个状态的话，`useReducer` 是个很好的选择。

React Hooks 还有其他一些有趣的 API，不过常用的应该就是上面这些了，大家有兴趣可以通过[React 官方文档](https://reactjs.org/docs/hooks-reference.html#additional-hooks)继续了解。

## 最后

很明显，React Hooks 的出现是为了解决之前 React 在开发时的一些痛点，也是为了更好的把一些逻辑代码封装到组件中，让组件真正抽象。

但就像文章开头提到的，不使用 Hooks 并不会影响你现有的代码，你也不用着急动手马上重构。因为，Hooks 的思想和已经存在多年的组件生命周期可能有些不同，你还需要慢慢适应。但如果你已经准备好了，那么，赶紧在一个新的组件中开始尝试 React Hooks 吧！

