# CSS编码规范
[CSS校验](#css校验)

[基本规范](#基本规范)
* [页面编码](#页面编码)
* [id和类的命名](#id和类的命名)
* [元素选择器](#元素选择器)
* [属性声明顺序](#属性声明顺序)
* [属性简写](#属性简写)
* [0的使用](#0的使用)
* [16进制的颜色值表示](#16进制的颜色值表示)
* [分号](#分号)
* [关于font-weight](#关于font-weight)

[CSS Reset](#cssreset)

[参考文档](#参考文档)
## CSS校验
除了 css hack 和浏览器私有属性， 推荐使用 [w3c css validator](http://jigsaw.w3.org/css-validator) 校验其余的代码.

## 基本规范

#### 页面编码
为了兼容低版本IE浏览器，CSS文件第一行需要声明文件编码。
```css
@charset "utf-8";
```
#### id和类的命名
为 id 和样式类使用有意义或通用的名字，避免由于 css 命名更改引起的不必要的文档或模板改变。
```css
/* 不推荐： 无意义 */
#yee-1901 {}

/* 不推荐： 表现层的命名 */
.button-green {}
```
```css
/* 推荐: 具体 */
#gallery {}
#login {}
.video {}

/* 推荐: 通用 */
.effect {}
.alt {}
```
id 和 class 的命名长度应该适中，不要太简略也不要太详细
```css
/* 不推荐 */
#navigation {}
.atr {}
```
```css
/* 推荐 */
#nav {}
.author {}
```
#### 元素选择器
由于[性能原因](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/)， 避免元素选择器和类选择器以及 id 选择器混用。
```css
/* 不推荐 */
#navigation {}
.atr {}
```
```css
/* 推荐 */
#nav {}
.author {}
```
#### 属性声明顺序
按照字母顺序声明属性，排序时忽略私有的浏览器前缀，对于特定的浏览器，私有的浏览器前缀应该参与排序。
```css
background: fuchsia;
border: 1px solid;
-moz-border-radius: 4px;
-webkit-border-radius: 4px;
border-radius: 4px;
color: black;
text-align: center;
text-indent: 2em;
```
或者按照表现形式排序，Positioning、Box Model、Typographic、Visual
```css
.main {
  position: absolute;
  top: 0;
  right: 0;
  display: block;
  width: 100px;
  height: 100px;
  color: #333;
  background-color: #f5f5f5;
  opacity: 1;
}
```
#### 属性简写
为了提高可读性，尽可能的使用简写属性
```css
/* 不推荐 */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```
```css
/* 推荐 */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```
#### 0的使用
对属性值为 0 的情况省略单位。
```css
margin: 0;
padding: 0;
```
省略属性值中的 0 前缀。
```css
font-size: .8em;
```
#### 16进制的颜色值表示
对属性值为 0 的情况省略单位。
```css
/* 不推荐 */
color: #aabbcc;
```
```css
/* 推荐 */
color: #abc;
```
#### 分号
使用分号结束单个属性的定义。
```css
/* 不推荐 */
.test {
  display: block;
  height: 100px
}
```
```css
/* 推荐 */
.test {
  display: block;
  height: 100px;
}
```
#### 关于font-weight
避免使用bolder、lighter这类相对量或浏览器的默认样式。
```css
/* 不推荐 */
.content { font-weight: blod; }
```
```css
/* 推荐 */
.content { font-weight: 700; }
```
#### CSS Reset
避免使用bolder、lighter这类相对量或浏览器的默认样式。
```css
@charset "utf-8";
body, h1, h2 , h3, h4, h5, h6, dl, dt, dd, ul, li, th, td, p, button, input, select, textarea { margin: 0; padding: 0; }
b, em, i, strong, th { font-style: normal; font-weight: 400; }
h1, h2 , h3, h4, h5, h6 { font-size: 100%; font-weight: 400; }
button, input, select, textarea { font-family: inherit; font-size: 100%; }
img { border: 0; }
ul { list-style: none; }
table { border-collapse: collapse; border-spacing: 0; }
th { text-align: left; }
button::-moz-focus-inner { border: 0; padding: 0; }
:focus { outline: 0; }
```
## 参考文档
[https://google.github.io/styleguide/htmlcssguide.xml](https://google.github.io/styleguide/htmlcssguide.xml)