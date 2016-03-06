---
layout: page
title: 按钮
---

按钮用于**行为**，比如在表单中，而超链接文本用于**目的地**，或者从一个页面跳转到另一个页面。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 默认按钮

使用标准的——而非经典的——`.btn`作用图表单行为和基本的页面行为 。这些广泛的在网站中使用。

当使用一个`<button>`元素时， **总是需要指定一个`type`** 。当使用一个 `<a>` 元素时， **为了可到达总是需要添加`role="button"`** 。

{% example html %}
<button class="btn" type="button">Button button</button>
<a class="btn" href="#" role="button">Link button</a>
{% endexample %}

你可以使用两种尺寸：默认大小`.btn`和小尺寸的`.btn-sm`。

{% example html %}
<button class="btn" type="button">Button</button>
<button class="btn btn-sm" type="button">Small button</button>
{% endexample %}

## 原色

原色按钮是绿色的，它被用来表明页面中的*主要*行为。当你需要突出你的按钮时，使用`.btn .btn-primary`。
你可以使用两种按钮尺寸——只是增加`.btn-primary`。

{% example html %}
<button class="btn btn-primary" type="button">Primary button</button>
<button class="btn btn-sm btn-primary" type="button">Small primary button</button>
{% endexample %}

## 危险

危险按钮是红色的。它们用来帮助强调接下来的行为是重要的或者可能是危险的（比如，删除一个仓库或者转移所有权）。
和原色按钮类似，只是增加`.btn-danger`。

{% example html %}
<button class="btn btn-danger" type="button">Danger button</button>
<button class="btn btn-sm btn-danger" type="button">Small danger button</button>
{% endexample %}

## 轮廓

轮廓按钮将行为轻描淡写使它们显得像一个方方正正的链接。只要添加`.btn-outline`就可以了。

{% example html %}
<button class="btn btn-outline" type="button">Outline button</button>
<button class="btn btn-sm btn-outline" type="button">Outline button</button>
{% endexample %}

## 不可用状态

在`<button>`元素中使用`disabled`属性，在`<a>`标签中使用`.disabled`类来使按钮不可用。

{% example html %}
<button class="btn" type="button" disabled>Disabled button</button>
<a class="btn disabled" href="#" role="button">Disabled button</a>
{% endexample %}

在原色，危险和轮廓按钮中也是类似的样式：

{% example html %}
<button class="btn btn-primary" type="button" disabled>Disabled button</button>
<a class="btn btn-primary disabled" href="#" role="button">Disabled button</a>
{% endexample %}

{% example html %}
<button class="btn btn-danger" type="button" disabled>Disabled button</button>
<a class="btn btn-danger disabled" href="#" role="button">Disabled button</a>
{% endexample %}

{% example html %}
<button class="btn btn-outline" type="button" disabled>Disabled button</button>
<a class="btn btn-outline disabled" href="#" role="button">Disabled button</a>
{% endexample %}

## 块按钮

通过添加`.btn-block`使任何按钮充满整个宽度。它增加了`width: 100%`，`diplay`由`inline-block`改变到`block`，并居中按钮文本。

{% example html %}
<p><button class="btn btn-block" type="button">Block button</button></p>
<p><button class="btn btn-sm btn-block" type="button">Small block button</button></p>
{% endexample %}

## 计数

你可以为**小按钮**简单的添加一个计数。在`.btn-sm`中增加`.with-count`类，然后在按钮后面增加`.social-count`。

**一定要在附加的类上清除浮动。**

{% example html %}
<div class="clearfix">
  <a class="btn btn-sm btn-with-count" href="#" role="button">
    <span class="octicon octicon-eye"></span>
    Watch
  </a>
  <a class="social-count" href="#">6</a>
</div>
{% endexample %}

你也可以在按钮中使用[counter](../utilities/#counter)组件：

{% example html %}
<button class="btn" type="button">
  Button
  <span class="counter">12</span>
</button>

<button class="btn btn-primary" type="button">
  Button
  <span class="counter">12</span>
</button>

<button class="btn btn-danger" type="button">
  Button
  <span class="counter">12</span>
</button>

<button class="btn btn-outline" type="button">
  Button
  <span class="counter">12</span>
</button>
{% endexample %}

## 按钮组

渴望一系列的按钮一个接着一个吗？把他们包裹在`.btn-group`里面，然后按钮将会团在一起并按照分组自动隔开。

{% example html %}
<div class="btn-group">
  <button class="btn" type="button">Button</button>
  <button class="btn" type="button">Button</button>
  <button class="btn" type="button">Button</button>
</div>

<div class="btn-group">
  <button class="btn btn-outline" type="button">Button</button>
  <button class="btn btn-outline" type="button">Button</button>
  <button class="btn btn-outline" type="button">Button</button>
</div>

<div class="btn-group">
  <button class="btn btn-sm" type="button">Button</button>
  <button class="btn btn-sm" type="button">Button</button>
  <button class="btn btn-sm" type="button">Button</button>
</div>
{% endexample %}

在`.btn-group`中的`<form`上添加`.button_to`可以显示适当的间距和圆角。

**注意！**这个类名有一定的矛盾，在接下来的主要版本中将要改变。

{% example html %}
<div class="btn-group">
  <form class="button_to">
    <button class="btn" type="button">Button in a form</button>
  </form>
  <button class="btn" type="button">Button</button>
  <button class="btn" type="button">Button</button>
</div>
{% endexample %}

## 隐藏文本按钮

使用`.hidden-text-expander`来指示和切换隐藏文本。

{% example html %}
<span class="hidden-text-expander">
  <a href="#">&hellip;</a>
</span>
{% endexample %}

你也可以通过添加`.inline`来使隐藏的内容在行内出现。
