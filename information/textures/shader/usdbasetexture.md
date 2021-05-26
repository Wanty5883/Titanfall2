---
description: $basetexture是所有起源引擎游戏中可用的材质着色器参数，它定义了反照率纹理。几乎没有材质不使用此参数，如果未定义，则某些着色器将加载默认纹理。
---

# $basetexture

##  $basetexture

**`$basetexture`** 是所有起源引擎游戏中可用的[材质](../valve-material-type-vmt.md) [着色器](https://developer.valvesoftware.com/wiki/Shader) 参数。它定义了[反照率贴图](../albedo.md)纹理。几乎没有[材质](../valve-material-type-vmt.md) 不使用此参数，如果未定义，则某些[着色器](./)将加载默认[纹理](../)。

## VMT语法

```text
$basetexture	<texture without extension, relative to <game>\materials\>
```

```text
LightmappedGeneric
{
	$basetexture	brick\brickwall031b
}
```

### 附加参数

#### `$basetexturetransform` `<`[`matrix`](https://developer.valvesoftware.com/wiki/Matrix)`>`

在材质使用前转换纹理，这不会影响曲面上的[光照贴图](../lightmap.md)。默认定位为 `"center .5 .5 scale 1 1 rotate 0 translate 0 0"`.

1. `center` 定义旋转点。 只有在 `rotate` 被使用时才会生效。
2. `scale` 将纹理与指定数量的材质相匹配 '`2 1`' 是X轴上50%的比例。
3. `rotate` 以度为单位逆时针旋转纹理。它可以设为任何数字，包括负数。
4. `translate` 按指定数字移动纹理。 '`.5`' 会把它移到另一半。

{% hint style="info" %}
必须包含所有数值！
{% endhint %}

{% hint style="warning" %}
**Bug:** 缩放纹理可能会导致奇怪的问题，因为Hammer中的纹理锁定工具实际上无法将纹理锁定到位。
{% endhint %}

{% hint style="warning" %}
**Bug:** 应用于笔刷的旋转纹理将围绕贴图原点旋转（确认：仅限Orangebox引擎？）。解决方法是将VMT中的中心位置更改为笔刷的原点。
{% endhint %}

#### `$frame` `<`[`integer`](https://developer.valvesoftware.com/wiki/Integer)`>`

这是为多帧纹理显示的帧。它通常由 [AnimatedTexture](https://developer.valvesoftware.com/wiki/List_Of_Material_Proxies#Texture_manipulation) 或者 [TextureToggle](https://developer.valvesoftware.com/wiki/List_Of_Material_Proxies#Entity_integration) 替代设置，但也可以手动设置。该值必须是有效索引，否则可能会发生游戏崩溃。

## $basetexture2

一些着色器（最著名的是 [WorldVertexTransition](https://developer.valvesoftware.com/wiki/WorldVertexTransition)）允许使用两个反照率贴图。第二个纹理由一组名称带有 '2' 的镜像命令处理：

#### `$basetexture2` `<`[`texture`](../)`>`

#### `$basetexturetransform2` `<`[`matrix`](https://developer.valvesoftware.com/wiki/Matrix)`>`

{% hint style="warning" %}
**Bug:** `$basetexturetransform2` 在WorldVertexTransnsion的DX9版本中不存在，仅适用于DX8着色器。在DX9中，`$basetexture2` will instead move with the original `$basetexturetransform` in sync with `$basetexture`. 这将会在 [![&amp;lt;Source&amp;gt;](https://developer.valvesoftware.com/w/images/1/18/Source_07_icon_16x16.png)](https://developer.valvesoftware.com/wiki/Source_2007) [Source 2007](https://developer.valvesoftware.com/wiki/Source_2007), [![&amp;lt;Source&amp;gt;](https://developer.valvesoftware.com/w/images/3/3b/Source_13_icon_16x16.png)](https://developer.valvesoftware.com/wiki/Source_2013) [Source 2013](https://developer.valvesoftware.com/wiki/Source_2013)，和 [![&amp;lt;Alien Swarm&amp;gt;](https://developer.valvesoftware.com/w/images/c/c9/AS-16px.png)](https://developer.valvesoftware.com/wiki/Alien_Swarm) [Alien Swarm](https://developer.valvesoftware.com/wiki/Alien_Swarm).中出现。其他游戏尚未测试。
{% endhint %}

{% hint style="info" %}
**Code Fix:** [![&amp;lt;Mapbase&amp;gt;](https://developer.valvesoftware.com/w/images/a/a8/Icon_Mapbase.png)](https://developer.valvesoftware.com/wiki/Mapbase) [Mapbase](https://developer.valvesoftware.com/wiki/Mapbase) adds support for `$basetexturetransform2` in Source 2013. The specific code can be found [on its repository](https://github.com/mapbase-source/source-sdk-2013) in the [LightmappedGeneric](https://developer.valvesoftware.com/wiki/LightmappedGeneric) shader files.
{% endhint %}

#### `$frame2` `<`[`integer`](https://developer.valvesoftware.com/wiki/Integer)`>`

还有更多的含 '2' 命令应用于各种着色器效果，每个命令都在各自的文章中进行了说明。

## 来源和参考

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/$basetexture](https://developer.valvesoftware.com/wiki/$basetexture)
{% endhint %}

