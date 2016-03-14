---
layout: page
title: 实用工具
---

在Primer中还一些快速处理行为，浮动，颜色，对齐等的实用工具。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 截断

`css-truncate`将使文本变短并用省略号替代。可以通过重写.css-truncate-target的最大宽度来改变被截断文本的最大宽度。

{% example html %}
<span class="branch-ref css-truncate css-truncate-target">
  really-long-branch-name
</span>
{% endexample %}

你可以通过添加`.expandable`使得在鼠标悬停时显示所有文本。

{% example html %}
<span class="css-truncate expandable">
  <span class="branch-ref css-truncate-target">this-is-a-really-long-branch-name</span>
</span>
{% endexample %}

## 计数器

在导航中添加一个额外的计数器用来显示一个数字或者是未读指示。

{% example html %}
<span class="counter">9</span>
{% endexample %}

## 浮动

快速的浮动某个东西到左边或者右边，并且在之后清除浮动。

{% example html %}
<div class="clearfix">
  <code class="left">.left</code>
  <code class="right">.right</code>
</div>
{% endexample %}

## 内容居中

如果**块状级别内容**没有占满父元素的所有宽度，那么很容易是他的内容居中。可以使用在[栅格列](/layout/#centered)上或者其让任何元素。

{% example html %}
<nav class="menu centered">
  <a class="menu-item selected" href="#">Account</a>
  <a class="menu-item" href="#">Profile</a>
  <a class="menu-item" href="#">Emails</a>
  <a class="menu-item" href="#">Notifications</a>
</nav>
{% endexample %}


## 文本对齐

在元素上使用一个类改变文本对齐`text-align`。

{% example html %}
<p class="text-left">Left aligned text.</p>
<p class="text-right">Right aligned text.</p>
<p class="text-center">Center aligned text.</p>
{% endexample %}

## 文本颜色

在一个元素上使用一个雷改变文本颜色`color`。

{% example html %}
<p class="text-open">Green/open text</p>
<p class="text-closed">Red/closed text</p>
<p class="text-merged">Merged text</p>
<p class="text-pending">Pending text</p>
{% endexample %}

`.text-closed`和`.text-failure` 是一样的，同样`.text-open`和`.text-success`也是一样。

## 柔和的链接

当你需要一个不是蓝色底板的超链接时，使用`.muted-link`。

{% example html %}
Here is some example text. <a class="muted-link" href="#">And a muted link.</a>
{% endexample %}

## 灵活的表格

灵活表格是一个模型，它是为了创建动态可调整可以放在一行上的元素（比如，他们总是不会再一个新行上）。
在我们的CSS中使用表格样式意味着它是跨浏览器友好的，可以至少在IE9上。

额外的外边距`margin`和内边距`padding`可能需要用来修正内容的空间。

{% example html %}
<div class="flex-table">
  <div class="flex-table-item flex-table-item-primary">
    <input class="input-block" type="text" placeholder="Long flexible input form">
  </div>
  <div class="flex-table-item">
    <button class="btn" type="button">Button</button>
  </div>
</div>
{% endexample %}
