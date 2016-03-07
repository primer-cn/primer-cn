---
layout: page
title: 表单
---

控制独特的表单风格并利用通用的布局。

<div class="flash">
  <strong>注意！</strong> 表单需要一些重写来清除特性并需要一些标记。我们马上就会学到！
</div>

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## 概述

- 为了兼容不同浏览器和简化以后的操作，我们重置一些元素的默认样式。这包括`<fieldset>`，WebKit验证泡沫，和大部分文本的`<input>`。
- 具体类型的文本`<input>`设置了自动的样式，但是`.form-control`可能是你需要的。
- 永远在你的`<button>`上声明一个`type`。
- 表单依赖表单组布局。

## 表单示例

Primer中的表单控制现在没有基本的特定布局（这取决于设计）。你需要使用`<fieldset>`，`<div>`，或者其他的元素和
样式来重新调整它们。

{% example html %}
<form>
  <label for="name">Name</label>
  <input type="text" id="name">

  <label for="email">Email address</label>
  <input type="email" id="email">

  <label>
    <input type="checkbox"> Remember me
  </label>

  <label>
    <input type="radio" id="herp" name="herpderp" checked> Herp
  </label>
  <label>
    <input type="radio" id="derp" name="herpderp"> Derp
  </label>

  <button class="btn" type="submit">Submit</button>
</form>
{% endexample %}

## 对比度表单

文本表单默认有一个白色的背景。你可以通过添加`.input-contrast`将其改变为浅灰色。

{% example html %}
<form>
  <input type="text" placeholder="Default input">
  <input class="input-contrast" type="text" placeholder="Input with contrast">
</form>
{% endexample %}

## 大小

通过一个附加的类使输入框变小，变大，或者充满宽度。

### 迷你型

{% example html %}
<form>
  <input class="input-mini" type="text" placeholder="Mini input">
</form>
{% endexample %}

### 大型

{% example html %}
<form>
  <input class="input-large" type="text" placeholder="Large input">
</form>
{% endexample %}

### 块状

{% example html %}
<form>
  <input class="input-block" type="text" placeholder="Full-width input">
</form>
{% endexample %}

## 选择框

为了使所有浏览器可以一致的渲染文本框，Primer给`<select>`增加了轻微的`height`和`vertical-align`。

{% example html %}
<form>
  <select>
    <option>Choose an option</option>
    <option>Git</option>
    <option>Subversion</option>
    <option>Social Coding</option>
    <option>Beets</option>
    <option>Bears</option>
    <option>Battlestar Galactica</option>
  </select>
</form>
{% endexample %}

### 定制

定制的`<select>`也可以通过添加`.select`来获得。**只有最新版的WebKit,Firefox和IE浏览器才可用**。

{% example html %}
<form>
  <select class="select">
    <option>Choose an option</option>
    <option>Git</option>
    <option>Subversion</option>
    <option>Social Coding</option>
    <option>Beets</option>
    <option>Bears</option>
    <option>Battlestar Galactica</option>
  </select>
</form>
{% endexample %}

### 小型

使用`.select-sm`类来使默认的和定制的`<select>`调整大小，以适应[我们小型按钮](/buttons/#default-buttons)的尺寸。

{% example html %}
<select class="select-sm">
  <option>Choose an option</option>
  <option>Git</option>
  <option>Subversion</option>
  <option>Social Coding</option>
  <option>Beets</option>
  <option>Bears</option>
  <option>Battlestar Galactica</option>
</select>

<select class="select select-sm">
  <option>Choose an option</option>
  <option>Git</option>
  <option>Subversion</option>
  <option>Social Coding</option>
  <option>Beets</option>
  <option>Bears</option>
  <option>Battlestar Galactica</option>
</select>
{% endexample %}

## 表单群组

{% example html %}
<form>
  <dl class="form">
    <dt><label>Example Text</label></dt>
    <dd><input type="text" value="Example Value"></dd>
  </dl>

  <dl class="form">
    <dt><label>Example Label</label></dt>
    <dd>
      <select class="select">
        <option>Choose an option</option>
        <option>Git</option>
        <option>Subversion</option>
        <option>Social Coding</option>
        <option>Beets</option>
        <option>Bears</option>
        <option>Battlestar Galactica</option>
      </select>
    </dd>
  </dl>
</form>
{% endexample %}

## 表单组验证

给我们的表单群组传送错误和警告信息。在`<dl class="form">`中添加适当的类，`.errored`或者`.warn`。
然后把你的错误信息放在一个附加的`<dd>`中，使用`.error`或者`.warning`。

{% example html %}
<form>
  <dl class="form errored">
    <dt><label>Example Text</label></dt>
    <dd><input type="text" value="Example Value"></dd>
    <dd class="error">This example input has an error.</dd>
  </dl>
  <br>
  <dl class="form warn">
    <dt><label>Example Text</label></dt>
    <dd><input type="text" value="Example Value"></dd>
    <dd class="warning">This example input has a warning.</dd>
  </dl>
</form>
{% endexample %}

## 复选框和单选按钮

使文本和方框对齐并给复选框和单选按钮控制添加样式。

{% example html %}
<form>
  <div class="form-checkbox">
    <label>
      <input type="checkbox" checked="checked">
      Available for hire
    </label>
    <p class="note">
      This will do insanely <strong>awesome</strong> and <strong>amazing</strong> things!
    </p>
  </div>
</form>
{% endexample %}

你可能也要给标签添加强调：

{% example html %}
<form>
  <div class="form-checkbox">
    <label>
      <input type="checkbox" checked="checked">
      <em class="highlight">Available for hire</em>
    </label>
  </div>
</form>
{% endexample %}

## 输入框组

使输入框和按钮相互附着。

{% example html %}
<form>
  <div class="input-group">
    <input type="text" placeholder="Username">
    <span class="input-group-button">
      <button class="btn">
        <span class="octicon octicon-clippy"></span>
      </button>
    </span>
  </div>
</form>
{% endexample %}

## 表单行为

通过`float:right`使带有`.form-actions`表单中的按钮右对齐。已经为你自动清除了漂浮。

{% example html %}
<div class="form-actions">
  <button type="button" class="btn btn-primary">Save changes</button>
  <button type="button" class="btn">Cancel</button>
</div>
{% endexample %}
