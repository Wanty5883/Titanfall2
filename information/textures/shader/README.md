---
description: 着色器是由显卡运行的用来对物体进行绘制和渲染的软件。起源引擎3D世界中的一切物体都需要使用着色器。
---

# 着色器

着色器是由显卡运行的用来对物体进行绘制和渲染的软件。起源引擎3D世界中的一切物体都需要使用着色器。

着色器使用存储在[材质文件](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Mb557rsibt7WkRMyAMQ/v/chinese/information/textures/valve-material-type-vmt/@drafts)中的参数进行操作。一般的处理都是非常简单的，但也不排除一些非常复杂的用来处理实时阴影，光照和折射的处理方式。

## 类型

着色器有两种主要类型，像素着色器和顶点着色器，它们分别在渲染任务中承担不同的职责。着色器代替了固定的函数通道并且允许开发者通过动态地修改像素和顶点来更好地控制渲染输出效果。SDK工具包包含了很多[现有的着色器](https://developer.valvesoftware.com/wiki/Category:Shaders)。

## 着色器语言 Shader Language

目前有三种主要的着色器语言，[High Level Shader Language \(HLSL\)](https://developer.valvesoftware.com/wiki/HLSL)， [C for Graphics \(Cg\)](https://developer.valvesoftware.com/wiki/CG) 和 [OpenGL Shading Language \(GLSL\)](http://en.wikipedia.org/wiki/GLSL)。起源引擎使用的是基于 [HLSL](https://developer.valvesoftware.com/wiki/HLSL) 的着色器。至于大多数的 Cg 着色器参数也可以很容易地移植到 HLSL 上来。

## 着色器模型 Shader Mode

着色器模型定义了显卡如何执行高级着色技术。旧的显卡不能够在物理模型上识别新的阴影技术。目前有五个版本的着色器模型：SM1.1，SM1.4，SM2.0，SM3.0和SM4.0.

起源引擎默认使用的着色器模型是 Shader Model 2.0 ，这是最常见的一种模型。但是如果你希望着色器兼容更新或者更老的显卡，你必须指定其使用的着色器模型版本，如果未指定，显卡大概率使用不了该着色器。 

当为较新的显卡创建着色器时，别忘了支持比较旧的显卡，否则你的游戏应用规模将会被限制，很多老显卡的玩家将不能够进行游玩。着色器需要向后兼容对特定旧显卡进行着色器指定，这样老的显卡将会使用某一个先前版本的着色器模型，而不是会导致错误的新着色器模型。

如果你想了解更多关于不同着色器的详情规格参数，请阅读以下[WIKI百科的文章](http://en.wikipedia.org/wiki/High_Level_Shader_Language)。

 有关更多起源引擎中创建着色器的信息，请参阅[着色器编辑](https://developer.valvesoftware.com/wiki/Shader_Authoring)页面

### 顶点着色器 Vertex shader

顶点着色器适用于可编程通道中的每一个顶点。其基本作用是将几何图形转换为屏幕空间坐标，以便像素着色器栅格化图像。在更复杂的模型上，顶点着色器负责控制网络形变，光照和一般的顶点位移。注意，顶点着色器不能够创建顶点，只能够对顶点进行编辑。

下面是一个在起源引擎中使用了大量带注释的顶点着色器的案例：

### 顶点着色器样例

这是一个穿透着色器（pass through shader）- 目前来说，它没有对顶点数据进行重大修改，只是在像素着色器阶段进行了数据传递。

```text
// common vertex shader defines provided with this header
#include "common_vs_fxc.h"

// define an output structure
struct VS_OUTPUT
{
  // position vector (float4)
  float4 pos       : POSITION0;
  // texture coordinates (uv - float2)
  float2 texCoord  : TEXCOORD0;
};

// main function - note C style definition
// takes a position vector (float4)
// returns a VS_OUTPUT struct
VS_OUTPUT main( float4 inPos: POSITION )
{
  // declare an empty VS_OUTPUT to fill
  VS_OUTPUT o = (VS_OUTPUT) 0;

  // compute the sign of the input position
  inPos.xy = sign( inPos.xy);
  // set the output position using the xy of the input
  o.pos = float4( inPos.xy, 0.0f, 1.0f);

  // get into range [0,1]
  o.texCoord = (float2(o.pos.x, -o.pos.y) + 1.0f)/2.0f;
  return o;
}
```

## 像素着色器

像素着色器应用于屏幕上呈现的每一个像素。像素着色器期望顶点着色器插值输入，然后用其栅格化图像。

下面是一个在起源引擎中使用了大量带注释的像素着色器的案例：

### 像素着色器样例

下面的像素着色器是一个用于创建灰度效果的后处理着色器（post-process shader）。

```text
// specify a texture sampler, the actual source of this is specified in a vmt
sampler2D Texture0 : register( s0 );

// same function declaration style as vertex shaders
// pixel shaders return the colour value of the pixel (hence the float4)
float4 main( float2 texCoord  : TEXCOORD0 ) : COLOR
{
  // sample the texture at the specified texture coordinates
  float4 tex = tex2D( Texture0, texCoord );
     
  // greyscale the pixel colour values
  // - perform a dot product between the pixel colour and the specified vector
  // - 0.222, 0.707, 0.071 is found throughout image processing for gray scale effects.
  float4 grey = dot(float3(0.222, 0.707, 0.071), tex);
  
  // return the pixel colour in the form of a float4.          
  return grey;
}
```

## 着色器在起源引擎中的应用

起源引擎提供了两种不同形式的着色器，Posprocess和Per-Object，在起源引擎中使用的大多数效果和材质很大程度上依赖于其着色器组件。

### 后处理着色器

后处理（Postprocess）着色器是一个典型的像素着色器，它可以在整个屏幕上进行四边形渲染。这个四边形渲染使用了帧副本缓冲来加载纹理，这样像素着色器可以改变和修改帧来输出各种效果，经典进阶应用有运动模糊和爆炸等。

{% hint style="info" %}
**注解：**以上部分已经过时，这些文件也不再包含在SDK中。`sdk_bloom.cpp` 和 `sdk_bloom.ps20.fxc` 定义了一个可供使用的着色器作为替代品。
{% endhint %}

起源 SDK 在后处理文件中提供了几个后处理着色器的例子 （`sdk_postprocess.cpp`，`sdk_postprocess_vs20.fxc`，和`sdk_postprocess_ps20.fxc`）

高级的后处理着色器，比如说起源引擎中的运动模糊和爆炸着色器，可能需要自定义[渲染目标](https://developer.valvesoftware.com/w/index.php?title=Render_Targets&action=edit&redlink=1)。更多关于后处理着色器的信息请参阅文档[自定义后处理效果](https://developer.valvesoftware.com/wiki/Custom_Postprocessing_Effects)。

### 逐对象着色器

逐对象（Per-Object）着色器可以作用于起源引擎中的任何对象，比如说一个模型或者一幅画。其通过相关的Valve Material \(.vmt\)文件进行引用。每个逐对象着色器都可以用来创建折射材料，动态修改模型顶点或者实现其他高级的渲染效果。 

起源 SDK 在 lightmap 文件中提供了几个逐对象着色器的例子\( `sdk_lightmap.cpp`， `sdk_lightmap_vs20.fxc`，和 `sdk_lightmap_ps20.fxc`\)。

## 着色器参数列表

这里列出了在 "Generic" 着色器中可用的参数列表，其他着色器可用参数请参照对应文档：

* 特殊着色器的参数在着色器的说明文档中会有介绍；
* 用于配置单个效果的参数一般会被分组到特定着色器的说明文章之中。如果找不到需要引用的参数，请尝试搜索它。

请查看[材质旗标](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-Mb557rsibt7WkRMyAMQ/v/chinese/information/textures/shader/material-flags/@drafts)来查看枚举的 $flags和 $flags2 参数的具体使用方法。

请查看材质贴图编译旗标（Material Map Compile Flags）的特殊 `%compile` 参数列表来查看可以改vbsp编译材料行为的参数。

**这个列表还远远不够完整。**

### **基础**

* [$basetexture](usdbasetexture.md)

### 反射

* [$reflectivity](usdreflectivity.md)

### 材质标志

* [Material Flags](material-flags.md)











{% hint style="info" %}
参考文献：

* [https://developer.valvesoftware.com/wiki/Shader](https://developer.valvesoftware.com/wiki/Shader)
* [https://developer.valvesoftware.com/wiki/Category:List\_of\_Shader\_Parameters](https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters)
{% endhint %}

