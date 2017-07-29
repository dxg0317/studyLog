# 网站制作

## 做计划

1. 用纸和笔画草图
1. 选择内容

- 文本：  制作段落和标题
- 主题颜色：  工具网站 [the Color Picke](https://www.w3schools.com/colors/colors_picker.asp)
- 图像：访问 [Google Images](https://www.google.com.hk/imghp?gws_rd=ssl,cr) 搜索合适的内容
- 字体: 访问 [Google Fonts](https://fonts.google.com/?selection.family=Khula) 搜索合适的字体

## 存储位置

- 网站存放在一个文件夹里
- 文件夹名和文件名使用**小写**且**不含空格**
- 最好是使用横线和下划线来分离单词

## 网页结构

-images/
-styles/
-scripts/
-index.html

``` html
//index.html内容
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <img src="" alt="My test image">
  </body>
</html>
```

## HTML

> HTML并不是真正的的程序语言，他是一种标记语言，用来结构化和含义化你想要放在web网站上的那些内容。它由一系列的元素（elements）所组成，这些元素可以用来封装你的内容中担任不同工作的各部分和各个角色。 闭合标签（ tags）可以使得一个文字或者一张图片连接到其他网址，可以使得文字为斜体，可让文字变大或者变小等等。

### html元素

组成：

- 开始标签（The opening tag）：这里包含了元素的名称（这里是 p），被开、闭尖括号所包围。这表示这里是这个元素的开始发挥作用——在这个例子中从这一段的开头开始。
- 闭合标签（The closing tag）：与开始标签相似，只是其中在元素名之前包含了一个斜杠。表明这里是元素的结尾——在这个例子中，就是这一段落的结尾。
- 内容（The content）：这是一个元素的内容，这个例子中就是所输入的文本本身。
- 元素（The element）：开标签、闭标签与内容相结合，便是一个完整的元素。
> 元素可以有Attribute属性,属性应该包含：
- 在属性与元素名称或上一个属性（如果有超过一个属性的话）之间的空格符
- 属性的名称，并接上一个等号
- 由引号所包围的属性值

#### 嵌套元素

你也可以将一个元素置于其他元素之中——这被称作嵌套.

#### 空元素

有一些元素并不包含内容，它们被称为空元素。如`<img>` 元素。

---

## `<img>`标签

``` html
//alt 属性建议必填
<img src="images/firefox-icon.png" alt="My test image">
```
