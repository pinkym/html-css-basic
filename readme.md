
# 工具
* [取色器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Colors/Color_picker_tool)
* 设计网页，包括[字体](https://developer.mozilla.org/zh-CN/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like)

----
# HTML
## html元素
元素（Element）：开始标签、结束标签与内容相结合，便是一个完整的元素。
不包含任何内容的元素称为空元素。比如 <img> 元素：

```html
<img src="images/firefox-icon.png" alt="测试图片">
```
本元素包含两个属性，但是并没有 </img> 结束标签，元素里也没有内容。这是因为图像元素不需要通过内容来产生效果，它的作用是向其所在的位置嵌入一个图像。

## html文档基本元素
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>测试页面</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="测试图片">
  </body>
</html>
```
* `<!DOCTYPE html>`:文档类型。历史遗留。最初被用来自动校正html文本，现在只是保留这种写法。
* `<html></html>` ：`<html>`元素。包含了html文件的全部内容，也被成为根元素。
* `<head></head>`: `<head>`元素。这部分的内容不是展现给用户的，而是包含例如面向搜索引擎的搜索关键字（keywords）、页面描述、CSS 样式表和字符编码声明等。
* `<meta charset="utf-8"> `: 这个元素指定了当前文档使用 UTF-8 字符编码 ，UTF-8 包括绝大多数人类已知语言的字符。基本上UTF-8可以处理任何文本内容，还可以避免以后出现某些问题。
* `<title></title>`: 页面的标题，显示在浏览器标签页上，同时作为收藏网页的描述文字。
* `<body></body>`: 包含期望让用户看到的内容。

## img元素
`alt`属性在img中的图片无法加载时显示。试着为图像编写一些更好的 alt 文本。

## 其他常用文本标记元素
### 1. 标题 heading
```html
<h1>主标题</h1>
<h2>顶层标题</h2>
<h3>子标题</h3>
<h4>次子标题</h4>
```
包含h1到h6。
不要使用标题元素来加大、加粗字体，因为标题对于 [无障碍访问](https://developer.mozilla.org/zh-CN/docs/learn/Accessibility) 和 [搜索引擎优化](https://developer.mozilla.org/zh-CN/docs/learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#%E4%B8%BA%E4%BB%80%E4%B9%88%E6%88%91%E4%BB%AC%E9%9C%80%E8%A6%81%E7%BB%93%E6%9E%84%E5%8C%96) 等问题非常有意义。要保持页面结构清晰，标题整洁，不要发生标题级别跳跃。

### 2. 段落 paragraph
`<p>` 元素是用来指定段落的。通常用于指定常规的文本内容。

### 3. 列表 list
* 有序列表 ordered list: 用一个`<ol>`元素包围。
* 无序列表 unordered list: 用一个`<ul>`元素包围。

列表的每个项目用一个列表项目（List Item）元素 `<li>` 包围。

### 4. 链接
要植入一个链接，我们需要使用一个简单的元素 — `<a>` — a 是 "anchor" （锚）的缩写。
例如：
```html
<a href="https://www.mozilla.org/zh-CN/about/manifesto/">Mozilla 宣言</a>
```
**如果网址开始部分省略了** `https://` 或者 `http://`，可能会得到错误的结果。
`href`代表的是超文本引用（ hypertext reference）。

## 更多html
上面涉及到的只是非常基础的html知识，如果要继续深入学习，可以参考下面的连接：

*  [html学习指南](https://developer.mozilla.org/zh-CN/docs/learn/HTML)：介绍了深入学习的路径
* [使用 HTML 解决常见问题](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Howto)：包含 `如何将网页分成有逻辑的段落`、`如何使用html显示代码`等主题，以及一些进阶项目

----

# CSS
CSS (Cascading Style Sheets) 是为网页添加样式的代码。

一些可能出现的由于翻译带来的困扰：

* “框”=“盒子”=box，边框=“border”。
* padding大部分人翻译成“内边距”，但是padding也有人翻译为“填充”。

在文档头（也就是 `<head> `和 `</head> `标签之间）加入以下代码将css文件链接至html文档：
```html
<link href="styles/style.css" rel="stylesheet" type="text/css">
```

## css规则集
```css
p {
    color: grey;
}
```
规则集包括：

* 选择器：它选择了一个或多个需要添加样式的元素（在这个例子中就是 p 元素）。要给不同元素添加样式只需要更改选择器就行了。
* 声明： 一个单独的规则。如 `color: grey;` 用来指定添加样式元素的属性。
* 属性：改变 HTML 元素样式的途径。（本例中 color 就是 `<p>` 元素的属性。）CSS 编写人员决定修改哪个属性以改变规则。
* 属性的值：在属性的右边，冒号后面即属性的值，它从指定属性的众多外观中选择一个值（我们除了 grey 之外还有很多属性值可以用于 color ）。

## 多元素选择
可以选择多种类型的元素并为它们添加一组相同的样式。将不同的选择器用逗号分开。
```css
p, li, h1 {
  color: red;
}
```
### 不同类型的选择器
|选择器名称	    | 选择的内容	| 示例 |
| ----- | -----: | :-----: |
|元素选择器（也称作标签或类型选择器）|	所有指定类型的 HTML 元素|	p 选择 `<p>`|
|ID 选择器	| 具有特定 ID 的元素（单一 HTML 页面中，每个 ID 只对应一个元素，一个元素只对应一个 ID）|	`#my-id`  选择` <p id="my-id"> `或 `<a id="my-id">`|
|类选择器	|具有特定类的元素（单一页面中，一个类可以有多个实例）|	`.my-class`选择` <p class="my-class">` 和` <a class="my-class">`|
|属性选择器	|拥有特定属性的元素	|`img[src]`选择 `<img src="myimage.png"> `而不是 `<img>`|
|伪（Pseudo）类选择器|	特定状态下的特定元素（比如鼠标指针悬停）|`a:hover`仅在鼠标指针悬停在链接上时选择 `<a>`|
还有更多选择器种类，参考 [选择器](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Selectors)。

## 字体和文本
> 中文字体文件较大，不适合直接用于 Web Font。

 1. 第一步，找到之前 Google Font 输出的地址。并以 <link> 元素的形式添加进 index.html 文档头（ <head> 和 </head> 之间的任意位置）。代码如下：
```css
<link href="https://fonts.font.im/css?family=Open+Sans" rel="stylesheet" type="text/css">
```
以上代码为当前网页下载 Open Sans 字体，从而使自定义 CSS 中可以对 HTML 元素应用这个字体。
 2. 接下来，删除 `style.css` 文件中已有的规则。虽然测试是成功的了，但是红字看起来并不太舒服。
 3. 将下列代码添加到相应的位置，用你在 [Google Fonts](https://fonts.google.com/) 找到的字体替代 `font-family` 中的占位行。（ `font-family` 意味着你想要你的文本使用的字体。）这条规则首先为整个页面设定了一个全局字体和字号（因为` <html>` 是整个页面的父元素，而且它所有的子元素都会继承相同的 `font-size` 和 `font-family`）：
```css
html {
  /* px 表示 “像素（pixels）”: 基础字号为 10 像素 */
  font-size: 10px; 
  /* Google fonts 输出的 CSS */
  font-family: 'Open Sans', sans-serif; 
}
```
 4. 接下来为文档体内的元素（`<h1>`、`<li>` 和 `<p>`）设置字号。将标题居中显示，并为正文设置行高和字间距，从而提高页面的可读性。
```css
 h1 {
  font-size: 60px;
  text-align: center;
}

p, li {
  font-size: 16px;    
  line-height: 2;
  letter-spacing: 1px;
}
```

## 一切皆盒子
编写 CSS 时你会发现，你的工作好像是围绕着一个一个盒子展开的——设置尺寸、颜色、位置，等等。页面里大部分 HTML 元素都可以被看作若干层叠的盒子。

并不意外，CSS 布局主要就是基于盒模型的。每个占据页面空间的块都有这样的属性：

- padding：即内边距，围绕着内容（比如段落）的空间。
- border：即边框，紧接着内边距的线。
- margin：即外边距，围绕元素外部的空间。
![padding、border、margin][1]
这里还使用了：

- width ：元素的宽度
- background-color ：元素内容和内边距底下的颜色
- color ：元素内容（通常是文本）的颜色
- text-shadow ：为元素内的文本设置阴影
- display ：设置元素的显示模式（暂略）

## 更改页面颜色
```css
html {
  background-color: #00539F;
}
```

## 文档体格式设置
```css
body {
  width: 600px;
  margin: 0 auto;
  background-color: #FF9500;
  padding: 0 20px 20px 20px;
  border: 5px solid black;
}
```
- `width: 600px;` —— 强制页面永远保持 600 像素宽。
- `margin: 0 auto;` —— 为 `margin` 或 `padding` 等属性设置两个值时，第一个值代表元素的上方和下方（在这个例子中设置为 0），而第二个值代表左边和右边（在这里，`auto` 是一个特殊的值，意思是水平方向上左右对称）。你也可以使用一个，三个或四个值，参考 [这里](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin#%E5%8F%96%E5%80%BC) 。
- `background-color: #FF9500;` —— 如前文所述，指定元素的背景颜色。我们给 `body` 用了一种略微偏红的橘色以与深蓝色的 `<html>` 元素形成反差，你也可以尝试其它颜色。
- `padding: 0 20px 20px 20px;` —— 我们给内边距设置了四个值来让内容四周产生一点空间。这一次我们不设置上方的内边距，设置右边，下方，左边的内边距为20像素。值以上、右、下、左的顺序排列。
- `border: 5px solid black;` —— 直接为 `body` 设置 5 像素的黑色实线边框。

## 定位页面主标题并添加样式
```css
h1 {
  margin: 0;
  padding: 20px 0;    
  color: #00539F;
  text-shadow: 3px 3px 1px black;
}
```
页面顶部有一个难看的间隙。那是因为浏览器会没有任何 CSS 的情况下 给 `<h1>` 等元素设置一些默认样式。但这并不是个好主意，但是我们希望一个没有任何样式的网页也有基本的可读性。为了去掉那个间隙，我们通过设置 ` margin: 0; ` 覆盖掉默认样式。

至此，我们已经把标题的上下内边距设置为 `20` 像素，并且将标题文本与 HTML 的背景颜色设为一致。

需要注意的是，这里使用了一个` text-shadow` 属性，它可以为元素中的文本提供阴影。四个值含义如下：

- 第一个值设置水平偏移值 —— 即阴影右移的像素数（负值左移）。
- 第二个值设置垂直偏移值 —— 即阴影下移的像素数（负值上移）。
- 第三个值设置阴影的模糊半径 —— 值越大产生的阴影越模糊。
- 第四个值设置阴影的基色。

## 图像居中
```css
img {
  display: block;
  margin: 0 auto;
}
```
把图像居中来使页面更美观。可以复用 `body` 的 `margin: 0 auto` ，但是需要一点点调整。 `<body>` 元素是**块级元素**，意味着它占据了页面的空间并且能够赋予外边距和其他改变间距的值。而图片是**内联元素**，不具备块级元素的一些功能。**所以为了使图像有外边距，我们必须使用 `display: block` 给予其块级行为。**
>以上说明假定所选图片小于页面宽度（600 pixels）。更大的图片会溢出 body 并占据页面的其他位置。要解决这个问题，可以：
1）使用 图片编辑器 来减小图片宽度；
2）用 CSS 限制图片大小，即减小 <img> 元素 width 属性的值（比如 400 px）

## 更多css
[参考](https://developer.mozilla.org/zh-CN/docs/Learn/CSS)