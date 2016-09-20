# HTML编码规范

[基本规范](#基本规范)
* [DOCTYPE](#doctype)
* [协议](#协议)
* [页面编码](#页面编码)
* [IE兼容模式](#ie兼容模式)
* [关注点分离](#关注点分离)
* [注释](#注释)
* [缩进](#缩进)
* [引号](#引号)
* [大小写](#大小写)
* [标签闭合](#标签闭合)
* [语义化](#语义化)
* [布尔型属性](#布尔型属性)
* [自定义属性](#自定义属性)

[文档模板](#文档模板)

[参考文档](#参考文档)
## 基本规范

#### DOCTYPE
统一使用HTML5`DOCTYPE`的声明。
```html
<!doctype html>
```
#### 协议
对于支持https的站点[省略协议可以避免协议混乱产生的问题](https://blog.wikimedia.org/2011/07/19/protocol-relative-urls-enabled-on-test-wikipedia-org)，也可以减少文件的大小。
```html
<!-- 不推荐 -->
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>

.example {
  background: url(http://www.google.com/images/example);
}
```
```html
<!-- 推荐 -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```
#### 页面编码
遵循HTML5的规范，使用 utf-8 编码，注意HTML文件也需要使用 utf-8 编码。
```html
<meta charset="utf-8" />
```
#### IE兼容模式
使用最高版本的IE内核进行渲染。
```html
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
#### 关注点分离
将表现，行为与结构分离，并尽可能减少链接请求。
```html
<!-- 不推荐 -->
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure: <u>HTML is stupid!!1</u>
<center>I can’t believe there’s no way to control the styling of my website without doing everything all over again!</center>
```
```html
<!-- 推荐 -->
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first CSS-only redesign</h1>
<p>I’ve read about this on a few sites but today I’m actually doing it: separating concerns and avoiding anything in the HTML of my website that is presentational.
<p>It’s awesome!
```
#### 注释
建议对复杂的页面模块进行注释。
```html
<div class="md">
    ...
</div> <!-- .md END -->
```
#### 缩进
使用四个空格来表示缩进。
```html
<ul>
    <li></li>
</ul>
```
#### 引号
使用双引号来标识HTML的属性。
```html
<!-- 不推荐 -->
<a class='maia-button maia-button-secondary'>Sign in</a>
```
```html
<!-- 推荐 -->
<a class="maia-button maia-button-secondary">Sign in</a>
```
#### 大小写
元素的标签和属性名必须小写。
```html
<!-- 不推荐 -->
<A HREF='/'>Home</A>
```
```html
<!-- 推荐 -->
<a href="/">Home</a>
```
#### 标签闭合
正确区分自闭合元素和非自闭合元素，非法闭合包括：`<br>..</br>`、`<script />`、`<iframe />`, 非法闭合会导致页面嵌套错误问题。
```html
<!-- 不推荐 -->
<title>Test</title>
<article>This is only a test.
```
```html
<!-- 推荐 -->
<!DOCTYPE html>
<meta charset="utf-8">
<title>Test</title>
<article>This is only a test.</article>
```
#### 语义化
使用符合语义的标签书写HTML文档，选择恰当的元素表达所需的含义，但是不要以牺牲实用性为代价，任何时候都要尽量使用最少的标签并保持最小的复杂度。
```html
<!-- 不推荐 -->
<div onclick="goToRecommendations();">All recommendations</div>
```
```html
<!-- 推荐 -->
<a href="recommendations/">All recommendations</a>
```
#### 布尔型属性
布尔型属性可以在声明时不赋值，XHTML规范要求为其赋值，但是HTML5规范不需要。
```html
<!-- 不推荐 -->
<input type="text" disabled="disabled">
```
```html
<!-- 推荐 -->
<input type="text" disabled>
```
#### 自定义属性
自定义属性用于嵌入自定义数据，统一使用HTML5`data-*`形式。
```html
<span data-index="1">ip</span>
```
## 文档模板
```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <meta http-equiv="x-ua-compatible" content="ie=edge">
        <title>Sample page</title>
        <link rel="stylesheet" href="global.css" />
    </head>
    <body>
        <div clss="page">
            <div clss="header">
                页头
            </div>
            <div clss="content">
                主体
            </div>
            <div clss="footer">
                页尾
            </div>
        </div>
        <script src="global.js"></script>
    </body>
</html>
```
## 参考文档
[https://google.github.io/styleguide/htmlcssguide.xml](https://google.github.io/styleguide/htmlcssguide.xml)