---
layout: page
title: 导航
---

Primer有几个导航组件。有些以单一的目标设计的，但其他的为了更加灵活而设计的，并且使用频率很高。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 菜单

菜单是垂直列表的导航链接。**你必须设置菜单的宽度和位置。**如果你喜欢，只要使用我们的表格列作为父节点，并且设置一自定义的`width`。

{% example html %}
<nav class="menu">
  <a class="menu-item selected" href="#">Account</a>
  <a class="menu-item" href="#">Profile</a>
  <a class="menu-item" href="#">Emails</a>
  <a class="menu-item" href="#">Notifications</a>
</nav>
{% endexample %}

还有一些和菜单一起工作很好的子组件和附加组件，包括头像，计数器，和图标。

{% example html %}
<nav class="menu">
  <a class="menu-item selected" href="#">
    <span class="octicon octicon-tools"></span>
    Account
  </a>
  <a class="menu-item" href="#">
    <span class="octicon octicon-person"></span>
    Profile
  </a>
  <a class="menu-item" href="#">
    <span class="octicon octicon-mail"></span>
    Emails
  </a>
  <a class="menu-item" href="#">
    <span class="octicon octicon-radio-tower"></span>
    <span class="counter">3</span>
    Notifications
  </a>
</nav>
{% endexample %}

你也可以随意地给菜单增加标题。感觉自由地使用近乎语义要素的`.menu-heading`类，包括行内元素，标题，和其他更多的。

{% example html %}
<nav class="menu">
  <span class="menu-heading">Menu heading</span>
  <a class="menu-item selected" href="#">Account</a>
  <a class="menu-item" href="#">Profile</a>
  <a class="menu-item" href="#">Emails</a>
  <a class="menu-item" href="#">Notifications</a>
</nav>
{% endexample %}


## 标签导航

当你需要在不同视图之间进行切换时，考虑使用标签导航。它将给你提供一行左对齐的水平标签！

{% example html %}
<div class="tabnav">
  <nav class="tabnav-tabs">
    <a href="#" class="tabnav-tab selected">Foo tab</a>
    <a href="#" class="tabnav-tab">Bar tab</a>
  </nav>
</div>
{% endexample %}

在`.tabnav`中的添加附加元素时使用`.right`。

{% example html %}
<div class="tabnav">
  <a class="btn btn-sm right" href="#">Button</a>
  <nav class="tabnav-tabs">
    <a href="#" class="tabnav-tab selected">Foo Tab</a>
    <a href="#" class="tabnav-tab">Bar Tab</a>
  </nav>
</div>
{% endexample %}

附件的少量文本和链接可以使用`.tabnav-extra`来优化配置样式：

{% example html %}
<div class="tabnav">
  <div class="tabnav-extra right">
    Tabnav widget text here.
  </div>
  <nav class="tabnav-tabs">
    <a href="#" class="tabnav-tab selected">Foo Tab</a>
    <a href="#" class="tabnav-tab">Bar Tab</a>
  </nav>
</div>
{% endexample %}

{% example html %}
<div class="tabnav">
  <div class="right">
    <a class="tabnav-extra" href="#">
      Tabnav extra link
    </a>
    <a class="tabnav-extra" href="#">
      Tabnav extra link
    </a>
  </div>
  <nav class="tabnav-tabs">
    <a href="#" class="tabnav-tab selected">Foo Tab</a>
    <a href="#" class="tabnav-tab">Bar Tab</a>
  </nav>
</div>
{% endexample %}

## 过滤器列表

一个垂直的过滤器列表。白色的背景灰色的文本。列表中被选择的部分将会充满蓝色背景并使文本变成白色。

{% example html %}
<ul class="filter-list">
  <li>
    <a href="#" class="filter-item selected">
      <span class="count">21</span>
      First filter
    </a>
  </li>
  <li>
    <a href="#" class="filter-item">
      <span class="count">3</span>
      Second filter
    </a>
  </li>
  <li>
    <a href="#" class="filter-item">
      Third filter
    </a>
  </li>
</ul>
{% endexample %}

## 面包屑导航

*即将到来...*
