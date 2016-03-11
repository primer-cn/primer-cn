---
layout: page
title: 白板
---

白板是为了当一个页面或者章节上缺少内容的时候出现的。把它们当做一个占位符来告诉用户为什么在这里会缺少信息。
也一定要提供一个行为了添加内容。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 基础的例子

在一些内容的外面使用`.blankslate`包装让它表现为白板的外观。

{% example html %}
<div class="blankslate">
  <h3>This is a blank slate</h3>
  <p>Use it to provide information when no dynamic content exists.</p>
</div>
{% endexample %}

## 带图标

当帮助消息中包含`.mega-octicon`并作为白板的第一个元素时。
一定要使用相关的图标。

{% example html %}
<div class="blankslate">
  <span class="mega-octicon octicon-git-commit"></span>
  <span class="mega-octicon octicon-tag"></span>
  <span class="mega-octicon octicon-git-branch"></span>
  <h3>This is a blank slate</h3>
  <p>Use it to provide information when no dynamic content exists.</p>
</div>
{% endexample %}

## 变化

在`.blankslate`中添加一个额外的可选类来该表它的外观。

### 调整宽度

缩小白板容器的大小来不占领所有可用的宽度。

{% example html %}
<div class="blankslate has-fixed-width">
  <h3>This is a blank slate</h3>
  <p>Use it to provide information when no dynamic content exists.</p>
</div>
{% endexample %}

### 加盖的

删除顶部角落的边框半径`border-radius`。

{% example html %}
<div class="blankslate capped">
  <h3>This is a blank slate</h3>
  <p>Use it to provide information when no dynamic content exists.</p>
</div>
{% endexample %}

### 扩大的

显著地增加垂直填充。

{% example html %}
<div class="blankslate spacious">
  <h3>This is a blank slate</h3>
  <p>Use it to provide information when no dynamic content exists.</p>
</div>
{% endexample %}

### 无背景

去除背景颜色`background-color`和边框`border`

{% example html %}
<div class="blankslate clean-background">
  <h3>This is a blank slate</h3>
  <p>Use it to provide information when no dynamic content exists.</p>
</div>
{% endexample %}
