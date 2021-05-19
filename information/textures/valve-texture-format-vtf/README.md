# Valve纹理格式-VTF

**Valve Texture Format \(VTF\)** 是起源引擎专用的纹理格式。 VTF 文件通常作为一个独立的材料被引用，而不是直接调用，这样可以允许它以多种方式重复利用。

VTF文件可以用Source SDK Tool VTEX由TGA图像或者其他有第三方软件辅助的常见图像格式创建。纹理和材质都储存在子文件夹 `game_dir/materials/`.

## 存储内容

 VTF格式的图像可以存储平面纹理（flat texture），环境映射（environment map）或者体积纹理（volumetric texture）。每一种都可以以拥有多个坐标系。 

* 环境映射是一个六面立方体映射。
* 体积纹理是一种有深度的纹理，其中的每一帧都是在三维中分层的一个“层”。 所以一个16\*16\*16的体积纹理由16层独立的16\*16的纹理堆叠而成，这样可以赋予纹理深度。这种格式在Source Engine内部被使用，并不需要你自己去创建一个。
* 对于每一帧和每一面，VTF文件既包含基本的原始源图像数据 \(像素图\)，也包含一系列用于在不同距离上渲染纹理的**mipmap（ 一种电脑图形图像技术，用于在三维图像的二维代替物中达到立体感效应）** 。因为每一个连续的mipmap恰好是前一个mipmap尺寸（高度和宽度）的1/2，源图像尺寸就必须是4的倍数。尽管源图像可能是矩形的，但是方形的mipmap在VTF中的储存效率更高。
* 开始帧（start frame）：用于动画
* **凹凸贴图（bump map）**的规模
* **VRAD（一个命令行工具，让静态和预编译的光照通过**[**光线传递**](http://en.wikipedia.org/wiki/Radiosity_%283D_computer_graphics%29)**算法在世界范围内反弹）**使用的反射率值。
* 一个用于引擎颜色采样，分辨率非常低的VTF副本。

### 资源

VTF 7.3 增加了一个可扩展的 “资源数据（resource data）“系统。 任何内容都可以被添加，但是引擎只会识别以下内容：

* 用于检测数据是否损坏的CRC（Cyclic Redundancy Check 循环冗余校验）值。
* **U/V** LOD（Level Of Details 多层次细节） 控制。当游戏纹理细节被设置为“高”\(`mat_picmip 0`\)时，加载细节度最高的mipmap。一个值为11的U LOD 控制值选择的对应mipmap像素为2048（2^11）

{% hint style="info" %}
因为目前用户选项中只有一个选项是高于”高“的纹理细节设置，所以除了%50或%100的纹理大小之外，这个调试的意义不大。
{% endhint %}

* \*\*\*\*[**动画粒子表（Animated particle sheet）**](https://noskill.gitbook.io/titanfall2/documentation/textures/valve-texture-format-vtf/animated-particles)数据。
* 扩展纹理设置。这是一个包含32个旗标（flag）的集合 。其中没有一个被Valve用到。与内置的VTF旗标不同，我们可以根据游戏自身来定义这些内容。

## 图像数据格式

VTF格式可以存储多种格式的图像数据。有些格式是为引擎所准备的，有些只是作为转换的过渡格式。未压缩的（uncompressed）格式是无损的，而压缩的（compressed）格式是有损的\(比如说DXT\)

![](https://developer.valvesoftware.com/w/images/c/cc/Note.png)**注解:**VTF格式实际上可以存储的格式包括但不限于下面列出的格式 -- 具体请查询你的引擎分支资料`public/bitmap/imageformat.h` 来获知哪些格式是被支持的。然而，这些格式不能保证一定能在引擎中正确工作，它们的枚举值很容易在引擎分支间被打乱。

### 图像数据格式表

| Format  | Red Bits | Green Bits | Blue Bits | Alpha Bits | Total Bits | Compresses | Supported | Comments |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| A8 | 0 | 0 | 0 | 8 | 8 | False | True |  |
| ABGR8888 | 8 | 8 | 8 | 8 | 32 | False | True | Uncompressed texture with alpha |
| ARGB8888 | 8 | 8 | 8 | 8 | 32 | False | True |  |
| BGR565 | 5 | 6 | 5 | 0 | 16 | False | True | Uncompressed texture, limited color depth |
| BGR888 | 8 | 8 | 8 | 0 | 24 | False | True | Uncompressed texture |
| BGR888\_BLUESCREEN | 8 | 8 | 8 | 0 | 24 | False | True |  |
| BGRA4444 | 4 | 4 | 4 | 4 | 16 | False | True | Uncompressed texture with alpha, half color depth |
| BGRA5551 | 5 | 5 | 5 | 1 | 16 | False | True |  |
| BGRA8888 | 8 | 8 | 8 | 8 | 32 | _Either_ | True | Also used for compressed HDR |
| BGRX5551 | 5 | 5 | 5 | 1 | 16 | False | True |  |
| BGRX8888 | 8 | 8 | 8 | 8 | 32 | False | True |  |
| DXT1 | N/A | N/A | N/A | 0 | 4 | True | True | Standard compression, no alpha |
| DXT1\_ONEBITALPHA | N/A | N/A | N/A | 1 | 4 | True | True | Standard compression, one bit alpha |
| DXT3 | N/A | N/A | N/A | 4 | 8 | True | True | Uninterpolated Alpha |
| DXT5 | N/A | N/A | N/A | 8 | 8 | True | True | Interpolated Alpha \(recommended\) |
| I8 | N/A | N/A | N/A | N/A | 8 | False | True | Luminance \(Grayscale\) |
| IA88 | N/A | N/A | N/A | 8 | 16 | False | True | Luminance \(Grayscale\) |
| P8 | N/A | N/A | N/A | N/A | 8 | False | False | Paletted |
| RGB565 | 5 | 6 | 5 | 0 | 16 | False | True |  |
| RGB888 | 8 | 8 | 8 | 0 | 24 | False | True |  |
| RGB888\_BLUESCREEN | 8 | 8 | 8 | 0 | 24 | False | True |  |
| RGBA16161616 | 16 | 16 | 16 | 16 | 64 | False | True | Integer HDR Format |
| RGBA16161616F | 16 | 16 | 16 | 16 | 64 | False | True | Floating Point HDR Format |
| RGBA8888 | 8 | 8 | 8 | 8 | 32 | False | True |  |
| UV88 | N/A | N/A | N/A | N/A | 16 | False | True | Uncompressed du/dv Format |
| UVLX8888 | N/A | N/A | N/A | N/A | 32 | False | True |  |
| UVWQ8888 | N/A | N/A | N/A | N/A | 32 | False | True |  |

**HDR（High Dynamic Range Imaging 高动态范围图像） 压缩**

HDR纹理可以用BGRA8888格式以压缩形式储存。

将压缩颜色转换回HDR整数值的公式是：

`RGB = RGB * (A * 16)`

对于浮点HDR公式则是：

`RGB = (RGB * (A * 16)) / 262144`

### 选择一个图像格式

尽管VTF提供了对多种图像数据格式的支持，但您一般使用的图像数据格式只有下列少数几种：

* **BGR888:** 这种格式的纹理没有alpha通道，有着非常细微的梯度（即法线贴图（normal maps）或者光晕）。
* **BGRA8888:** 这种格式的纹理有alpha通道和非常细微的梯度（即法线贴图（normal maps）或者光晕）。它也可以用来生产非常高质量的纹理。
* **DXT1:** 一种非常典型的纹理格式，没有alpha通道 \(也被称为BC1\)。
  * **注解：** DXT1支持1位alpha精度。然而，任何alpha值为0的区域将是全黑的。因此，这个功能最好在使用[$alphatest](https://developer.valvesoftware.com/wiki/$alphatest)语句时使用。
* **DXT3:** **DXT5一般都作为DXT3的上位选择，**但是DXT3也是可以接受的\(不一定更好\) ，这是一种带alpha通道和尖锐梯度的纹理 \(也被称为BC2\)。
* **DXT5:** 一种带有alpha通道的经典纹理格式 \(也被称为BC3\)。
* **I8:** 没有alpha通道，梯度非常细微的黑白纹理格式\(即光晕\).
* **IA88:** 有alpha通道，梯度非常细微的黑白纹理格式\(即光晕或者烟雾\)
* **RGBA16161616F: HDR**纹理格式.
* **UV88:** [**Du/Dv 映射（Du/dv\_map）**](https://developer.valvesoftware.com/wiki/Du/dv_map)的纹理格式.

在很多地方你都能找到各种关于DXT压缩格式的技术细节。

## 图像旗标

**提示:**大多数着色器都被默认配置为材质参数，而不是纹理旗标。

一个VTF文件可以包含以下旗标 \(version 7.5\):

| Flag |  **Value** |  **Comment** |
| :--- | :--- | :--- |
| Point Sampling | 0x0001 | Low quality, "pixel art" texture filtering. |
| Trilinear Sampling | 0x0002 | Medium quality texture filtering. |
| Clamp S | 0x0004 | Clamp S coordinates. |
| Clamp T | 0x0008 | Clamp T coordinates. |
| Anisotropic Sampling | 0x0010 | High quality texture filtering. |
| Hint DXT5 | 0x0020 | Used in [skyboxes](../skybox-basics/). Makes sure edges are seamless. |
| PWL Corrected | 0x0040 | Purpose unknown. |
| SRGB | n/a | Uses space RGB. Useful for High Gamuts. Deprecated in 7.5. |
| No Compress | 0x0040 | No DXT compression used. Deprecated |
| Normal Map | 0x0080 | Texture is a normal map. |
| No Mipmaps | 0x0100 | Render largest mipmap only. \(Does not delete existing mipmaps, just disables them.\) |
| No Level Of Detail | 0x0200 | Not affected by texture resolution settings. |
| No Minimum Mipmap | 0x0400 | If set, load mipmaps below 32x32 pixels. |
| Procedural | 0x0800 | Texture is an procedural texture \(code can modify it\). |
| One Bit Alpha | 0x1000 | One bit alpha channel used. |
| Eight Bit Alpha | 0x2000 | Eight bit alpha channel used. |
| Environment Map | 0x4000 | Texture is an environment map. |
| Render Target | 0x8000 | Texture is a render target. |
| Depth Render Target | 0x10000 | Texture is a depth render target. |
| No Debug Override | 0x20000 |  |
| Single Copy | 0x40000 |  |
| Pre SRGB | 0x80000 | SRGB correction has already been applied |
| One Over Mipmap Level In Alpha | 0x80000 | Fill the alpha channel with 1/Mipmap Level. Deprecated \(Internal to VTEX?\) |
| Premultiply Color By One Over Mipmap Level | 0x100000 | \(Internal to VTEX?\) |
| Normal To DuDv | 0x200000 | Texture is a DuDv map. \(Internal to VTEX?\) |
| Alpha Test Mipmap Generation | 0x400000 | \(Internal to VTEX?\) |
| No Depth Buffer | 0x800000 |  Do not **buffer** for Video Processing, generally render distance. |
| Nice Filtered | 0x1000000 |  Use **NICE filtering** to generate mipmaps. \(Internal to VTEX?\) |
| Clamp U | 0x2000000 | Clamp U coordinates \(for volumetric textures\). |
| Vertex Texture | 0x4000000 | Usable as a vertex texture |
| SSBump | 0x8000000 |  Texture is a **SSBump**. \(SSB\) |
| Border | 0x20000000 | Clamp to border colour on all texture coordinates |

## 文件格式

VTF图像格式介绍如下：

### VTF 布局设计

{% tabs %}
{% tab title="Version 7.2" %}
1. VTF 数据头（Header）
2. VTF 低分辨率图像数据（Low Resolution Image Data）
3. 对应的Mipmap \(从最小到最大\)
   * 对应的帧 \(从首个到最后一个\)
     * 对应的 \(从首个到最后一个\)
       * 对应的 Z 切片\(Z Slice；最小到最大;；随着Mipmap变化\)
         * VTF 高分辨率图像数据（High Resolution Image Data）
{% endtab %}

{% tab title="Version 7.3 +" %}
1. VTF Header
2. Resource entries
   * VTF Low Resolution Image Data
   * Other [resource data](./#resources)
   * For Each Mipmap \(Smallest to Largest\)
     * For Each Frame \(First to Last\)
       * For Each Face \(First to Last\)
         * For Each Z Slice \(Min to Max; Varies with Mipmap\)
           * VTF High Resolution Image Data
{% endtab %}
{% endtabs %}

### VTF 列举（enumerations）

```text
enum
{
	IMAGE_FORMAT_NONE = -1,
	IMAGE_FORMAT_RGBA8888 = 0,
	IMAGE_FORMAT_ABGR8888,
	IMAGE_FORMAT_RGB888,
	IMAGE_FORMAT_BGR888,
	IMAGE_FORMAT_RGB565,
	IMAGE_FORMAT_I8,
	IMAGE_FORMAT_IA88,
	IMAGE_FORMAT_P8,
	IMAGE_FORMAT_A8,
	IMAGE_FORMAT_RGB888_BLUESCREEN,
	IMAGE_FORMAT_BGR888_BLUESCREEN,
	IMAGE_FORMAT_ARGB8888,
	IMAGE_FORMAT_BGRA8888,
	IMAGE_FORMAT_DXT1,
	IMAGE_FORMAT_DXT3,
	IMAGE_FORMAT_DXT5,
	IMAGE_FORMAT_BGRX8888,
	IMAGE_FORMAT_BGR565,
	IMAGE_FORMAT_BGRX5551,
	IMAGE_FORMAT_BGRA4444,
	IMAGE_FORMAT_DXT1_ONEBITALPHA,
	IMAGE_FORMAT_BGRA5551,
	IMAGE_FORMAT_UV88,
	IMAGE_FORMAT_UVWQ8888,
	IMAGE_FORMAT_RGBA16161616F,
	IMAGE_FORMAT_RGBA16161616,
	IMAGE_FORMAT_UVLX8888
};
```

```text
enum CompiledVtfFlags
{
	// Flags from the *.txt config file
	TEXTUREFLAGS_POINTSAMPLE = 0x00000001,
	TEXTUREFLAGS_TRILINEAR = 0x00000002,
	TEXTUREFLAGS_CLAMPS = 0x00000004,
	TEXTUREFLAGS_CLAMPT = 0x00000008,
	TEXTUREFLAGS_ANISOTROPIC = 0x00000010,
	TEXTUREFLAGS_HINT_DXT5 = 0x00000020,
	TEXTUREFLAGS_PWL_CORRECTED = 0x00000040,
	TEXTUREFLAGS_NORMAL = 0x00000080,
	TEXTUREFLAGS_NOMIP = 0x00000100,
	TEXTUREFLAGS_NOLOD = 0x00000200,
	TEXTUREFLAGS_ALL_MIPS = 0x00000400,
	TEXTUREFLAGS_PROCEDURAL = 0x00000800,

	// These are automatically generated by vtex from the texture data.
	TEXTUREFLAGS_ONEBITALPHA = 0x00001000,
	TEXTUREFLAGS_EIGHTBITALPHA = 0x00002000,

	// Newer flags from the *.txt config file
	TEXTUREFLAGS_ENVMAP = 0x00004000,
	TEXTUREFLAGS_RENDERTARGET = 0x00008000,
	TEXTUREFLAGS_DEPTHRENDERTARGET = 0x00010000,
	TEXTUREFLAGS_NODEBUGOVERRIDE = 0x00020000,
	TEXTUREFLAGS_SINGLECOPY	= 0x00040000,
	TEXTUREFLAGS_PRE_SRGB = 0x00080000,
        
        TEXTUREFLAGS_UNUSED_00100000 = 0x00100000,
	TEXTUREFLAGS_UNUSED_00200000 = 0x00200000,
	TEXTUREFLAGS_UNUSED_00400000 = 0x00400000,

	TEXTUREFLAGS_NODEPTHBUFFER = 0x00800000,

	TEXTUREFLAGS_UNUSED_01000000 = 0x01000000,

	TEXTUREFLAGS_CLAMPU = 0x02000000,
	TEXTUREFLAGS_VERTEXTEXTURE = 0x04000000,
	TEXTUREFLAGS_SSBUMP = 0x08000000,			

	TEXTUREFLAGS_UNUSED_10000000 = 0x10000000,

	TEXTUREFLAGS_BORDER = 0x20000000,

	TEXTUREFLAGS_UNUSED_40000000 = 0x40000000,
	TEXTUREFLAGS_UNUSED_80000000 = 0x80000000,
};
```

### VTF 数据头（header）

```text
typedef struct tagVTFHEADER
{
	char		signature[4];		// File signature ("VTF\0"). (or as little-endian integer, 0x00465456)
	unsigned int	version[2];		// version[0].version[1] (currently 7.2).
	unsigned int	headerSize;		// Size of the header struct  (16 byte aligned; currently 80 bytes) + size of the resources dictionary (7.3+).
	unsigned short	width;			// Width of the largest mipmap in pixels. Must be a power of 2.
	unsigned short	height;			// Height of the largest mipmap in pixels. Must be a power of 2.
	unsigned int	flags;			// VTF flags.
	unsigned short	frames;			// Number of frames, if animated (1 for no animation).
	unsigned short	firstFrame;		// First frame in animation (0 based).
	unsigned char	padding0[4];		// reflectivity padding (16 byte alignment).
	float		reflectivity[3];	// reflectivity vector.
	unsigned char	padding1[4];		// reflectivity padding (8 byte packing).
	float		bumpmapScale;		// Bumpmap scale.
	unsigned int	highResImageFormat;	// High resolution image format.
	unsigned char	mipmapCount;		// Number of mipmaps.
	unsigned int	lowResImageFormat;	// Low resolution image format (always DXT1).
	unsigned char	lowResImageWidth;	// Low resolution image width.
	unsigned char	lowResImageHeight;	// Low resolution image height.

	// 7.2+
	unsigned short	depth;			// Depth of the largest mipmap in pixels.
						// Must be a power of 2. Is 1 for a 2D texture.

	// 7.3+
	unsigned char	padding2[3];		// depth padding (4 byte alignment).
	unsigned int	numResources;		// Number of resources this vtf has. The max appears to be 32.
} VTFHEADER;
```

### VTF 资源条目（Resource Entry）

```text
struct ResourceEntryInfo {
	unsigned char	tag[3]; 		// A three-byte "tag" that identifies what this resource is.
	unsigned char	flags;			// Resource entry flags. The only known flag is 0x2, which indicates that no data chunk corresponds to this resource.
	unsigned int	offset;			// The offset of this resource's data in the file. 
};
```

#### 标签（Tags）

```text
{ '\x01', '\0', '\0' } - Low-res (thumbnail) image data.
{ '\x30', '\0', '\0' } - High-res image data.
{ '\x10', '\0', '\0' } - Animated particle sheet data.
{ 'C', 'R', 'C' } - CRC data.
{ 'L', 'O', 'D' } - Texture LOD control information.
{ 'T', 'S', 'O' } - Game-defined "extended" VTF flags.
{ 'K', 'V', 'D' } - Arbitrary KeyValues data.
```

### VTF 低分辨率图像数据

低分辨率图像被在文件的头数据中所描述的格式紧密包装。 低分辨率图像数据通常以DXT1压缩图像格式存储。其尺寸最大即是宽度和高度不超过16像素的mipmap尺寸。比如说对于一个 256x256 像素的 VTF是16x16,；对于一个256x64 像素的VTF是 16x4；1x32 像素的VTF是: 1x16,； 4x4 像素的VTF是 4x4，以此类推。

### VTF 高分辨率图像数据

高分辨率图像被在文件的头数据中所描述的格式紧密包装。 通用的数据格式包含 DXT1, DXT5, BGR888, BGRA8888 和UV88。所有维度都必须是4的倍数。

### 历史版本

**目的:解决游戏特定的兼容性问题**

#### **v7.5**

* 发布于July 19th, 2010 ，作为 **Alien Swarm 异星虫群** 的一部分
* 同于 v7.4.
* 重定义并修改了两个纹理旗标
* 球形地图正式归为冗余信息
* VTF内部创建过程的大部分更改都是使用VTEX， 比如说： Mipmap衰减（[MipMap ](../mip-mapping.md)fading）, alpha衰减（Alpha decay） 和  XBox360 格式.

#### **v7.4**

* 发布于October 10th, 2007 作为[半条命2橙盒版](https://en.wikipedia.org/wiki/The_Orange_Box)的一部分。
* 同于 v7.3.
* 解决有关伽马校正在XBOX360电视输出纹理执行结合系统内存分页池的问题。

#### **v7.3**

* 添加了一个可扩展的面向资源的结构。
* 增加了CRC，纹理的LOD控制，列表资源以及向后兼容的图像和低分辨率图像资源。
* 添加了几种定制化的深度模板格式\(供内部引擎使用\)，以及法线贴图格式和线性未压缩格式。
* 发布于September 18th, 2007 作为 [军团要塞](https://developer.valvesoftware.com/wiki/Team_Fortress_2)2 beta测试的一部分.

#### **v7.2**

* 增加了体积纹理支持。
* 发布于September 23rd, 2005 作为[Steam](https://developer.valvesoftware.com/wiki/Steam)引擎升级的一部分。

#### **v7.1**

* 为环境映射增加了球形地图支持\(这是为了支持DirectX 6，后来被砍掉了\)。

#### **v7.0**

* 最初发布的版本 \(只在内部发布，然而，一些v7.0纹理被公开发表了\)。

#### 执行（Implementation）

一个独立于Steam实现的VTF图像文件格式的例子可以在LGPL C/ c++库的[VTFLib](https://developer.valvesoftware.com/wiki/VTFLib)中找到。

{% hint style="info" %}
Source开发者文档链接: [https://developer.valvesoftware.com/wiki/Valve\_Texture\_Format](https://developer.valvesoftware.com/wiki/Valve_Texture_Format)
{% endhint %}

