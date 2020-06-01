---
layout: post
title:  "javascript学习笔记"
subtitle:   持续更新中。。。
date:   2020-05-21
author:   tanzhaaa
header-img: img/post-bg-debug.png
catalog: true
tags: 
    - javascript
    - 学习笔记
---

* content
{:toc}

~~更新中~~


# 第一章：基本用法


HTML 中的脚本必须位于 `<script> `与 `</script> `标签之间。

脚本可被放置在 HTML 页面的` <body>` 和 `<head>` 部分中。

可以把JavaScript函数放置到HTML页面的`<head>`部分，也可以放在` <body>` ，

也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。

外部 JavaScript 文件的文件扩展名是 .js。

如需使用外部文件，请在` <script>` 标签的 "src" 属性中设置该 .js 文件：

举例

    <!DOCTYPE html>
    <html>
    <body>
    <script src="myScript.js"></script>
    </body>
    </html>

myScript.js的内容：

    alert("我的第一个 JavaScript");


**对于外部的jS就不需要在头尾有 `<script>` 标签了**


# 第二章:JS的输出

JavaScript 没有任何打印或者输出的函数。
但是显示数据有以下几种方法:

JavaScript 可以通过不同的方式来输出数据：

+ 使用 window.alert() 弹出警告框。
+ 使用 document.write() 方法将内容写到 HTML 文档中。
+ 使用 innerHTML 写入到 HTML 元素。
+ 使用 console.log() 写入到浏览器的控制台。

## 操作HTML元素:

如需从 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。

请使用 "id" 属性来标识 HTML 元素，并 innerHTML 来获取或插入元素内容：

    <!DOCTYPE html>
    <html>
    <body>

    <h1>我的第一个 Web 页面</h1>

    <p id="demo">我的第一个段落</p>

    <script>
    document.getElementById("demo").innerHTML = "段落已修改。";
    </script>

    </body>
    </html>

document.getElementById("demo") 是使用 id 属性来查找 HTML 元素的 JavaScript 代码 。

innerHTML = "段落已修改。" 是用于修改元素的 HTML 内容(innerHTML)的 JavaScript 代码。

## JavaScript对变量赋值:

    var length = 16;                                  // Number 通过数字字面量赋值
    var points = x * 10;                              // Number 通过表达式字面量赋值
    var lastName = "Johnson";                         // String 通过字符串字面量赋值
    var cars = ["Saab", "Volvo", "BMW"];              // Array  通过数组字面量赋值
    var person = {firstName:"John", lastName:"Doe"};  // Object 通过对象字面量赋值

## JavaScript函数:

    function myFunction(a, b) {
        return a * b;                                // 返回 a 乘以 b 的结果
    }

## JavaScript变量:
变量名称对大小写敏感（y 和 Y 是不同的变量）
    
    var pi=3.14;
    var person="John Doe";
    var lastname="Doe", age=30, job="carpenter";    //您可以在一条语句中声明很多变量。该语句以 var 开头，并使用逗号分隔变量即可：
    var x,y,z=1;    //一条语句中声明的多个不可以赋同一个值:

## JavaScript 对象
在 JavaScript中，几乎所有的事物都是对象。

        var person = {
        firstName:"John",
        lastName:"Doe",
        age:50,
        eyeColor:"blue"
    };


### 对象属性

可以说 "JavaScript 对象是变量的容器"。

但是，我们通常认为 "JavaScript 对象是键值对的容器"。

键值对通常写法为 name : value (键与值以冒号分割)。

键值对在 JavaScript 对象通常称为 对象属性。

### 访问对象属性

可以通过两种方式访问对象属性:

    person.lastName;
或者:

    person["lastName"];

### 对象方法

对象的方法定义了一个函数，并作为对象的属性存储。

对象方法通过添加 () 调用 (作为一个函数)。

该实例访问了 person 对象的 fullName() 方法:

    name = person.fullName();

如果你要访问 person 对象的 fullName 属性，它将作为一个定义函数的字符串返回：

    name = person.fullName;

### 访问对象方法

你可以使用以下语法创建对象方法：

*methodName : function() { code lines }*

你可以使用以下语法访问对象方法：

*objectName.methodName()*

通常 fullName() 是作为 person 对象的一个方法， fullName 是作为一个属性。

有多种方式可以创建，使用和修改 JavaScript 对象。

同样也有多种方式用来创建，使用和修改属性和方法。

## JavaScript 事件

HTML 事件是发生在 HTML 元素上的事情。

当在 HTML 页面中使用 JavaScript 时， JavaScript 可以触发这些事件。

### HTML 事件

HTML 事件可以是浏览器行为，也可以是用户行为。

以下是 HTML 事件的实例：

+ HTML 页面完成加载
+ HTML input 字段改变时
+ HTML 按钮被点击
通常，当事件发生时，你可以做些事情。

在事件触发时 JavaScript 可以执行一些代码。

HTML 元素中可以添加事件属性，使用 JavaScript 代码来添加 HTML 元素。

### 常见的HTML事件

下面是一些常见的HTML事件的列表:

 事件       |   描述
 ---        |   ----
onchange	|   HTML 元素改变
onclick	    |   用户点击 HTML 元素
onmouseover	|   用户在一个HTML元素上移动鼠标
onmouseout	|   用户从一个HTML元素上移开鼠标
onkeydown	|   用户按下键盘按键
onload	    |   浏览器已完成页面的加载

### JavaScript 可以做什么?
事件可以用于处理表单验证，用户输入，用户行为及浏览器动作:

+ 页面加载时触发事件
+ 页面关闭时触发事件
+ 用户点击按钮执行动作
+ 验证用户输入内容的合法性
+ 等等 ...
可以使用多种方法来执行 JavaScript 事件代码：

+ HTML 事件属性可以直接执行 JavaScript 代码
+ HTML 事件属性可以调用 JavaScript 函数
+ 你可以为 HTML 元素指定自己的事件处理程序
+ 你可以阻止事件的发生。
等等 ...



