# Valve材质类型-VMT

**材质**是一个用来定义二位表面属性的`.vmt` \("Valve Material Type"\)文本文件。其包含起源引擎在视觉上，听觉上和物理层面上模拟表面所需的所有信息。 

材质的内容可以分为以下几类：

1. [材质名称](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Mb557rsibt7WkRMyAMQ/v/chinese/information/textures/@drafts)
2. [物理表面种类](https://developer.valvesoftware.com/wiki/$surfaceprop)
3. [着色器参数](https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters)
4. [着色器版本回溯](https://developer.valvesoftware.com/wiki/Material_optimization)
5. [材质代理](https://developer.valvesoftware.com/wiki/Material_Proxy)

## 一个简单的例子

```text
LightmappedGeneric
{
	$basetexture coast\shingle_01
	$surfaceprop gravel
}
```

这是一种非常基本的[卵石沙滩](http://en.wikipedia.org/wiki/Shingle_beach)材质：

1. [`LightmappedGeneric`](https://developer.valvesoftware.com/wiki/LightmappedGeneric) 是使用的着色器名称，意味着此材质用于有[光线贴图](https://developer.valvesoftware.com/wiki/Lightmap)的表面 （[笔刷](https://developer.valvesoftware.com/wiki/Brush)）。
2. **{** 字符用于启用一组参数。
3.  [`$basetexture`](https://developer.valvesoftware.com/wiki/$basetexture)由`coast\shingle_01`对应路径的贴图给予。 这是将要绘制在表面上的基础贴图。
4. [`$surfaceprop`](https://developer.valvesoftware.com/wiki/$surfaceprop)提供了表面的物理属性。
5. **}** 字符用于结束一组参数。
6. 注意：不同着色器的参数，用法及效果都不同，请根据使用情景进行选用

注意，这种材质只能用于笔刷。如果你想要在[模型](https://developer.valvesoftware.com/wiki/Model)上使用它，则需要使用另一种名为 [`VertexLitGeneric`](https://developer.valvesoftware.com/wiki/VertexLitGeneric) 的着色器。

大多数的情况下，你只需要更改vmt第一行的着色器名称来改变着色器，因为它们之间的大部分参数都是共享的。当然，也有用于特定着色器的参数，比如说[Phong](https://developer.valvesoftware.com/wiki/Phong)效果只能用于`VertexLitGeneric`。需要注意的是，如果参数不能被着色器所理解，在没有冲突的情况下，不会有任何报错，只是不会有任何的效果。

![](https://developer.valvesoftware.com/w/images/4/45/Tip.png) **提示：**如果在参数值中出现了空格或者制表符，你需要将整个参数值用双引号括起来，否则会出现错误。一般来说数值都会像这样被包装，以提高可读性。

## 寻找材质

### SteamPipe

当V设将一些游戏上传到 [SteamPipe](https://developer.valvesoftware.com/wiki/SteamPipe) 时，材质将会从 [GCF](https://developer.valvesoftware.com/wiki/GCF) 中转移到 [VPK](https://developer.valvesoftware.com/wiki/VPK) 文件中。VPK 文件将会与[GCFScape](https://developer.valvesoftware.com/wiki/GCFScape)一同工作。

请[在此](https://support.steampowered.com/kb_article.php?ref=7388-QPFN-2491)参阅更多关于SteamPipe的信息。

### 非SteamPipe游戏

在非 [SteamPipe](https://developer.valvesoftware.com/wiki/SteamPipe) 的起源游戏中， 材质将会存储在你游戏或者mod的 `materials\` 文件夹中。请使用[Hammer](https://developer.valvesoftware.com/wiki/Hammer)（最佳）或者其他第三方编辑器来查看它们。

如果你想编辑或者查看V社材料文件中的源码，你需要使用 [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape) 将他们从 [GCF](https://developer.valvesoftware.com/wiki/GCF) 包中提取出来。如果它们被存储在 GCF 中，名称中一般会伴随着“材料 material”字符。

{% hint style="info" %}
源文档链接： [https://developer.valvesoftware.com/wiki/Material](https://developer.valvesoftware.com/wiki/Material)
{% endhint %}

