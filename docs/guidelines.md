---
layout: page
title: 代码指南
---

最佳实践和指南，为了写出亲切格式、语句等的HTML和CSS。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## HTML

### 基本格式

* 使用软件标签的两个空格作为缩进。空格是保证代码在任何人的环境中都显示一致的唯一方式。
* 文本的段落应该使用使用`<p>`标签。永远不要连续使用多个`<br>`标签。
* 表单中的项目列表总是应该使用`<ul>`,`<ol>`,或者`<dl>`。永远不要使用一堆的`<div>`或者`<p>`。
* 每个表单中输入框的附加文本都应该使用`<label>`标签。**特别是单选框和多选框元素。**
* 即使属性的引号是可选的，为了可读性总是在属性的两边加上引号。
* 避免在注释中书写关闭标签，如`<!-- /.element -->`。这只会增加页面的加载时间。另外，大多数编辑器有缩进标线和开关标签的高亮显示。
* 避免在字闭合元素中中添加斜杠。如`<br>`,`<hr>`,`<img>`和`<input>`。
* 不要手动设置标签下标`tabindex`——应该依赖于浏览器的顺序设置。

{% highlight html %}
<p class="line-note" data-attribute="106">
  This is my paragraph of special text.
</p>
{% endhighlight %}

### 布尔属性

许多属性不需要设置一个值，比如`disabled`或者`checked`，随意不要忘记他们(布尔值)。

{% highlight html %}
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
  <option value="1" selected>1</option>
</select>
{% endhighlight %}

