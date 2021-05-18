---
description: >-
  A shader is software which runs on a graphics card to determine how an object
  should be drawn. Source uses shaders for everything in the 3D world.
---

# 着色器

A shader is software which runs on a graphics card to determine how an object should be drawn. Source uses shaders for everything in the 3D world.

Shaders are manipulated with parameters stored in [material](../valve-material-type-vmt.md) files. While the most common are quite simple, very complex ones exist to handle effects like real-time shadowing, lighting and refraction.

## Types

There are two variations of shaders, Pixel shaders and Vertex shaders, each of which performs a different task in the rendering pipeline. Shaders form a replacement for the fixed function pipeline and allow developers greater control over rendering output by providing the ability to modify pixels and vertices dynamically. The SDK includes many [existing shaders](https://developer.valvesoftware.com/wiki/Category:Shaders).

## Shader languages

There are currently three main shader languages: [High Level Shader Language \(HLSL\)](https://developer.valvesoftware.com/wiki/HLSL), [C for Graphics \(Cg\)](https://developer.valvesoftware.com/wiki/CG) and [OpenGL Shading Language \(GLSL\)](http://en.wikipedia.org/wiki/GLSL). The Source engine uses [HLSL](https://developer.valvesoftware.com/wiki/HLSL) based shaders. However Cg is so similar that most Cg shaders can be quickly and easily ported to HLSL.

## Shader models

A shader model defines how advanced shading techniques are allowed to get on graphics card. This prevents older graphics cards from being physically able to recognize newer shading techniques. Currently there are five versions of shader models: SM 1.1, SM 1.4, SM 2.0, SM 3.0 and SM 4.0.

The Source engine will compile using Shader Model 2.0 by default, which is the most common model, but if you wish to compile shaders reserved for older or newer graphics cards, you will have to specify what shader model it should use, or the card will fail to use the shader.

When creating shaders for newer graphics cards, it's important to remember to support those with older cards, or you will quickly limit the specs of your game to only a select few. Older cards will require so called "shader fallbacks" to be specified, where a backup shader \(using an older shader model\) will be used if the newer shader fails.

If you want to learn more about the detailed specs of different Shader Models, read the [Wikipedia article](http://en.wikipedia.org/wiki/High_Level_Shader_Language).

 For information on authoring shaders for use in the Source engine, please see [Shader Authoring](https://developer.valvesoftware.com/wiki/Shader_Authoring).

### Vertex shaders

Vertex shaders are applied for each vertex run on a programmable pipeline. Its most basic goal is to transform geometry into screenspace coordinates so that the Pixel shader can rasterize an image. On a more complex scale, Vertex shaders are responsible for mesh deformation, lighting, shadowing and general vertex displacement. Vertex shaders cannot create vertices.

A heavily commented example vertex shader, ready for use in Source is provided below.

### Example vertex shader

This is a pass through shader - in so far as it makes no major modification to the vertex data, instead just passing the data through to the pixel shader stage.

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

## Pixel shaders

Pixel shaders are applied for each pixel rendered to the screen. A pixel shader expects input from interpolated vertex values, which it then uses to rasterize the image. Pixel shaders can produce a huge range of effects involving the color of individual pixels such as refraction, per-pixel lighting or reflection.

A heavily commented example pixel shader, ready for use in Source is provided below.

### Example pixel shader

The pixel shader below is intended for use as a post-process shader and creates a grayscale effect.

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

## Applications of shaders in Source

The Source engine provides for two separate forms of shaders, Posprocess and Per-Object, the majority of the effects and materials used within the Source engine rely heavily on their Pixel shader components.

### Postprocess

A Postprocess shader is typically a Pixel shader that works on a quad rendered across the entire screen. The quad is textured with a copy of the frame buffer, the Pixel shader can then alter and modify the rendered output to create a variety of effects, such as basic color modification to more advanced processes such as motion blur and bloom

{% hint style="info" %}
**Note:**This information is out of date, and the files are no longer included in the SDK. `sdk_bloom.cpp` and `sdk_bloom.ps20.fxc` define one possible shader that could be used as an alternative example
{% endhint %}

The Source SDK provides an example of this form of shader in the postprocess files \(`sdk_postprocess.cpp`, `sdk_postprocess_vs20.fxc`, and `sdk_postprocess_ps20.fxc`\)

Advanced Postprocess shaders, such as the bloom and motion blur shaders included with source, may also need to use custom [Render Targets](https://developer.valvesoftware.com/w/index.php?title=Render_Targets&action=edit&redlink=1). For more information on integrating a Postprocess shader with a mod, see [Custom\_Postprocessing\_Effects](https://developer.valvesoftware.com/wiki/Custom_Postprocessing_Effects)

### Per-object

A Per-Object shader in the Source engine is used on any object with the shader referenced in the relevant [Valve Material \(.vmt\)](../valve-material-type-vmt.md) file, such as a model or piece of brushwork. A Per-Object shader could be used to create a refractive material, modify a models vertices dynamically or other advanced rendering effects.

The Source SDK provides an example of a Per-Object shader in the lightmap files \( `sdk_lightmap.cpp`, `sdk_lightmap_vs20.fxc`, and `sdk_lightmap_ps20.fxc`\)

## List of shader parameters

This category list top-level parameters available in the "Generic" shaders.

* Parameters for specialized shaders are documented in the shaders articles themselves.
* Parameters for configuring a single effect are \(generally\) grouped into a single article. Try searching for a parameter if you can't find it listed.

See [Material Flags](material-flags.md) for $flags and $flags2 parameter enumerations.

See Material Map Compile Flags for the list of special `%compile` parameters which change the vbsp compile behaviors of materials.

**This list is far from complete.**

### **Basics**

* [$basetexture](usdbasetexture.md)

### Reflection

* [$reflectivity](usdreflectivity.md)

### M.

* [Material Flags](material-flags.md)











{% hint style="info" %}
Reference:

* [https://developer.valvesoftware.com/wiki/Shader](https://developer.valvesoftware.com/wiki/Shader)
* [https://developer.valvesoftware.com/wiki/Category:List\_of\_Shader\_Parameters](https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters)
{% endhint %}

