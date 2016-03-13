---
layout: page
title: 工具提示
---

完全在CSS中给任何元素周围添加工具提示。只需要添加一些类和一个独条标签`aria-label`属性。

另外，你还要指定一个方向：

- `.tooltipped-n`
- `.tooltipped-ne`
- `.tooltipped-e`
- `.tooltipped-se`
- `.tooltipped-s`
- `.tooltipped-sw`
- `.tooltipped-w`
- `.tooltipped-nw`

工具提示类将会和图标类产生冲突，因此，必须要在父元素代替图标。

{% example html %}
<span class="tooltipped tooltipped-n" aria-label="This is the tooltip.">
  Text with a tooltip
</span>
{% endexample %}
