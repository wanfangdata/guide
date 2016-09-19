# HTML编码规范

[基本规范](#基本规范)
* [DOCTYPE](#DOCTYPE)
* [页面编码](#页面编码)
* [IE兼容模式](#IE兼容模式)
* [关注点分离](#关注点分离)
* [注释](#注释)
* [缩进](#缩进)
* [引号](#引号)
* [标签闭合](#标签闭合)
* [布尔型属性](#布尔型属性)
* [自定义属性](#自定义属性)

[文档模板](#文档模板)

## 基本规范
#### DOCTYPE
统一使用 HTML5 DOCTYPE 的声明，确保在不同浏览器中拥有一致的表现
```html
<!doctype html>
```
#### 页面编码
遵循HTML5的规范，使用 utf-8 编码，注意html文件也需要使用 utf-8 编码
```html
<meta charset="utf-8" />
```
#### IE兼容
使用最高版本的IE内核进行渲染。
```html
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
#### 关注点分离
将表现，行为与结构分离
```html
<!-- 推荐 -->
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>page</title>
        <link rel="stylesheet" href="css.css" />
    </head>
    <body>
        <div></div>
        <script src="js.js"></script>
    </body>
</html>
```
```html
<!-- 不推荐 -->
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>page</title>
        <style>
            ...
        </style>
    </head>
    <body>
        <div></div>
        <script>
            ...
        </script>
    </body>
</html>
```

