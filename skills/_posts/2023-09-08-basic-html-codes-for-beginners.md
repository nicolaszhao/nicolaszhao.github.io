---
layout: post
title:  适合初学者的 HTML 代码基础
---

本文是一位国外的热心粉丝推荐，内容很基础，但我觉得写的很好、很实用，所以拿来很拙劣的翻译了下，希望能帮助到有需要的朋友。

> 原文地址：[https://www.websiteplanet.com/blog/html-guide-beginners/](https://www.websiteplanet.com/blog/html-guide-beginners/)
>
> 原作者：Ezequiel Bruni

本文面向不会编码的小白，或者经常接触 HTML，但对一些奇怪的标记总是搞不清楚的人。

这里不涉及 CSS 和 JavaScript，你也不需要为此成为一名程序员。虽然 HTML 是一种“编码语言”，但其本身并不能用来执行代码逻辑。所以，你可以轻松的进行一次初学者之旅。

## 基本概念

HTML 是专门让浏览器（比如 Chrome 或 Firefox）在屏幕上显示内容的语言。也就是说，HTML 定义了网页上的实际内容。它是通过标签来实现的，看起来像这样：`<p>这是一些文本。</p>`。

尖括号里的字母叫标签名。 “p”标签专门用来定义一个段落或一般文本块。“结束标记”使用“/”字符与“开始标记”区分开来。但并非每个标签都是如此。有些标签可以自己“打开”和“关闭”，比如：`<img src="" alt="" />`。

当然，这里不会详细介绍所有标签。除非你打算成为一名网页设计师（译者注：应该是前端开发者），否则你不需要了解所有这些。但了解“p”标签（也称为段落标签）是很有必要的。

```html
<p>A Turing machine is a mathematical model of computation that defines an abstract machine, which manipulates symbols on a strip of tape according to a table of rules. Despite the model's simplicity, given any computer algorithm, a Turing machine capable of simulating that algorithm's logic can be constructed.</p>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image1.jpg)

此外，HTML 文件只是一个名称以“.html”结尾的纯文本文件。实际上，你可以在 Windows 上使用记事本编写整个网页，尽管有许多更好的文本编辑器可以完成这项工作。

我们回到标签部分，标签可以包含“属性”。属性可用来做很多事情，例如，使一个段落看起来和另一个有区别，通常可以通过“class=”属性来实现，如下所示：

```html
<p class="intro-text">This is an introductory paragraph.</p>
<p>This is a regular paragraph.</p>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image2.jpg)

当然，你必须使用另一种语言—— CSS，让“介绍文字”看起来真正的与众不同，但这不是今天的话题。

此外，还有大量的属性，很多属性必须和特定标签一起使用，这里不具体展开了。

## 网页

HTML 作为一种语言实际上多年来经历了多次修订。目前，HTML 的标准版本称为 HTML5，尽管你很难将其称为第五次迭代。但这种命名方式更方便和容易推广。

HTML5 旨在大幅简化手动编写 HTML 的体验，并使代码更易于人类和计算机阅读。具体来说，它旨在提供有关页面内容的更多上下文。

这是一个非常基本的 HTML5 页面：

```html
<!DOCTYPE html>
<html>
<head>
<title>This is my awesome web page.</title>
</head>
<body>
</body>
</html>
```

开头的“DOCTYPE”行告诉浏览器它正在查看 HTML5 网页。 “html”标签用于告诉浏览器页面的开始和结束位置。

如果你在浏览器中打开该页面，则只会显示一个完全空白的窗口。当然，你会在浏览器选项卡中看到“这是我超棒的网页”，仅此而已。 “title”标签就是干这个的。你可能已经注意到称为“head”和“body”的两组标签。让我们往下看：

### `head`

网页的“head”部分是放置与网页本身有关的信息的位置，但不放置内容。**用户真正能看到的只有标题，**它不会出现在页面上，而是出现在浏览器的用户界面中（浏览器标签栏）。

让我们看另一个例子：

```html
<html>
<head>
<title>Elephants Galore!</title>
<link rel="stylesheet" href="style.css">
<meta name="Description" content="The elephant  may well be one of the world's cutest animals. Read more about elephants here!">
<meta name="Keywords" content="elephant, mammal, lemurs are cute too">
</head>
</html>
```

正如你所看到的，这个示例不仅仅是一个标题。它有一个“link”标签，用于告诉浏览器来加载这个文件，并建立起两个文件之间的关系。在本例中，它加载了一个 CSS 文件，该文件可用于定义 HTML 的排版和页面布局。

**它还具有两个“meta”标签，用于存储搜索引擎等应用程序使用有关的网页信息。**其中一个是页面的基本描述，当该页面出现在搜索引擎结果中时，该描述会显示在搜索引擎网站上。第二个元标记定义了搜索引擎用于分类的关键字。

