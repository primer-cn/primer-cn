---
layout: page
title: 通知
---

弹出消息，或者警告，告知用户成功信息或者待解决的行为。尽量少的使用它们。不要一次展示多个弹窗。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 默认的

弹出消息会在一个合适的地方出现——它们只是浅蓝色的圆角矩形。

{% example html %}
<div class="flash">
  Flash message goes here.
</div>
{% endexample %}

你可以把多个段落的文本放到一个弹出消息中——最后一个段落的底部`margin`将会被自动覆盖。

{% example html %}
<div class="flash">
  <p>This is a longer flash message in it's own paragraph. It ends up looking something like this. If we keep adding more text, it'll eventually wrap to a new line.</p>
  <p>And this is another paragraph.</p>
</div>
{% endexample %}

如果需求提升，你可以使用`.flash-messages`快速的把你的弹出消息和周围的内容分开。*注意下例中额外的上下边界*

{% example html %}
<div class="flash-messages">
  <div class="flash">
    Flash message goes here.
  </div>
</div>
{% endexample %}

## 变种

在弹出消息中添加`.flash-warn`或者`.flash-error`可以分别使它变成黄色和红色。

{% example html %}
<div class="flash flash-warn">
  Flash message goes here.
</div>
{% endexample %}

{% example html %}
<div class="flash flash-error">
  Flash message goes here.
</div>
{% endexample %}

## 带图标

在弹出消息的左侧添加一个图标让它展现出时髦并吸引注意力。只需要添加`.flash-with-icon`和你的图标。

{% example html %}
<div class="flash flash-with-icon">
  <span class="octicon octicon-alert"></span>
  Flash message with an icon goes here.
</div>
{% endexample %}

## 解散

在任何弹出消息的右侧添加一个JavaScript使它可以解散(关闭)的图标。

{% example html %}
<div class="flash">
  <span class="octicon octicon-x flash-close js-flash-close"></span>
  Dismissable flash message goes here.
</div>
{% endexample %}
