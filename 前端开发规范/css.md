# CSS编码规范
[CSS校验](#css校验)

[基本规范](#基本规范)
* [页面编码](#页面编码)
* [id和类的命名](#id和类的命名)
* [id和类的命名](#id和类的命名)

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
## 参考文档
[https://google.github.io/styleguide/htmlcssguide.xml](https://google.github.io/styleguide/htmlcssguide.xml)