更多的信息，[阅读WhatWG section](http://www.whatwg.org/specs/web-apps/current-work/multipage/common-microsyntaxes.html#boolean-attributes)。

### 精简标签

只要可能，避免在HTML中使用过多的父元素。很多时候这要求反复检查和重构，但是产生更少的HTML。例如：

{% highlight html %}
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
{% endhighlight %}

### 表单

* 倾向于单选框或者复选框列表，而不是选择菜单。
* 把单选框和多选输入框以及他们的文本包装在`<label>`中。这里不需要`for`属性——包装自动关联两个标签。
* 表单按钮应该总是包含一个明显的类型`type`。为主要的按钮使用`type="submit"`按钮和普通的按钮使用`type="button"`。
* 主要的表单按钮必须第一次展示在DOM中，特别是那些有多个确定按钮的表单。每个按钮的视觉排序应该使用`float:right;`。

### 表格

在适当的地方使用`<thead>`,`<tfoot>`,`<tbody>`和··==`<th>`标签（和`scope`属性）。
（注意：为了速度应该把`<tfoot>`放在`<tbody>`标签之前。你希望浏览器在在家一个完整的表格数据之前加载表格底部。）

{% highlight html %}
<table summary="This is a chart of invoices for 2011.">
  <thead>
    <tr>
      <th scope="col">Table header 1</th>
      <th scope="col">Table header 2</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Table footer 1</td>
      <td>Table footer 2</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Table data 1</td>
      <td>Table data 2</td>
    </tr>
  </tbody>
</table>
{% endhighlight %}

## SCSS

### 空格

* 使用软件标签的两个空格作为缩进。空格是保证代码在任何人的环境中都显示一致的唯一方式。
* 属性声明时在冒号`:`后面加上空格符。
* 规则声明时在冒号`:`后面加上空格符。
* 当分类选择器时，保持个体选择器在同一行上。
* 声明代码块时在新的一行上加上关闭大口号。
* 为了更精确的错误报告，每一个声明应该出现在它自己的行内。

### 格式化

* 使用十六进制颜色代码`#000`，除非在原始的CSS中使用`rgba()`(SCSS的`rgba()`被重载为接收十六进制颜色作为一个参数的函数，例如`rgba(#000, .5)`)。
* 在注视块使用`//`代替使用`/* */`。
* 避免0值的单位指定，例如，使用`margin: 0;`代替`margin: 0px`。
* 努力限制使用实例的声明，你必须明确的设置所有变量的值。

### 混合

As a rule of thumb, avoid unnecessary nesting in SCSS. At most, aim for three levels. If you cannot help it, step back and rethink your overall strategy (either the specificity needed, or the layout of the nesting).
作为一个最重要的规则，在SCSS中避免不必要的嵌套。最多的目标是三个层次。如果这不够多，退后一步重新思考你的整体设计
（不是特定的需求，就是嵌套的布局）。

### 例子

这里是一些遵循上面准则的好例子：

{% highlight scss %}
// Example of good basic formatting practices
.styleguide-format {
  color: #000;
  background-color: rgba(0, 0, 0, .5);
  border: 1px solid #0f0;
}

// Example of individual selectors getting their own lines (for error reporting)
.multiple,
.classes,
.get-new-lines {
  display: block;
}

// Avoid unnecessary shorthand declarations
.not-so-good {
  margin: 0 0 20px;
}
.good {
  margin-bottom: 20px;
}
{% endhighlight %}

## 文件结构

通常的，一个平行的文件目录是最好的，但是在GitHub上我们通过包bundles(分离编译过的CSS文件)和款式sections(关联内容的目录)来分离文件。

### Bundles

GitHub.com使用少量的包。这里是简化后的代表我们的两个桌面包(分开来支持IE9的最大选择器并限制每个CSS文件)和一个专门供我们手机展示的手机包。

{% highlight bash %}
stylesheets
├── github
│   ├── base.scss
│   ├── layout.scss
│   └── buttons.scss
├── github2
│   ├── about.scss
│   └── blog.scss
└── mobile
    ├── base.scss
    └── files.scss
{% endhighlight %}

### 包含(S)CSS文件

前面我们再Primer和Github上使用[Sprockets](https://github.com/sstephenson/sprockets)来**引入**文件。
现在，我们使用明确的列表**imports**来控制层叠，特性等。

{% highlight scss %}
// Imports
@import "primer";
@import "component";
@import "another_component";

// Rules
.rule { ... }
{% endhighlight %}

Primer样式也是这样被包含的，在你需要他们的时候。

## 像素 vs. 字体尺寸

在字体大小`font-size`中使用像素`px`，因为它提供对文本的绝对控制。此外，没有单位的行高`line-height`是首选因为它不继承它父元素的百分比值，
而是基于和字体大小`font-size`的乘积。

## 类命名约定

决不在CSS文件中使用`js-`开头的类名。`js-`仅仅是在JS文件中使用。

使用`is-`开头的规则在CSS和JS中都可以使用。

## 特性 (classes vs. ids)

在一个页面中会出现**仅仅一次**的元素应该使用ID，否则，使用类。当有疑问的时候，使用类名。

* **好**的id使用场景：头部，底部，弹出框模块。
* **坏**的id使用场景：导航，列表项，试图页面项(如：问题试图)。

当设计一个组件时，开始于一个元素+类空间（选择类名而不是ID），默认的选择直接子选择器，并尽可能少的使用特性。
这里是个好的例子：

{% highlight html %}
<ul class="category-list">
  <li class="item">Category 1</li>
  <li class="item">Category 2</li>
  <li class="item">Category 3</li>
</ul>
{% endhighlight %}

{% highlight scss %}
.category-list { // element + class namespace

  // Direct descendant selector > for list items
  > li {
    list-style-type: disc;
  }

  // Minimal specificity for all links
  a {
    color: #f00;
  }
}
{% endhighlight %}

### CSS特性规范

* 如果你必须使用一个id选择器（`$selector`），确保在你的规则定义中你会有多余*一个*。一个像`#header .search #quicksearch{ ... }`这样的规则是被视为有害的。
* 当修改一个存在的元素为特定用法时，尝试使用特定的类名。代替`.listings-layout.bigger`为使用规则如`.listings-layout.listings-bigger`。
考虑在你的未来代码中方便查找`ack/grep`。
* 类名`disabled`,`mousedown`,`dang`,`hover`,`selected`和`active`应该*总是*用来作为类的命名空间（`button.selected`是一个好例子）。
