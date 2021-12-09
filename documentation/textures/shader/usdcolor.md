---
description: >-
  $color is a material shader parameter available in all Source games. It
  independently scales the red, green and blue channels of an albedo.
---

# $color

&#x20;**`$color`** is a [material](../valve-material-type-vmt.md) [shader](./) parameter available in all Source games. It independently scales the [red, green and blue](../colors/) channels of an [albedo](../albedo.md). There are two ways of expressing a value:

```
$color "[ <float> <float> <float> ]"
$color "{ <int> <int> <int> }"
```

The default is [`"[1 1 1]"`](../colors/#rgb-vec) or [`"{255 255 255}"`](../colors/#rgb).

## Gamma

Course uses a gamma correction of 2.2 by default. This must be taken into account when attempting to adjust the color of a texture to match some other color in a screenshot (for example, when trying to match the color of the bottom of a skybox material to the color of fog in the map). This is done by raising the initially calculated scale to the power of 2.2 before setting the `$color`value for your material. For example, if the sample (target) color in a screenshot is 120, the color of your texture at the point of interest is 240, and you want the two colors to match, you need to compute the [albedo](../albedo.md) scale for your material as $$(120 / 240) ^ 2.2 = 0.218$$ (not 0.5, as one might expect).

{% hint style="info" %}
**Tip:** Don't try to recreate a texture through a screenshot. [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape) is free.
{% endhint %}

## Solid color

This parameter can be used _without_ an [albedo](../albedo.md) to display a solid color without the need of a texture (except  a [`%tooltexture`](https://developer.valvesoftware.com/wiki/%tooltexture) ). As well as a small saving in performance and memory footprint, [material\_modify\_control](https://developer.valvesoftware.com/wiki/Material\_modify\_control) can be used to completely change the material's color at run-time if desired.

In this scenario, `"[1 1 1]"` is pure white.

{% hint style="info" %}
&#x20;**Tip:**If the material is representing empty blackness, you will probably want to use the [`UnlitGeneric`](https://developer.valvesoftware.com/wiki/UnlitGeneric) shader to prevent it from ever becoming grey.
{% endhint %}

## Models

A variant of **`$color`** named **`$color2`** is specific for use with [`VertexLitGeneric`](https://developer.valvesoftware.com/wiki/VertexLitGeneric). It works the same way as **`$color`** but for use on models.

```
$color2 "[ <float> <float> <float> ]"
$color2 "{ <int> <int> <int> }"
```

### Additional Model Parameters

#### `$blendtintbybasealpha` `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Left 4 Dead) (Also in Source 2013)

Enables the use of an alpha mask to define areas on the model to tint. Uses the alpha channel of the `$basetexture.`

**Bug:** Incompatible with [`$alphatest`](https://developer.valvesoftware.com/wiki/$alphatest) and [`$translucent`](https://developer.valvesoftware.com/wiki/$translucent).

#### `$blendtintcoloroverbase` `<`[`float`](https://developer.valvesoftware.com/wiki/Float)`>` (New with Team Fortress 2)

Sets the amount to replace with solid color. A value of '0' will be full tint while a value of '1.00' will replace the [albedo](../albedo.md) in the mask area with the color defined with `$color2.` Default value is '0'.

**Note:**This parameter is not available in [![\<Left 4 Dead>](https://developer.valvesoftware.com/w/images/c/c0/L4D-16px.png)](https://developer.valvesoftware.com/wiki/Left\_4\_Dead)[![\<Left 4 Dead 2>](https://developer.valvesoftware.com/w/images/9/93/L4D2-16px.png)](https://developer.valvesoftware.com/wiki/Left\_4\_Dead\_2) and [![\<Alien Swarm>](https://developer.valvesoftware.com/w/images/c/c9/AS-16px.png)](https://developer.valvesoftware.com/wiki/Alien\_Swarm).

#### `$tintmasktexture` `<`[`texture`](../)`>` (Only in Counter-Strike: Global Offensive)

Use a separate texture as a mask for color tinting instead of the [`$basetexture`](usdbasetexture.md)'s alpha. Only the green channel is used for tinting.

#### [`$allowdiffusemodulation`](https://developer.valvesoftware.com/wiki/$allowdiffusemodulation) `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Left 4 Dead)

Prevents the model's material from being tinted by `$color2` or `rendercolor.`

#### [`$notint`](https://developer.valvesoftware.com/wiki/$notint) `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (Only in Counter-Strike: Global Offensive)

Prevents the model's material from being tinted by `$color2` or `rendercolor.` Replaces `$allowdiffusemodulation` in [![\<Counter-Strike: Global Offensive>](https://developer.valvesoftware.com/w/images/3/35/Csgo.png)](https://developer.valvesoftware.com/wiki/Counter-Strike:\_Global\_Offensive).

## Caveats

* `$color2` is incompatible with the use of [`$selfillum`](https://developer.valvesoftware.com/wiki/$selfillum), as it will override the glow properties used by both `$selfillum` & `$selfillummask`. Use the `$selfillumtint` command to adjust the glow so it properly appears.

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/$color](https://developer.valvesoftware.com/wiki/$color)
{% endhint %}
