---
description: Modding guide to change color of the holographic walls around the map
---

# Holographic wall color

## Used VPK

{% hint style="success" %}
* englishclient\_mp\_wargames.bsp.pak000\_dir.vpk
{% endhint %}

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)

{% page-ref page="../../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

## Editing <a id="editing"></a>

To edit the following color effect you need to find their `.vmt` files. Further in this guide you will find the different file locations and details about what modifications can be done.

In the page linked down bellow you will find additionnal information to modify the material and texture files.

{% page-ref page="../../../information/textures/colors/color-and-texture-info.md" %}

Navigate to this location in your extracted folder.

> materials\world\utility

Open the file `holo_map_grid_light_blue.vmt` and / or `holo_map_grid_orange.vmt` and refer to the different information provided.

As both files are meterial files, [changing the color](https://noskill.gitbook.io/titanfall2/information/textures/colors/color-and-texture-info#usdlayercolor) is quite straight forward.

In the examples down bellow, this color values are being used.

```text
"$color2" "[3 0 1.65]"
```

This material files leave quite a lot of possibilities, you could change the texture itself, use multiple layer, rotate the texture, play a gif, etc. Feel free to mess with it and share your results in our Discord community.

### Examples

{% embed url="https://gfycat.com/thriftyfaintkronosaurus" %}

{% embed url="https://gfycat.com/reliableboringasiaticmouflon" %}

![made by chrisssgx\#5949](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/WarGames%20-%20Holographic%20wall%20color1.png)

![made by chrisssgx\#5949](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/WarGames%20-%20Holographic%20wall%20color2.png)

![made by chrisssgx\#5949](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/WarGames%20-%20Holographic%20wall%20color3.png)

## Repacking

{% page-ref page="../../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

