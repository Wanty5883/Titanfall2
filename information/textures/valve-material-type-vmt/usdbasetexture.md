---
description: >-
  $basetexture is a material shader parameter available in all Source games. It
  defines an albedo texture. It is very rare for a material not to use this
  parameter and some shaders will load a default t
---

# $basetexture

##  $basetexture

**`$basetexture`** is a [material](./) [shader](https://developer.valvesoftware.com/wiki/Shader) parameter available in all Source games. It defines an [albedo](https://developer.valvesoftware.com/wiki/Albedo) texture. It is very rare for a [material](./) not to use this parameter and some [shaders](https://developer.valvesoftware.com/wiki/Shader) will load a default [texture](../) if it stays undefined.

## VMT syntax

```text
$basetexture	<texture without extension, relative to <game>\materials\>
```

```text
LightmappedGeneric
{
	$basetexture	brick\brickwall031b
}
```

### Additional parameters

#### `$basetexturetransform` `<`[`matrix`](https://developer.valvesoftware.com/wiki/Matrix)`>`

Transforms the texture before use in the material. This does not affect [lightmaps](https://developer.valvesoftware.com/wiki/Lightmaps) on the surface.The default position is `"center .5 .5 scale 1 1 rotate 0 translate 0 0"`.

1. `center` defines the point of rotation. Only useful if `rotate` is being used.
2. `scale` fits the texture into the material the given number of times. '`2 1`' is a 50% scale in the X axis.
3. `rotate` rotates the texture counter-clockwise in degrees. Accepts any number, including negatives.
4. `translate` shifts the texture by the given numbers. '`.5`' will shift it half-way.

{% hint style="info" %}
All values must be included!
{% endhint %}

{% hint style="warning" %}
**Bug:** Scaling the texture may cause odd issues where the Texture Lock tool in Hammer will not actually lock the texture in place.
{% endhint %}

{% hint style="warning" %}
**Bug:** Rotating textures applied on brushes will rotate around the map origin \(confirm: Orangebox engine only?\). A fix for this is to change the center position in the VMT to the brush's origin.
{% endhint %}

#### `$frame` `<`[`integer`](https://developer.valvesoftware.com/wiki/Integer)`>`

The frame displayed for a multi-frame texture. This is normally set by the [AnimatedTexture](https://developer.valvesoftware.com/wiki/List_Of_Material_Proxies#Texture_manipulation) or [TextureToggle](https://developer.valvesoftware.com/wiki/List_Of_Material_Proxies#Entity_integration) proxies, but can be set manually. The value must be a valid index, or crashes might occur.

## $basetexture2

Some shaders \(most notably [WorldVertexTransition](https://developer.valvesoftware.com/wiki/WorldVertexTransition)\) allow the use of two albedos. The second texture is handled by a mirrored set of commands with '2' in their name:

#### `$basetexture2` `<`[`texture`](../)`>`

#### `$basetexturetransform2` `<`[`matrix`](https://developer.valvesoftware.com/wiki/Matrix)`>`

{% hint style="warning" %}
**Bug:** `$basetexturetransform2` doesn't exist in the DX9 version of WorldVertexTransition, only working with the DX8 shader. In DX9, `$basetexture2` will instead move with the original `$basetexturetransform` in sync with `$basetexture`. This is the case in [![&amp;lt;Source&amp;gt;](https://developer.valvesoftware.com/w/images/1/18/Source_07_icon_16x16.png)](https://developer.valvesoftware.com/wiki/Source_2007) [Source 2007](https://developer.valvesoftware.com/wiki/Source_2007), [![&amp;lt;Source&amp;gt;](https://developer.valvesoftware.com/w/images/3/3b/Source_13_icon_16x16.png)](https://developer.valvesoftware.com/wiki/Source_2013) [Source 2013](https://developer.valvesoftware.com/wiki/Source_2013), and [![&amp;lt;Alien Swarm&amp;gt;](https://developer.valvesoftware.com/w/images/c/c9/AS-16px.png)](https://developer.valvesoftware.com/wiki/Alien_Swarm) [Alien Swarm](https://developer.valvesoftware.com/wiki/Alien_Swarm). Other games have not been tested.
{% endhint %}

{% hint style="info" %}
**Code Fix:** [![&amp;lt;Mapbase&amp;gt;](https://developer.valvesoftware.com/w/images/a/a8/Icon_Mapbase.png)](https://developer.valvesoftware.com/wiki/Mapbase) [Mapbase](https://developer.valvesoftware.com/wiki/Mapbase) adds support for `$basetexturetransform2` in Source 2013. The specific code can be found [on its repository](https://github.com/mapbase-source/source-sdk-2013) in the [LightmappedGeneric](https://developer.valvesoftware.com/wiki/LightmappedGeneric) shader files.
{% endhint %}

#### `$frame2` `<`[`integer`](https://developer.valvesoftware.com/wiki/Integer)`>`

There are further '2' commands applying to various shader effects, which are each documented in their respective articles.

## **Source & reference**

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/$basetexture](https://developer.valvesoftware.com/wiki/$basetexture)
{% endhint %}

