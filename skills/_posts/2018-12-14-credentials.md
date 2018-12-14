---
layout: post
title: 了解下凭证管理 API
---

现有的网站或 Web App 在登录界面都有“记住密码”功能，然后，在下一次访问时可以自动登录。通常，自动登录是通过 cookie 存储服务端生成的 token，在登录时，服务端对其进行校验，以保证 token 的可靠性。

这种传统的方式对开发要求较高，需要制定一系列的校验策略和失效规则。因此，现代浏览器（Chrome）提供了一套凭证管理 API（Crediential Management API），可以把用户登录信息存储在客户端（浏览器）中，不会写入 cookie，安全性很高。

接下来我们通过一些示例代码来一起了解下。

## 异步登录

假如，我们已经拥有一个登录表单，但默认，表单提交时会发生页面跳转。所以，我们需要在 `onsubmit` 事件中阻止默认行为，然后再用 AJAX 来提交数据。

例如，我们用 fetch API 来做异步请求：

```js
handleLogin = (event) => {
  event.preventDefault();

  const formData = new FormData(this.form);

  fetch('/api/login', {
    method: 'POST',
    body: formData
  })
    .then(res => {
      return res.status === 200 ?
        res.json() :
        Promise.reject();
    })
    .then(data => {
      // 存储凭据
    })
    .catch(err => {
      console.error(err);
    });
}
```

## 存储凭据

假设，以上登录请求成功响应。然后，接着在上面代码的“存储凭据”注释部分，调用 `navigator.credentials.store` 方法来存储登录信息。该方法是个异步操作，会等待用户的响应，如图所示：

![Credentials](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-1.png)

当用户选择“保存”，`navigator.credentials.store` 方法返回的 promise 会变为 `resolve`，否则就是 `reject` 。

另外，`store` 方法需要传递凭据对象，凭据管理 API 提供了两个凭据对象：[PasswordCredential](https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential) 和 [FederatedCredential](https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential)，分别存储账号密码登录和第三方登录两种模式。

看一下具体的代码示例：

```js
// 别忘了做兼容性判断
if (navigator.credentials) {
  const cred = new PasswordCredential({
    id: formData.get('username'),
    password: formData.get('password'),
    name: '赵不寒',
    iconURL: data.avatar
  });

  navigator.credentials.store(cred).then(() => {
    this.setState({
      username: cred.id,
      login: true
    });

    console.log(`登录成功，跳转用户页面...`);
    
    // 存储成功后做路由跳转逻辑
    // ...
  });
}
```

简单了解下代码，首先，我们创建了 `PasswordCredential` 的凭证对象，然后把凭证对象 `cred` 传入 `navigator.credentials.store` 方法，等待用户交互。当用户点击提示对话框中的“保存”，`navigator.credentials.store` 的 promise 会返回 resolve，然后，你可以在这里做相应的登录跳转逻辑。

当然，如果你接入的是第三方登录 API，就需要用 `FederatedCredential` 创建凭证对象，不同的是，在创建时，需要传入 `provider` 属性来代替 `password`。需要注意的是，`provider` 必须是完整的 URL（带协议头）。

我们在浏览器控制台做下实验：

![Credentials](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-2.png)

## 获取凭据

凭据存储后，需要获取才能实现自动登录。调用 `navigator.credentials.get` 方法，并传入参数 `{ password: true }` 可以返回凭证对象。

示例代码：

```js
componentDidMount() {
  
  // 在页面加载后开始执行以下逻辑，记得兼容性
  if (navigator.credentials) {
    navigator.credentials.get({
      password: true
    })
      .then((cred) => {
        if (cred) {
          this.setState({
            username: cred.id,
            login: true
          });

          console.log(`登录成功，跳转用户页面...`);
        }
      });
  }
}
```

当凭证对象 `cred` 存在，浏览器就会显示一个自动登录的提示框：

![Credentials](/assets/post-images/{{ page.date | date: "%Y-%m-%d" }}/image-3.jpg)

如果要获取第三方登录凭证对象，`navigator.credentials.get` 方法的参数需要多传一个 `federated` 的字段：

```js
navigator.credentials.get({
  password: true,
  federated: {
    providers: [
      'https://www.baidu.com', 
      'https://www.weibo.com', 
      'https://www.github.com'
    ]
  }
});
```

注意，提供的 `providers` 需要与创建的凭证对象 `FederatedCredential` 中的参数字段 `provider` 一致。同时，对获取的凭证对象 `cred`，需要做类型判断：

```js
switch (cred.type) {
  case 'password':
    // PasswordCredential 凭证处理
  case 'federated':
    // FederatedCredential 凭证处理
    switch (cred.provider) {
      case 'https://www.baidu.com':
        // 调起百度第三方登录
      case 'https://www.weibo.com':
        // 调起微博第三方登录
    }
}
```

## 退出凭据

当用户主动退出网站，那么在下次访问时，不应该自动登录。可以调用 `navigator.credentials.preventSilentAccess` 来退出登录凭证。

```js
handleLogout = () => {
  navigator.credentials.preventSilentAccess()
    .then(() => {
      this.setState({
        username: '',
        login: false
      });
    });
}
```

调用 `handleLogout` 后，在重新调用 `navigator.credentials.get` 时，就不会再自动登录。

## 兼容性

目前，该 API 对于浏览器的支持还比较有限，具体可以查阅 [Can I Use](http://caniuse.com/#search=navigator.credentials)。

## 参考链接

- [凭证管理 API 简介](https://lavas.baidu.com/pwa/automatic-login/credential-management-api/introduction), LAVAS
- [Credential Management API](https://developer.mozilla.org/en-US/docs/Web/API/Credential_Management_API), MDN