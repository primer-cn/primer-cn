---
layout: page
title: 脚手架
---

脚手架是指Primer建立的全局重置和依赖。

## 目录

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## HTML5文档类型

Primer使用确定的HTML元素和CSS属性，**要求**使用HTML5文档类型。
在你所有页面的开头包含它们。

{% highlight html %}
<!DOCTYPE html>
<html lang="en">
  ...
</html>
{% endhighlight %}

## 盒大小(Box-sizing)

我们在Primer里重置了所有元素的`box-sizing`为`border-box`。这允许我们更加简单的给那些拥有`padding`和`border`
属性的元素分配宽度。

## 建立在Normalize之上

为了改进跨浏览器渲染，我们使用 [Normalize.css](http://necolas.github.io/normalize.css/) 来更正跨浏览器和设备的一些小差异。