# Vtex - 编译参数

[Vtex](./) 可以在其执行期间加入附加的编译参数列表。这些参数是可选的，用来最优化编译效果。

编译参数列表是一个简单的与相对应需要编译的 [targa \(.tga\)](../../../../../../information/file-format/truevision-graphics-adapter-tga.md) 图像名称相同的文本文件\(.txt\) ，列表和需要编译的图像需要放在同一文件夹，即 `SteamApps/common/gamefolder/materialsrc/` ，其中`gamefolder`是你游戏的根目录。

控制台后台文件的用法示例：

```text
nonice 1
nolod 1
nomip 1
```

## 参数

### allmips

强制纹理使用所有mipmap\(没有最小的mipmap\)。

### alphatest\_hifreq\_threshhold

### alphatest\_threshhold

### alphatest

以上参数用法暂时不明

### alphatodistance

创建距离阿尔法（alpha-to-distance）纹理。

### anisotropic

强制需要编译的纹理被施加各向异性过滤（Anisotropic filtering）。

### bumpscale

设置纹理的凹凸贴图强度值，控制法线贴图明显度的强弱。

### clamps

### clampt

### clampu

不允许纹理在S、T或U坐标空间中被包裹。这通常用于未平铺的界面。

{% hint style="info" %}
**提示：**当一个texel在纹理之外被需要时，我们会使用一下两种技术中的一种来应对：**压缩\(CLAMPING\)** texel以限制纹理大小，如果纹理大小过大则适应为最近大小的可用texel。**包装（WRAPPING\)** 使texel适应为正常纹理的增量（不同大小进行不同情况的适应）。包装会导致纹理重复，压缩只会存在于一个位置。
{% endhint %}

### distancespread

控制创建距离阿尔法（alpha-to-distance）纹理时阿尔法的分布情况。

### dudv

纹理是一个 Du/Dv 贴图。

### dxt5

 强制 [DXT5](https://developer.valvesoftware.com/wiki/DirectX_Texture_compression_5) 压缩，即使原图没有阿尔法通道。

### maxheight

### maxheight\_360

### maxwidth

### maxwidth\_360

为“最高质量”\(mat\_picmip 0\)的纹理质量设置最大的纹理大小。负值的mat\_picmip设置将会超过此限制。

### mipblend

功能不明

### nocompress

不在这个纹理上使用格式压缩。着对于具有精细渐变的纹理\(如光晕\)非常有用。

### nodebug

调试时不会覆盖。



### nolod

无论纹理质量\(mat\_picmip\)设置如何，都不使用此纹理的低分辨率版本，此设置用于非世界图形，如HUD艺术。

### nomip

使纹理不使用mipmapping。一般用于材质，如天空盒和菜单背景。

{% hint style="warning" %}
 **Bug:** 有时mipmap仍然会加载！请使用 [VTFEdit](../vtfedit.md) 来减少纹理占用。
{% endhint %}

### nonice

不在此纹理较低的mip级上使用NICE过滤。

### normal

此纹理将作为一个法线贴图。意味着不会有nice过滤，所以在生成mipmap时所有法线将保持不变。

{% hint style="info" %}
**注解**：当纹理名称以 `_normal` 结尾时自动执行此命令。
{% endhint %}

### normalalphatodudvluminance

当从法线贴图转换为Du/Dv贴图时，使用alpha通道作为亮度贴图

### normaltodudv

将纹理转换为Du/Dv贴图。

### numchannels

控制从源文件中导入通道的数量。\(1 = Red only, 2 = Red and Green, 3 = RGB, 4 = RGB + Alpha\)没有囊括的颜色通道将被替换为全颜色强度。

### oneovermiplevelinalpha

Alpha通道衰减，且mipmap变得更小。

### pfm

纹理将作为一个可用于HDR的可移植的浮点贴图。

### pfmscale \(float\)

用于控制浮点贴图的强度。

### pointsample

不在游戏中过滤这个纹理。

### premultcolorbyoneovermiplevel

颜色通道随着mipmap变小而衰减。在将法线贴图转换为Du/Dv贴图时使用。

### procedural

程序化纹理。

### reduce

### reducex

### reducey

同时缩小X轴和Y轴。当然，缩减值必须是2的幂，这将告诉VTEX减少维度的量\(2 =一半大小，4 =四分之一大小，8 =八分之一大小，等等\)。

### rendertarget

纹理将作为一个渲染对象。

### singlecopy

暂时不造~

### skybox

用于编译[天空盒](../../../../../../information/textures/skybox-basics/) 。这将保证天空盒的每个面的边缘都匹配。

### spheremap\_negz

### spheremap\_z

### spheremap\_negy

### spheremap\_y

### spheremap\_negx

### spheremap\_x

这个也不造~

### ssbump

用于[自阴影凹凸贴图（self-shadowing bump maps      $ssbump\)](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MameUdNnvaNTbr4dtZX/v/chinese/information/textures/bump-map/usdssbump/@drafts).

{% hint style="info" %}
 **注解：**当纹理名称以 `_height-ssbump` 结尾时自动执行此命令。
{% endhint %}

### startframe \(integer\)

### endframe \(integer\)

用于动画纹理。纹理格式必须命名为texture000, texture001, texture002等。startframe定义了开始帧，endframe定义了结束帧。最多允许包含1000帧。

### stripalphachannel

使Vtex忽略源纹理的alpha通道。

### stripcolorchannel

用于创建没有颜色数据的纹理。

### trilinear

强制对编译后的纹理施加至少三重线性过滤。

### volumetexture

创建一个体积纹理。

### 使用 .psd 'file info' 参数

从[.psd文件](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MameUdNnvaNTbr4dtZX/v/chinese/information/file-format/psd-photoshop-document/@drafts)编译的纹理可以将命令行参数直接保存到[.psd](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MameUdNnvaNTbr4dtZX/v/chinese/information/file-format/psd-photoshop-document/@drafts)文件中。请使用Photoshop中的“文件信息（File Info）”菜单来达成这一点，并将你的Vtex命令添加到“描述（description）”文本区域。当[编译.psd](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MameUdNnvaNTbr4dtZX/v/chinese/information/file-format/psd-photoshop-document/@drafts)文件时，这些参数将由[Vtex](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MameUdNnvaNTbr4dtZX/v/chinese/how-to-start-modding/modding-introduction/modding-tools/source/vtf-and-vmt/vtex/@drafts)自动计算。

以下是一个不会平铺照射的的闪光灯的的创建案例:

```text
clamps 1;
clampt 1;
border 0;
```

{% hint style="info" %}
源文件链接： [https://developer.valvesoftware.com/wiki/Vtex\_compile\_parameters](https://developer.valvesoftware.com/wiki/Vtex_compile_parameters)
{% endhint %}

