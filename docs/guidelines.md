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

* Use hex color codes `#000` unless using `rgba()` in raw CSS (SCSS' `rgba()` function is overloaded to accept hex colors as a param, e.g., `rgba(#000, .5)`).
* Use `//` for comment blocks (instead of `/* */`).
* Avoid specifying units for zero values, e.g., `margin: 0;` instead of `margin: 0px;`.
* Strive to limit use of shorthand declarations to instances where you must explicitly set all the available values.

### Misc

As a rule of thumb, avoid unnecessary nesting in SCSS. At most, aim for three levels. If you cannot help it, step back and rethink your overall strategy (either the specificity needed, or the layout of the nesting).

### 例子

Here are some good examples that apply the above guidelines:

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

## File organization

In general, a flat directory of files works best, but at GitHub we break things down by bundles (separate compiled CSS files) and sections (directories of related content).

### Bundles

GitHub.com uses a handful of bundles. Here's a simplified representation of our two desktop bundles (split to support IE9's maximum selector limit per CSS file) and a dedicated mobile bundle for our separate mobile views.

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

### Including (S)CSS files

Previously we used [Sprockets](https://github.com/sstephenson/sprockets) to **require** files in Primer and at GitHub. Nowadays, we use explicit lists of **imports** to control the cascade, specificity, and more.

{% highlight scss %}
// Imports
@import "primer";
@import "component";
@import "another_component";

// Rules
.rule { ... }
{% endhighlight %}

This is also how Primer's styles are to be included, should you need them.

## Pixels vs. ems

Use `px` for `font-size`, because it offers absolute control over text. Additionally, unit-less `line-height` is preferred because it does not inherit a percentage value of its parent element, but instead is based on a multiplier of the `font-size`.

## Class naming conventions

Never reference `js-` prefixed class names from CSS files. `js-` are used exclusively from JS files.

Use the `is-` prefix for state rules that are shared between CSS and JS.

## Specificity (classes vs. ids)

Elements that occur **exactly once** inside a page should use IDs, otherwise, use classes. When in doubt, use a class name.

* **Good** candidates for ids: header, footer, modal popups.
* **Bad** candidates for ids: navigation, item listings, item view pages (ex: issue view).

When styling a component, start with an element + class namespace (prefer class names over ids),  prefer direct descendant selectors by default, and use as little specificity as possible. Here is a good example:

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

### CSS Specificity guidelines

* If you must use an id selector (`#selector`) make sure that you have no more than *one* in your rule declaration. A rule like `#header .search #quicksearch { ... }` is considered harmful.
* When modifying an existing element for a specific use, try to use specific class names. Instead of `.listings-layout.bigger` use rules like `.listings-layout.listings-bigger`. Think about `ack/grep`ing your code in the future.
* The class names `disabled`, `mousedown`, `danger`, `hover`, `selected`, and `active` should *always* be namespaced by a class (`button.selected` is a good example).
