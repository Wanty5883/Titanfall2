---
description: VTFEdit是包含在VTFLib中函数的GUI前端。
---

# VTFEdit

**VTFEdit**是包含在[VTFLib](https://developer.valvesoftware.com/wiki/VTFLib)（一个LGPL开源编程库）中函数的GUI前端。VTFEdit是VTFTool的继承者，由  [Neil "Jed" Jedrzejewski](https://developer.valvesoftware.com/wiki/User:Wunderboy) 和 [Ryan "Nemesis" Gregg](https://developer.valvesoftware.com/wiki/User:Nem)所编写的。

VTFEdit本身完全由Ryan编写，是一个基于.NET的GUI工具，用于创建和转换 [VTF](https://developer.valvesoftware.com/wiki/VTF) 和 [VMT](https://developer.valvesoftware.com/wiki/VMT) 文件。 它是一个非常强大的工具，可以将各种格式的文件转换为所有起源纹理格式的VTF格式。

VTFEdit使用nVidia的[nvDXTlib](http://developer.nvidia.com/object/dds_utilities.html)库生成 [MIP映射](https://developer.valvesoftware.com/wiki/MIP_Mapping)和DXTn压缩图像，并提供多种格式和过滤器。

其他功能包括从灰度图像创建[法线贴图](https://developer.valvesoftware.com/wiki/Normal_Maps)的能力、用于MIP贴图生成的各种锐化过滤器、访问所有具有VTF文件头标志的文件、 a simple tree based VMT creation system with [GCF](https://developer.valvesoftware.com/wiki/GCF) access，WAD转换工具、批处理转换工具和VMT创建向导。

{% hint style="danger" %}
**Bug:** 如果试图将文本以外的内容粘贴到编辑器中，VTFEdit将会崩溃。
{% endhint %}

## 参见

{% page-ref page="../../../../../information/textures/valve-texture-format-vtf/creating-a-material.md" %}

![](../../../../../.gitbook/assets/vtfedit1.png)

![](../../../../../.gitbook/assets/vtfedit2.png)

{% hint style="info" %}
资源信息: [https://developer.valvesoftware.com/wiki/VTFEdit](https://developer.valvesoftware.com/wiki/VTFEdit)
{% endhint %}