### `body`

“body”标签是放置所有内容的位置，用户可以在页面加载后可以看到。它看起来可能这样：

```html
<html>
<head>
…
</head>
<body>
<header>
<h1>Elephants Galore!</h1>
</header>
<section class="pagecontent">
<p>Here's some text about elephants!</p>
</section>
<footer>Copyright &copy; Elephants Galore!, 2467</footer>
</body>
</html>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image3.png)

注意，“header”与“head”有很大的不同，我们会稍后讨论。

## 基本内容标签

这部分对你来说可能是最重要的。**你将学会如何在不破坏内容的情况下更改内容**。我们已经见识了“p”标签，现在，我们跳过它。让我们继续讨论其余的基本内容标签和格式化标签：

### 标题

标题可以把大段的文本分隔成较小的段落，以便你可以更轻松地浏览文章。你可以使用六个标签来定义标题和副标题：

```html
<h1>This is a level 1 heading</h1>
<h2>This is a level 2 heading</h2>
<h3>This is a level 3 heading</h3>
<h4>This is a level 4 heading</h4>
<h5>This is a level 5 heading</h5>
<h6>This is a level 6 heading</h6>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image4.jpg)

注意，“h1”标签是最大的、级别最高的标题，“h6”标签是最小的、级别最低的标题。 “h1”标签通常用于页面标题和网站徽标（Logo）等内容。向下的“h2”标签通常用于分隔页面或帖子中的内容。

### 超链接

超链接，简称“链接”。我们使用锚标记或“a”标记链接到我们网站上的其他页面，或同一页面中的其他内容以及其他网站。**要将某些文本转换为链接，请将其包裹在锚标记中，并使用“href=”属性设置链接的 URL。**

这里，我们快速为感兴趣的人提供一些上下文：URL 代表统一资源定位符，讲人话的话就是“网址”。 URL 由三部分组成：

1. **协议：**基本上，它告诉计算机它将接收或发送什么类型的信息。网页的协议是“HTTP”（超文本传输协议）和HTTPS（HTTP 的加密版本）。

   网址将以“https://”之类的内容开头，尽管许多浏览器并不总是显示这部分。

2. **域名或 IP 地址：**对于大多数人来说，这将显示为网站的名称，例如“google.”。起初该地址通常包含前缀“www.”，但这已经过时了，基本上你不必再输入它。

3. **顶级域名 (TLD)：**比如“.com”、“.org”和“.net”，现在全球有数百个顶级域名。

把它们合一起后，你就会得到类似“https://www.google.com”的一个东西。通常“www.”不再需要输入。

当你在 HTML 中链接到另一个网站时，你应该使用完整的 URL，如下所示：

```html
<a href=”https://google.com”>Google</a>
```

该链接将把你带到 google.com。

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image5.jpg)

然而，当你链接到自己网站上的另一个页面时，情况会发生一些变化。你可以使用所谓的“相对 URL”。也就是说，URL 指向同一服务器上的另一个文件。如果同一文件夹中有两个页面，例如主页（始终命名为 index.html）和“关于我们”页面（about.html），那么从一个页面链接到另一个时就会很简单。

要从主页链接到“关于我们”页面，你只需这样编写：

```html
<a href=”about.html”>About Us</a>
```

如果你的“关于我们”页面位于子文件夹中（与 index.html 位于同一文件夹中），并且该文件夹名为“about-us”，则代码将如下所示：

```html
<a href=”about-us/about.html”>About Us</a>
```

最后，你也可以链接到你自己页面上的其他内容。当用户单击链接时，浏览器将自动向下滚动，以显示链接的内容。

为此，你要链接的内容必须具有“id=”属性。 “id=”属性用于定义网页重要的部分，每个页面的每个“id=”是唯一的，只能使用一次。代码看起来像这样：

```html
<a href="#content2"></a>
<div id="#content1">
<p>Here's some content.</p>
</div>
<div id="content2">
<p>Here's the content you want to link to.</p>
</div>
```

### 图片

如果你要在网站上显示图片，你需要使用“img”标签：

