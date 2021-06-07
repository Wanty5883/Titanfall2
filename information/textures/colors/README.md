# 纹理和颜色

## RGB

**RGB** 是红，绿，蓝三种颜色的缩写形式。在 [TGA](../../file-format/truevision-graphics-adapter-tga.md) 或 [VTF](../valve-texture-format-vtf/) 中，图像的每个像素由三个可以定义每像素红/绿/蓝叠加含量的[字节](https://developer.valvesoftware.com/wiki/Byte)所定义, 不同的含量可以叠加出不同的颜色。纹理也可以有第四个名为 [alpha](https://developer.valvesoftware.com/wiki/Alpha) 的通道，一般用来为每像素存储其不透明度。

* 每种颜色的三/四个单独的数据值一般被称为“通道 channels”。起源引擎中的[着色器](https://developer.valvesoftware.com/wiki/Shader)可以单独操作每个通道以产生不同的颜色效果。 
* 在[材质](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Mb557rsibt7WkRMyAMQ/v/chinese/information/textures/valve-material-type-vmt/@drafts)中，RGB颜色是一个[材质矢量](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Mb557rsibt7WkRMyAMQ/v/chinese/information/textures/material-vector/@drafts)。

### RGB 矢量

在RGB颜色系统中，你可以根据不同的红、绿、蓝配比来指定某一种颜色，其的值与计算机屏幕上的红、绿、蓝灯珠的发光强度所对应。在RGB方案中，白色表示为`红、绿、蓝（1，1，1）`，而黑色为`红、绿、蓝（0，0，0）`，而某个最亮的颜色值将为表示为三色通道中的某一通道值为1，其余都为0，意味着没有其他颜色。一些颜色参数案例如下所示：

```text
vec(1,0,0)         // red
vec(1,1,0)         // yellow
vec(0,1,0)         // green
vec(1,0.5,0)       // orange
vec(0,0,1)         // blue
vec(0,1,1)         // cyan
vec(1,0,1)         // magenta
vec(0.4,0.2,0.6)   // purple
vec(0,0,0)         // black
vec(1,1,1)         // white
```

在不同的电脑以及不同的3D光照条件下，颜色的表现效果可能不尽相同。以上的颜色在不同情境下的显示差异应该是最小的，因为RGB值为0/1时不会受色彩校正（gamma correction 伽马校正）所影响。

在泰坦陨落2中玩家可以使用超过1的值，在游戏中会表现为过度曝光。（可能是HDR ?）

## 来源和参考

{% hint style="info" %}
源文档链接：

* [https://www.glowscript.org/docs/GlowScriptDocs/color.html](https://www.glowscript.org/docs/GlowScriptDocs/color.html)
* [https://developer.valvesoftware.com/wiki/RGB](https://developer.valvesoftware.com/wiki/RGB)

参考文献： [https://thebookofshaders.com/06/?lan=us](https://thebookofshaders.com/06/?lan=us)
{% endhint %}

