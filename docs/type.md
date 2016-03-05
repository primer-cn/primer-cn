---
layout: page
title: 排版
---

标题，段落，块引用，列表，和更多拥有全局属性的重置。值得注意的是这和我们的Markdown样式不一样。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 标题

{% example html %}
<h1>h1. Primer heading</h1>
<h2>h2. Primer heading</h2>
<h3>h3. Primer heading</h3>
<h4>h4. Primer heading</h4>
<h5>h5. Primer heading</h5>
<h6>h6. Primer heading</h6>
{% endexample %}

## 正文文本

{% example html %}
<p>Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nullam id dolor id nibh ultricies vehicula.</p>
<p>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec ullamcorper nulla non metus auctor fringilla. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Donec ullamcorper nulla non metus auctor fringilla.</p>
<p>Maecenas sed diam eget risus varius blandit sit amet non magna. Donec id elit non mi porta gravida at eget metus. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit.</p>
{% endexample %}

## 领头

通过添加`.lead`使一个段落突出。

{% example html %}
<p class="lead">
  Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus.
</p>
{% endexample %}

## 行内文本元素

为普通行内HTML元素添加样式。

{% example html %}
<p>You can use the mark tag to <mark>highlight</mark> text.</p>
<p><del>This line of text is meant to be treated as deleted text.</del></p>
<p><s>This line of text is meant to be treated as no longer accurate.</s></p>
<p><ins>This line of text is meant to be treated as an addition to the document.</ins></p>
<p><u>This line of text will render as underlined</u></p>
<p><small>This line of text is meant to be treated as fine print.</small></p>
<p><strong>This line rendered as bold text.</strong></p>
<p><em>This line rendered as italicized text.</em></p>
{% endexample %}

## 块引用

任何使用`<blockquote>`包装任何<abbr title="HyperText Markup Language">HTML</abbr>作为引用。为了直接引用，我们推荐加一个`<p>`。

{% example html %}
<blockquote>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
</blockquote>
{% endexample %}

## 列表

<div class="flash">
  <strong>Heads up!</strong> The broken display of lists is <strong>intentional</strong> as Primer globally resets these elements for the time being. This will eventually be undone in the next major version.
</div>

### 无序的

一系列项目，它们*没有*明确的顺序。

{% example html %}
<ul>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Nulla volutpat aliquam velit
    <ul>
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ul>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ul>
{% endexample %}

### 有序的

一系列项目，它们*有*明确的顺序。

{% example html %}
<ol>
  <li>Lorem ipsum dolor sit amet</li>
  <li>Nulla volutpat aliquam velit
    <ol>
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ol>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ol>
{% endexample %}
