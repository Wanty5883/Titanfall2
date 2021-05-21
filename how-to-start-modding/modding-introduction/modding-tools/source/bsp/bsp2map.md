---
description: BSP2MAP是一个由Skyler 'Zipster' York完成的GoldSource金源引擎的反编译器
---

# BSP2MAP

**BSP2MAP** 是一个由Skyler 'Zipster' York完成的[GoldSrc](https://developer.valvesoftware.com/wiki/GoldSrc)金源引擎的反编译器。它可以将[.bsp](https://developer.valvesoftware.com/wiki/BSP)格式转换为[.map](https://developer.valvesoftware.com/wiki/BSP)格式，由此可以加载到[Hammer编辑器](https://developer.valvesoftware.com/wiki/Hammer_Editor)中。 不幸的是，金源引擎的地图并不能够储存足够的地图绘制信息，所以几何体必须借由多边形来创建。BSP2MAP将所有基于画笔的实体掏空，并赋予其一个单位厚度，以此来复制并导出金源引擎中的地图。

{% hint style="danger" %}
最好不要使用这个反编译器，它的效率和精确度都没有另一个反编译器[WinBSPC](https://developer.valvesoftware.com/wiki/WinBSPC)要来的好。下面是一个对比：
{% endhint %}

![BSP2MAP &#x5C1D;&#x8BD5;&#x53CD;&#x7F16;&#x8BD1;&#x7684; HL crossfire.](../../../../../.gitbook/assets/crossfire_bsp2map.png)

![WinBSPC&apos;s &#x5C1D;&#x8BD5;&#x53CD;&#x7F16;&#x8BD1;&#x7684; HL crossfire.](../../../../../.gitbook/assets/crossfire_winbspc.png)

{% hint style="info" %}
原文章链接： [https://developer.valvesoftware.com/wiki/BSP2MAP](https://developer.valvesoftware.com/wiki/BSP2MAP)
{% endhint %}

