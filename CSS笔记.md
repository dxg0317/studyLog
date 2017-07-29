# CSS

## CSS 语句（CSS statements）

### 类型

- 选择器加上声明块被称为规则集（ruleset），通常简称规则（rule）。

- @-规则 CSS中使用@-规则来传递元数据、条件信息或其它描述性信息。它由（@）符号开始，紧跟着一个表明它是哪种规则的描述符，之后是这种规则的语法块，并最终由一个半角分号（;）结束。每种由描述符定义的@-规则，都有其特有的内部语法和语义。一些例子如下：

  - @charset @import （元数据）
  - @media 或 @document （条件信息，又被称为嵌套语句，见下方。)
  - @font-face （描述性信息）

``` css
/*具体语法示例：*/
/*该@-规则向当前 CSS 导入其它 CSS 文件*/
@import 'custom.css';
```

### 嵌套语句

是@-规则中的一种，它的语法是 CSS 规则的嵌套块，只有在特定条件匹配时才会应用到文档上。特定条件如下：

- @media 只有在运行浏览器的设备匹配其表达条件时才会应用该@-规则的内容；
- @supports 只有浏览器确实支持被测功能时才会应用该@-规则的内容；
- @document 只有当前页面匹配一些条件时才会应用该@-规则的内容。

具体语法示例

``` css
@media (min-width: 801px) {
  body {
    margin: 0 auto;
    width: 800px;
  }
}
/*上述的嵌套语句只有在页面宽度超过801像素时才会应用。*/
```

***

## 语法之外：使 CSS 更具可读性和注释

- 适当的空格
- CSS中的注释以 /* 开始并以 */ 结束。

``` css
/*注释*/
body {
  font: 1em/150% Helvetica, Arial, sans-serif;
  padding: 1em;
  margin: 0 auto;
  max-width: 33em;
}

@media (min-width: 70em) {
  body {
    font-size: 130%;
  }
}
```

***

## CSS选择器

- 简单选择器
- 属性选择器
- 伪类和伪元素
- 组合器和多用选择器
