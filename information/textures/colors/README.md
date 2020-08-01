# Texture & Colors

## RGB

**RGB** stands for **r**ed, **g**reen, **b**lue. In a [TGA](../../file-format/truevision-graphics-adapter-tga.md) or [VTF](../valve-texture-format-vtf/), each pixel of the image is defined by three [bytes](https://developer.valvesoftware.com/wiki/Byte) that define how much red, green, and blue light are added together to produce the color in that pixel. Textures can also have a fourth channel, called [alpha](https://developer.valvesoftware.com/wiki/Alpha), which can store other information for each pixel \(usually opacity\).

* The three or four separate values for each color are called 'channels'. [Shaders](https://developer.valvesoftware.com/wiki/Shader) in Source can manipulate each channel individually to produce color effects.
* Within [materials](../valve-material-type-vmt.md), an RGB colour is a [material vector](../material-vector.md).

### RGB Vec

In the RGB color system, you specify a color in terms of fractions of red, green, and blue, corresponding to how strongly glowing are the tiny red, green, and blue dots of the computer screen. In the RGB scheme, white is the color with a maximum of red, blue, and green \(1, 1, 1\). Black has minimum amounts \(0, 0, 0\). The brightest red is represented by \(1, 0, 0\); that is, it has the full amount of red, no green, and no blue.

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

Colors may appear differently on different computers, and under different 3D lighting conditions. The named colors above are most likely to display appropriately, because RGB values of 0 or 1 are unaffected by differing color corrections \("gamma" corrections\).

In Titanfall 2 it is possible to use values over 1. Giving over exposure \(HDR ?\).

## Source & reference

{% hint style="info" %}
Source

* [https://www.glowscript.org/docs/GlowScriptDocs/color.html](https://www.glowscript.org/docs/GlowScriptDocs/color.html)
* [https://developer.valvesoftware.com/wiki/RGB](https://developer.valvesoftware.com/wiki/RGB)

Reference: [https://thebookofshaders.com/06/?lan=us](https://thebookofshaders.com/06/?lan=us)
{% endhint %}

