---
description: 本教程将会教你从头开始一步一步地创建一个全新的材质，并创建材质的纹理文件。
---

# 创建材质

本教程将会教你从头开始一步一步地创建一个全新的[材质](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Ma932GRGVfjjlaaoa1C/v/chinese/information/textures/valve-material-type-vmt/@merged)，并创建材质的[纹理文件](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Ma932GRGVfjjlaaoa1C/v/chinese/information/textures/valve-texture-format-vtf/@merged)。

## 创建一个材质

任何图像文件都可以作为纹理，只要它的尺寸\(高度和宽度\)都是2的幂：2，4，8，16，32，64，128，256，512，1024，2048等等。要决定新建纹理的参数设置，请先检查在游戏中正在使用的对应纹理。更高的分辨率的纹理会降低性能，但当你近距离观察时，显示的图像会更清晰。

不同类型的对象拥有不同的标准分辨率（例如：角色模型的标准分辨率就非常高）。如果你不清楚的话请用 [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape) 查看 `source materials.gcf`中v社的标准设置![](https://developer.valvesoftware.com/w/images/c/cc/Note.png) ****

{% hint style="info" %}
**注解：**纹理源文件应该保存为（例如[TGA](../../file-format/truevision-graphics-adapter-tga.md)预编译）这种无损格式以防不必要的纹理质量损失
{% endhint %}

## **转换纹理**

纹理必须转换为[Valve Texture Format \(VTF\)](./)格式才能让起源引擎使用。v设提供了[VTEX](https://developer.valvesoftware.com/wiki/Vtex)作为转换工具。这是一个有很多限制的命令行工具，所以第三方工具VTFEdit是更好的选择： 它提供了一个图形用户界面，允许使用者直接更改纹理的属性而无需从头重新编译它，并兼容各种图像格式，还可以直接每个纹理创建脚本文件。当然，在一些情况下你还是需要使用VTEX的，但只有很少一部分（比如说一些动态纹理和[spritesheet技术](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Ma932GRGVfjjlaaoa1C/v/chinese/information/textures/valve-texture-format-vtf/animated-particles/@drafts)）。

此外，如果您有需要使用透明度的纹理，建议您在导入到VTFEdit之前保存为TIFF格式，因为PNG的透明度往往容易出现一些问题（有一些VTF插件可以让您直接从Photoshop、GIMP和Paint.net保存为vtf格式，但是本教程并不会介绍它们，因为不是每个人能够使用这些工具）。

要在VTFEdit中导入纹理， 请选择 `File > Import` 或者使用Ctrl+I快捷键。然后，选择你需要的图像，导入选项窗口就会弹出：

![](../../../.gitbook/assets/vtfedit_importoptions.png)

### 通用设定

There settings are the most important. There are three:

* 法线格式
  * 如果纹理是不透明的，请使用颜色/压缩（color/compression）格式。
* Alpha格式
  * 如果纹理有alpha通道，应该使用颜色/压缩（color/compression）格式。
* 纹理类型

  * 导入多个图像意味着这些图像将会作为动画/[立方体贴图面](https://app.gitbook.com/@noskill/s/titanfall2/v/chinese/information/textures/cube-mapping/@drafts)/深度切片来使用。

  如果你正在制作一个简单的世界纹理，你不需要改变任何上述参数。 但是，如果你在制作一个有着细微斜面细节的纹理，你需要选择一个[非有损压缩格式](https://noskill.gitbook.io/titanfall2/v/chinese/information/textures/valve-texture-format-vtf#choosing-an-image-format)。

### Mipmap设置

[Mipmaps](../mip-mapping.md)是纹理的低分辨率版本，当纹理表面远离相机时引擎会进行切换以节省资源。它们极大地减少了纹理所需调用的数量，提高了性能和图像质量。纹理 [LOD](https://en.wikipedia.org/wiki/Level_of_detail)需要Mips才能工作。

{% hint style="info" %}
 **提示：**在3D世界出现的纹理需要拥有[mipmaps](../mip-mapping.md)。为了节约内存，在2D世界中使用的纹理尽量不要使用[mipmaps](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Ma9BRdwf8qrjFOuXmGJ/v/chinese/information/textures/mip-mapping/@drafts)。
{% endhint %}

下列图片展示了各种在 [VTFEdit](../../../how-to-start-modding/modding-introduction/modding-tools/#vtf-and-vmt)可以使用的[mipmap](../mip-mapping.md)滤镜：

![&#x9510;&#x5316;&#x6EE4;&#x955C;](../../../.gitbook/assets/vtf_sharpen_filters.jpg)

![Mip&#x6EE4;&#x955C; \#1](../../../.gitbook/assets/vtf_mipmap_filters1.jpg)

![Mip&#x6EE4;&#x955C; \#2](../../../.gitbook/assets/vtf_mipmap_filters2.jpg)

![Mip&#x6EE4;&#x955C; \#3](../../../.gitbook/assets/vtf_mipmap_filters3.jpg)

![Mip&#x6EE4;&#x955C; \#4](../../../.gitbook/assets/vtf_mipmap_filters4.jpg)

### 法线贴图设置

这些（mis-labelled） 设置允许你用你输入的图像自动生成一个[凹凸贴图](https://developer.valvesoftware.com/wiki/Bump_map)。你可能想用图像编辑功能来快速完成设计，但是自动生成选项只能生成一个非常基础的贴图。

## 配置&保存

当您点击OK时，输入的文件将会进行格式转换（越大的图像转换时间越长，需要使用者耐心等待大），转换完成后，对应的VTF将会出现。现在剩下要做的就是使用窗口左侧的复选框列表中的选项配置纹理。请参阅 [Valve Texture Format image\_flags](./#image-flags) 来获取进一步的信息。

Finally, save the file somewhere under your game or mod's  `\materials` folder.

## 创建一个材质（Materials）

起源引擎并不会直接访问纹理。所有的纹理都要通过一个[材质](https://noskill.gitbook.io/titanfall2/v/chinese/information/textures/valve-material-type-vmt)进行配置之后才会被调用。

[材料](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Ma9GJZ1h2Li9XAhpICO/v/chinese/information/textures/valve-material-type-vmt/@drafts)是可以在任何文本编辑器中创建的脚本文件，但建议您结合在[编辑软件](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Ma9GJZ1h2Li9XAhpICO/v/chinese/how-to-start-modding/modding-introduction/modding-tools#general/@drafts)页面中用[高亮语法规则](https://developer.valvesoftware.com/wiki/Notepad%2B%2B_VDF_languages)列出的软件之一进行编辑。为了让你的材质被检测到， **你必须把它以`.vmt`格式保存在你的游戏或mod下的** **`\materials` 文件夹中** .

{% hint style="info" %}
 **注解：**如果你正在为一个现有的mod制作贴图材质或纹理，可以考虑使用[BSPZIP](https://developer.valvesoftware.com/wiki/BSPZIP)\[Packbsp](https://developer.valvesoftware.com/wiki/Packbsp)\[Pakrat](https://developer.valvesoftware.com/wiki/Pakrat)\[Compile Pal](https://developer.valvesoftware.com/wiki/Compile_Pal) 等软件来将材质和纹理文件打包到贴图文件中。
{% endhint %}

### 语法

一个材质文件的语法格式应该看起来像这样：

```text
<shader>
{
	<parameter> <value>
	...
}
```

```text
LightmappedGeneric
{
	$basetexture coast\shingle_01
	$surfaceprop gravel
}
```

有很多的[着色器](https://developer.valvesoftware.com/wiki/Shader)可供选择，但是大多数的材质都会选择[`LightmappedGeneric`](https://developer.valvesoftware.com/wiki/LightmappedGeneric) \([笔刷](https://developer.valvesoftware.com/wiki/Brush)\)，[`VertexLitGeneric`](https://developer.valvesoftware.com/wiki/VertexLitGeneric) \([模型](https://developer.valvesoftware.com/wiki/Model)\)[`UnlitGeneric`](https://developer.valvesoftware.com/wiki/UnlitGeneric)`（`通常用于[UI](https://developer.valvesoftware.com/wiki/VGUI2)材料，偶尔用于[工具材料](https://developer.valvesoftware.com/wiki/Tool_texture)）三者之一，。hich is used for [UI](https://developer.valvesoftware.com/wiki/VGUI2) materials and the occasional [tool texture](https://developer.valvesoftware.com/wiki/Tool_texture).

### Parameters

For a list of all documented shader parameters, see [Category:List of Shader Parameters](https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters).

With a shader chosen you're onto parameters \(also called commands\). There are hundreds of options for what to put in a material so this article will only cover the most common, which are accepted by more or less all shaders. They are:

* [`$basetexture`](../shader/usdbasetexture.md)
* [`$surfaceprop`](https://developer.valvesoftware.com/wiki/$surfaceprop)
* [`$envmap`](https://developer.valvesoftware.com/wiki/$envmap)
* [`$bumpmap`](../bump-map/usdbumpmap.md)
* [`$detail`](https://developer.valvesoftware.com/wiki/$detail)
* [`$selfillum`](https://developer.valvesoftware.com/wiki/$selfillum)
* [`$model`](https://developer.valvesoftware.com/wiki/$model_%28VMT%29)

{% hint style="info" %}
 **Tip:** If you ever need to use a space or tab character in a parameter value, you must wrap the while value with "quote marks". You'll often see absolutely everything wrapped like this - save yourself some typing, as that's unnecessary.
{% endhint %}

{% hint style="info" %}
 **Tip:** To refresh materials in-game - use this console command: `mat_reloadallmaterials`, this will reload every single material. It's recommended to use this command to prevent game from freezing and some other weird artifacts: `mat_reloadmaterial "vmt_name without .vmt"`. Example: `mat_reloadmaterial "monitor_screen"`. Mat\_reloadtextures is presented too.
{% endhint %}

## Source & reference

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Creating\_a\_Material](https://developer.valvesoftware.com/wiki/Creating_a_Material)

Reference: [https://en.wikipedia.org/wiki/Level\_of\_detail](https://en.wikipedia.org/wiki/Level_of_detail)
{% endhint %}











\*\*\*\*

\*\*\*\*

