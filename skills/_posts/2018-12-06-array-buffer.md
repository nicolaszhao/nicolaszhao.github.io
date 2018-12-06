---
layout: post
title: ArrayBuffer 学习日记
---

一直对 ES6 中的 `ArrayBuffer` 感到很懵，平时工作中也没有需要的使用场景，但 Web API 中很多都用到了 `ArrayBuffer`，可见他的能力不容小视。最近，小研究了下这个对象，Get 到了很多，很值得在这做个笔记来分享下心得。

`ArrayBuffer` 可以理解为一段内存，用来存储二进制数据。如果是传统的文本格式，传递一个 32 位整数，JavaScript 与操作系统之间的通信都要进行格式转化，非常耗时。`ArrayBuffer` 可以允许开发者直接操作内存，使得开发者能通过 JavaScript 与操作系统的原生接口进行二进制通信。

`ArrayBuffer` 不能直接读写，需要用视图对象 `TypedArray` 和`DataView` 进行操作。可以把视图和 `ArrayBuffer` 的关系理解为前端 UI 和后端数据接口的关系。

## ArrayBuffer 对象

`ArrayBuffer` 是一个构造函数，可以传入参数来分配一段存放书籍的连续内存区域，参数是 `Number` 类型，单位是字节（一个字节 = 8位）。

```js
// 生成一段 32 字节的内存区域
const buffer = new ArrayBuffer(32);
```

同一段内存，也可以创建多种不同的视图，同时，多个视图对应的内存是同一段，一个视图修改后会影响到另一个：

```js
const buffer = new ArrayBuffer(32);
const x = new Int32Array(buffer);
x[0] = 1;

const y = new Int8Array(buffer);
y[0] = 2;

x[0]; // 2
```

## TypedArray 视图

`ArrayBuffer` 可以存放多种类型的数据，同一段内存，不同的数据可以用不同的视图（view）来解读。`TypedArray` 是其中一种视图，JavaScript 中不存在这个 `TypedArray` 构造函数，而是有一组（9 种）不同类型视图：

- `Int8Array`: 8 位有符号整数，每个元素 1 个字节
- `Uint8Array`: 8 位无符号整数，每个元素 1 个字节
- `Uint8ClampedArray`: 8 位无符号整数，每个元素 1 个字节
- `Int16Array`: 16 位有符号整数，每个元素 2 个字节
- `Uint16Array`: 16 位无符号整数，每个元素 2 个字节
- `Int32Array`: 32 位有符号整数，每个元素 4 个字节
- `Uint32Array`: 32 位无符号整数，每个元素 4 个字节
- `Float32Array`: 32 位浮点数，每个元素 4 个字节
- `Float64Array`: 64 位浮点数，每个元素 8 个字节

`TypedArray` 类似于 `Array`，所有 `Array` 的数组方法和 `length` 属性都能使用。但和 `Array` 有以下几点差异：

- `TypedArray`  数组成员都是同一种类型
- `TypedArray`  数组成员不会有空位
- `TypedArray`  数组成员的默认值都为 0，例如，`new Array(10)` 返回一个 10 个空位的普通数组，`new Uint8Array(10)` 返回一个包含 10 个 0 的 `TypedArray` 数组
- `TypedArray` 数组本身不存储数据，它的数据都存放在 `ArrayBuffer` 对象中

### TypedArray 构造函数

#### TypedArray(buffer, byteOffset = 0, length?)

可以接受 3 个参数：

1. 必需，底层 `ArrayBuffer` 对象
2. 可选，视图开始的字节序号，默认从 0 开始
3. 可选，视图包含的数据个数，默认直到本段内存结束

```js
// 创建了 1 段 8 个字节的内存
const buffer = new ArrayBuffer(8);

// 创建了一个指向 buffer 的 Int32 的视图，
// 从字节 0 开始直到缓冲区末尾，包含 2 个数据，每个数据 4 个字节
const x = new Int32Array(buffer);

// 创建了一个指向 buffer 的 Uint8 视图，
// 从字节 2 开始，直到缓冲区末尾，包含 6 个数据，每个数据 1 个字节
const y = new Uint8Array(buffer, 2);

// 创建了一个指向 buffer 的 Int16 视图，
// 从字节 2 开始，指定长度为 2，包含 2 个数据，每个数据 2 个字节
const z = new Int16Array(buffer, 2, 2);
```

`byteOffset` 必须与所要建立的数据类型一致，否则会报错：

```js
const buffer = new ArrayBuffer(8);
const x = new Int16Array(buffer, 1);
// Uncaught RangeError: start offset of Int16Array should be a multiple of 2
```

上面的代码，`Int16Array` 是带符号的 16 位整数，需要 2 个字节，所以 `byteOffset` 参数必须能被 2 整除。

#### TypedArray(length)

`TypedArray` 视图还可以直接分配**元素个数**来生成内存。

```js
// 生成一个 8 个成员的 Float64Array 数组（共 64 字节）
const x = new Float64Array(8);
```