```html
<img src="images/elephants.jpg" alt="Picture of darned cute baby elephants." width="640px" height="480px">
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image6.jpg)

**img 标签有两个主要的属性你得牢记。**第一个是“src=”属性，它告诉浏览器实际的图像地址，以便浏览器可以加载它。其次是，“alt=”属性，它让看不到图像的人和搜索引擎知道图像的内容。

有很多视力不太好的人，他们使用屏幕阅读器大声朗读网页内容。**众所周知，替代文本对于帮助人们充分体验你的网站是至关重要的，即使他们不用眼睛浏览。**

你可能会猜到“width”和“height”属性的作用。然而，在响应式、适合移动设备的设计中，并不总是使用这些属性。图像的大小以其他方式定义，而不是在 HTML 中定义。这个例子中，我们图像的单位用了像素，所以“width=’640px’”意味着图像的宽度是 640 像素。

### 列表

HTML 中有两种类型的列表格式。第一种称为“无序列表”，你可将其称为“项目符号列表”。它旨在列出列表的内容，而具体的顺序并不重要。代码如下所示：

```html
<ul>
<li>This is a list item.</li>
<li>This is a list item.</li>
<li>This is a list item.</li>
</ul>
```

第二种列表格式是“有序列表”，它按升序为每个列表项分配一个编号。代码如下所示：

```html
<ol>
<li>This is a list item.</li>
<li>This is a list item.</li>
<li>This is a list item.</li>
</ol>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image7.jpg)

### 引用

“blockquote”标签用于定义引号，并将这些引号（以视觉方式）与文本的其余部分分开。代码如下：

```html
<blockquote>May the Force be with you. - Some Jedi, probably</blockquote>
```

在上下文中它可能是这样的：

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image8.jpg)

## 页面结构标签

这些是网页的“构建块”。用户通常看不到它们，因为它们用于定义网页的布局和结构。但你需要了解它们，以便在滚动你的页面代码时认识它们。

### div

本节中第一个也是最古老的 HTML 标签是“div”。它是一种通用分隔符，旨在将一组内容标签与另一组内容标签分开。例如，如果你有两列段落，你可以编写如下代码：

```html
<div class="left-column">
<p>Here's some text in the left column.</p>
</div>
<div class="right-column">
<p>Here's some more text in the right column.</p>
</div>
```

实际上你需要编写 CSS 代码来将这两个“div”标签转换为列，否则它们看起来不会有多大区别。这就是“div”标签的用途。这是应用 CSS 代码布局后的样子。

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image9.jpg)

### 页眉、中间部分和页脚

这是我们使用“header”、“section”和“footer”标签的地方。基本上，它们就像“div”，但它们是为更具体的目的而设计的。 **“header”标签用于内容的起始部份。**例如，你可以使用它将网站名称放在页面顶部，如下所示：

```html
<header>
<h1>Elephants Galore!</h1>
</header>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image10.jpg)

**section 标签用于将你的内容划分为多个部分。**例如，如果你的主页上有一个区域展示你的博客文章，另一个区域展示你的电子商务产品，你可以像这样使用它：

```html
<section id="blog">
Put your blog posts here.
</section>
<section id="eCommerce">
Put your store products here.
</section>
```

最后，**“footer”标签用于内容的结尾。**在网页上，你可以使用“footer”标签来显示版权等信息，如下所示：

```html
<footer>
  Copyright &copy; Elephants Galore!, 2467
</footer>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image11.jpg)

### “article” 标签

**“article”标签用于分组一个部分中的相似的内容，**例如博客文章、电子商务产品列表、房地产列表等。你可以在“article”标签内使用“header”、“section”和“footer”标签，以有组织的方式显示信息。

这是一个例子：

```html
<article>
<header>
<h3>This is a blog post title.</h3>
</header>
<section>
<p>Blog post content goes here.</p>
</section>
<footer>
<p>This post was published on Thursday, in the Elephant category.</p>p>
</footer>
</article>
 
<article>
<header>
<h3>This is a blog post title.</h3>
</header>
<section>
<p>Blog post content goes here.</p>
</section>
<footer>
<p>This post was published on Thursday, in the Elephant category.</p>
</footer>
</article>
 
<article>
<header>
<h3>This is a blog post title.</h3>
</header>
<section>
<p>Blog post content goes here.</p>
</section>
<footer>
<p>This post was published on Thursday, in the Elephant category.</p>
</footer>
</article>
```

![](https://dt2sdf0db8zob.cloudfront.net/wp-content/uploads/2020/02/Learn-HTML-Free-Basic-HTML-Codes-for-Beginners-image12.png)

## 该你开始了

当然，HTML 可能比我在这里向你展示的要复杂得多，但基本概念就是这么简单。有了你在这里学到的知识，你应该能够深入研究网页或模板了。你可以尝试做一些小小的改变，而不会担心弄乱它。

不过，每个模板或主题的工作方式会略有不同。它们的编码方式也略有差异。**要注意标签的“class =”和“id =”属性，要弄清楚它们的作用以及它们影响页面的哪个部分。**并非每个开发人员编写的 `class` 或 `id` 都是易于理解的，但它们确实是有用的。

接下来该你上场了。牢记：撤销、保存和备份！