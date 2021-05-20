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

### General settings

There settings are the most important. There are three:

* Normal format
  * The color/compression format that should be used if the texture is opaque.
* Alpha format
  * The color/compression format that should be used if the texture has an alpha channel.
* Texture type

  * If you imported more than one image, this determines what they will be used as \(animation frames/[cubemap ](../cube-mapping.md)faces/depth slices\).

  If you're making a plain and simple world texture you won't need to change any of these. If you're making a texture with fine gradient detail however, you'll need to choose a[ non-lossy compression mode](./#choosing-an-image-format).

### Mipmap settings

[Mipmaps](../mip-mapping.md) are low-resolution versions of a texture that swap in when a surface is far away from the camera. They greatly reduce the amount of texture resizing needed, improving both performance and image quality. Mips are required for texture [LOD ](https://en.wikipedia.org/wiki/Level_of_detail)to work.

{% hint style="info" %}
 **Tip:**Textures that will appear in the 3D world should have [mipmaps](../mip-mapping.md). To conserve memory, textures that will only be used in a 2D interface should not.
{% endhint %}

The following images demonstrate the various [mipmap ](../mip-mapping.md)filters available in [VTFEdit](../../../how-to-start-modding/modding-introduction/modding-tools/#vtf-and-vmt):

![Sharpen filters](../../../.gitbook/assets/vtf_sharpen_filters.jpg)

![Mip filters \#1](../../../.gitbook/assets/vtf_mipmap_filters1.jpg)

![Mip filters \#2](../../../.gitbook/assets/vtf_mipmap_filters2.jpg)

![Mip filters \#3](../../../.gitbook/assets/vtf_mipmap_filters3.jpg)

![Mip filters \#4](../../../.gitbook/assets/vtf_mipmap_filters4.jpg)

### Normal map settings

These \(mis-labelled\) settings allow you to automatically generate a [bump map](https://developer.valvesoftware.com/wiki/Bump_map) from your input image. You'll want to do this properly with an image editor for the material you ship, but the automated option is there is you want quick results or a base to work from.

## Configuring & saving

When you hit OK the input file is converted \(there may be quite a lengthy pause for large images\) and the output VTF appears. Now all that is left is configuring the texture with the options in the checkbox list on the left-hand side of the screen. See [Valve Texture Format image\_flags](./#image-flags) for descriptions of each.

Finally, save the file somewhere under your game or mod's  `\materials` folder.

## Creating a material

Source doesn't access textures directly. Everything goes through a [material](../valve-material-type-vmt.md).

[Materials](../valve-material-type-vmt.md) are script files that can be created in any text editor, but it's recommended that you use one of the [software listed](../../../how-to-start-modding/modding-introduction/modding-tools/#general) in conjunction with the community-made [syntax highlighting rules](https://developer.valvesoftware.com/wiki/Notepad%2B%2B_VDF_languages). For your material to be detected, **you must save it under your game or mod's**  **`\materials` folder with the extension `.vmt`**.

{% hint style="info" %}
 **Note:** If you are creating materials and textures exclusively for a map for a existing mod, consider using  [BSPZIP](https://developer.valvesoftware.com/wiki/BSPZIP)\[Packbsp](https://developer.valvesoftware.com/wiki/Packbsp)\[Pakrat](https://developer.valvesoftware.com/wiki/Pakrat)\[Compile Pal](https://developer.valvesoftware.com/wiki/Compile_Pal) to package the material and texture files within the map file itself. This will avoid them ever becoming lost.
{% endhint %}

### Syntax

A material file looks like this:

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

There are many [shaders](https://developer.valvesoftware.com/wiki/Shader) to choose from, but most materials will use either [`LightmappedGeneric`](https://developer.valvesoftware.com/wiki/LightmappedGeneric) \([brushes](https://developer.valvesoftware.com/wiki/Brush)\) or [`VertexLitGeneric`](https://developer.valvesoftware.com/wiki/VertexLitGeneric) \([models](https://developer.valvesoftware.com/wiki/Model)\). The third most common shader is [`UnlitGeneric`](https://developer.valvesoftware.com/wiki/UnlitGeneric), which is used for [UI](https://developer.valvesoftware.com/wiki/VGUI2) materials and the occasional [tool texture](https://developer.valvesoftware.com/wiki/Tool_texture).

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