#### TypedArray(typedArray)

`TypedArray` 视图还可以接受另一个 `TypedArray` 实例作为参数：

```js
const typedArray = new Int8Array( new Uint8Array(4) );
```

生成的新数组，只是复制了参数数组的值，不会对应同一段内存，新数组会开辟一段新的内存存储数据：

```js
const x = new Int8Array([1, 1]);
const y = new Int8Array(x);

x[0]; // 1
y[0]; // 1

x[0]; = 2;
y[0]; // 1
```

#### TypedArray(arrayLikeObject)

构造函数参数也可以是个普通数组，可以直接生成 `TypedArray` 实例：

```js
// 生成一个 8 位无符号整数的 TypedArray 实例，包含 4 个数据
const typedArray = new Uint8Array([1, 2, 3, 4]);
```

### TypedArray 关键属性

#### TypedArray.BYTES_PER_ELEMENT

每一种 `TypedArray` 的构造函数都有一个 `BYTES_PER_ELEMENT` 属性，表示这种数据类型占据的字节数：

```js
Int32Array.BYTES_PER_ELEMENT // 4
```

#### TypedArray.prototype.buffer

返回整段内存区域对应的 `ArrayBuffer` 对象（只读）

```js
const x = new Float32Array(64);
const y = new Uint8Array(x.buffer);
```

#### TypedArray.prototype.byteOffset

`byteOffset` 属性返回 `TypedArray` 数组从底层 `ArrayBuffer` 对象的哪个字节开始

#### TypedArray.prototype.byteLength

`byteLength` 属性返回 `TypedArray` 数组占据的内存长度，单位字节

#### TypedArray.prototype.length

 ` byteLength` 属性是字节长度，而 `length` 表示的是数组包含的成员个数：

```js
const a = new Int16Array(8);

a.length // 8
a.byteLength // 16
```

## DataView 视图

如果一段数包括多种类型，可以通过 `DataView` 视图进行操作，但 `DataView` 不像 `TypedArray`，它只有 1 种类型的构造函数。

`DataView` 视图的构造函数可以接受 1 个 `ArrayBuffer` 对象作为参数来生成视图：

```js
const buffer = new ArrayBuffer(24);
const dv = new DataView(buffer);
```

同时，`DataView` 可以用 8 种实例方法来读取内存：

- **getInt8**：读取 1 个字节，返回一个 8 位整数。
- **getUint8**：读取 1 个字节，返回一个无符号的 8 位整数。
- **getInt16**：读取 2 个字节，返回一个 16 位整数。
- **getUint16**：读取 2 个字节，返回一个无符号的 16 位整数。
- **getInt32**：读取 4 个字节，返回一个 32 位整数。
- **getUint32**：读取 4 个字节，返回一个无符号的 32 位整数。
- **getFloat32**：读取 4 个字节，返回一个 32 位浮点数。
- **getFloat64**：读取 8 个字节，返回一个 64 位浮点数。

这一系列 `get` 方法的参数都是一个字节序号（不能是负数，否则会报错），表示从哪个字节开始读取：

```js
const buffer = new ArrayBuffer(24);
const dv = new DataView(buffer);

// 从第 1 个字节读取一个 8 位无符号整数
const v1 = dv.getUint8(0);

// 从第 2 个字节读取一个 16 位无符号整数
const v2 = dv.getUint16(1);

// 从第 4 个字节读取一个 16 位无符号整数
const v3 = dv.getUint16(3);
```

`DataView` 视图也可以用 8 种方法把数据写入内存：

- **setInt8**：写入 1 个字节的 8 位整数。
- **setUint8**：写入 1 个字节的 8 位无符号整数。
- **setInt16**：写入 2 个字节的 16 位整数。
- **setUint16**：写入 2 个字节的 16 位无符号整数。
- **setInt32**：写入 4 个字节的 32 位整数。
- **setUint32**：写入 4 个字节的 32 位无符号整数。
- **setFloat32**：写入 4 个字节的 32 位浮点数。
- **setFloat64**：写入 8 个字节的 64 位浮点数。

这些方法，接受 2 个参数，第一个参数是字节序号，表示从哪个字节开始写入，第二个参数为写入的数据。

```js
// 在第 1 个字节，写入值为 25 的 32 位的整数
dv.setInt32(0, 25);
```

## 二进制数组的应用

浏览器中有多个 Web API 都用到了 `ArrayBuffer` 对象和它的视图：

- AJAX
- Canvas
- WebSocket
- Fetch API
- File API

### Fetch API 示例

```js
fetch(url)
  .then((response) => response.arrayBuffer())
  .then((arrayBuffer) => {
    // ...
  });
```

其他的 API 具体用法可以参考它们的相关文档。

## 参考链接

- [ECMAScript 6 入门 - ArrayBuffer](http://es6.ruanyifeng.com/#docs/arraybuffer)，阮一峰
- [ArrayBuffer](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)，MDN

