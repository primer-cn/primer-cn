---
layout: page
title: 布局
---

Primer的布局包括基本页面容器和一个单一管理区，基于分数的网格系统。那听起来远比它实际的要复杂——
只不过是容器，行，和列。

你可以在`_layout.scss`中找到以下所有样式。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 容器

使用`.container`让你的页面内容居中。

{% highlight html %}
<div class="container">
  <!-- contents here -->
</div>
{% endhighlight %}

容器通过`width: 980px;`和使用水平的`margin`来使内容居中。

## 网格

### 原理

当在行中使用`.columns`并在具体每一列中使用column类和分数类就会生成一个标准好看的网格。
这里是它的工作原理：

- 增加一个`.container`来封装所有事情并提供足够的水平空间。
- 使用`<div class="columns">`来创建行，并清除列之间的漂浮。
- 使用`<div calss="column">`增加列。
- 增加分数宽度形式的类来设置列的宽度(例如,`.one-fourth`)。

### 演示

实际中，你的列将会看起来像下面的例子这样。

{% example html %}
<div class="container">
  <div class="columns">
    <div class="one-fifth column">
      .one-fifth
    </div>
    <div class="four-fifths column">
      .four-fifths
    </div>
  </div>

  <div class="columns">
    <div class="one-fourth column">
      .one-fourth
    </div>
    <div class="three-fourths column">
      .three-fourths
    </div>
  </div>

  <div class="columns">
    <div class="one-third column">
      .one-third
    </div>
    <div class="two-thirds column">
      .two-thirds
    </div>
  </div>

  <div class="columns">
    <div class="one-half column">
      .one-half
    </div>
    <div class="one-half column">
      .one-half
    </div>
  </div>
</div>
{% endexample %}

### 居中

可以在`.column`类中添加`centered`使列[居中](/utilities/#centering-content)。

{% example html %}
<div class="columns">
  <div class="one-half column centered">
    .one-half
  </div>
</div>
{% endexample %}