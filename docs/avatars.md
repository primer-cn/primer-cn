---
layout: page
title: 头像
---

头像是用户可以设置他们轮廓照相的图片。在Github上，它们一直是圆角正方形的。
它们可以是用户上传的自定义照片，或者系统生成用于识别的占位图片。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 基础的例子

在任何`<img>`元素添加`.avatar`使它成为一个头像。这重置了一些对齐的关键样式，解决Firefox图像占位的一个错误，并且使棱角变圆。

为了最大化浏览器性能吗，一定要设置宽度`width`和高度`height`属性。

{% example html %}
<img class="avatar" src="https://avatars3.githubusercontent.com/u/9919?v=3&s=144" width="72" height="72">
{% endexample %}

## 小头像

我们偶尔的使用小头像。任何小于`48px`宽度的头像都应该包含`.avatar-small`调节类，用来重置边框半径`border-radius`为一个更加适当的级别。

{% example html %}
<img class="avatar avatar-small" src="https://avatars3.githubusercontent.com/u/9919?v=3&s=64" width="32" height="32">
{% endexample %}

## 父子头像

当你需要一个大的父头像，和一个小的字头像，并轻微的叠加在一起时，使用父子(parent-child)类。

{% example html %}
<div class="avatar-parent-child left">
  <img class="avatar" src="https://avatars3.githubusercontent.com/u/9919?v=3&s=96" width="48" height="48">
  <img class="avatar avatar-child" src="https://avatars3.githubusercontent.com/u/9919?v=3&s=40" width="20" height="20">
</div>
{% endexample %}
