---
description: >-
  Modding guide to change color of the holographic walls and arrows around the
  map
---

# Holographic wall color

## Preparation

For this guide you will need a VPK tool and a text editor.

{% content-ref url="../../../intro/duction/tools/" %}
[tools](../../../intro/duction/tools/)
{% endcontent-ref %}

## Used VPK

{% hint style="success" %}
* englishclient\_mp\_wargames.bsp.pak000\_dir.vpk
{% endhint %}

## Extracting

{% content-ref url="../../../intro/duction/vpk-packpack.md" %}
[vpk-packpack.md](../../../intro/duction/vpk-packpack.md)
{% endcontent-ref %}

## Editing <a href="#editing" id="editing"></a>

Navigate to this location in your extracted folder.

> materials\world\utility

This location contains all the `.vmt` files of the holographic walls

Following bulleted list contains names of the files in this location and their short descriptions. Picture examples are located further in this guide.

* `holo_map_grid_light_blue.vmt` blue arrows
* `holo_map_grid_light_blue_shootable.vmt` blue holographic walls
* `holo_map_grid_mip0.vtf` base texture used by holographic walls
* `holo_map_grid_orange.vmt` orange arrows&#x20;
* `holo_map_grid_orange_shootable.vmt` orange holographic walls and outer holographic walls
* `holo_map_grid_red_dense.vmt` holographic walls of the pit

Open a `.vmt` file you want to edit.

To edit colors simply change the values of `"$color2"`. For more details on changing these values, refer to [Color & Texture info](https://noskill.gitbook.io/titanfall2/information/textures/colors/color-and-texture-info#usdlayercolor)

These material files leave quite lot of possibilities, you could replace textures the walls use, make them transparent, clear, changing colors, put any picture on them, play a gif, etc. In the page linked down bellow you will find additional information to modify the material and texture files. Feel free to experiment with it and share your results in our Discord community.

{% content-ref url="../../../documentation/textures/colors/color-and-texture-info.md" %}
[color-and-texture-info.md](../../../documentation/textures/colors/color-and-texture-info.md)
{% endcontent-ref %}

### Examples

![As mentioned in the bulleted list these are orange arrows with "$color2" changed to "\[3 0 1.65\]"](../../../.gitbook/assets/titanfall-2-screenshot-2021.02.05-16.18.02.39.png)

![As mentioned in the bulleted list these are blue arrows with "$color2" changed to "\[0 1.5 3\]"](../../../.gitbook/assets/titanfall-2-screenshot-2021.02.05-16.18.33.95.png)

![As mentioned in the bulleted list these are orange holographic walls with "$color2" changed to "\[4 0 0\]" (red) and blue holographic walls with "$color2" changed to "\[0 4 0\]" (green)](../../../.gitbook/assets/titanfall-2-screenshot-2021.02.05-16.17.32.05.png)

![As mentioned in the bulleted list orange holographic walls use the same .vmt as outer holographic walls these are outer holographic walls](../../../.gitbook/assets/titanfall-2-screenshot-2021.02.05-16.58.39.64.png)

![As mentioned in the bulleted list these are holographic walls of the pit with "$color2" changed to "\[4 4 0\]" (yellow)](../../../.gitbook/assets/titanfall-2-screenshot-2021.02.05-17.16.37.14.png)

{% embed url="https://gfycat.com/thriftyfaintkronosaurus" %}

{% embed url="https://gfycat.com/reliableboringasiaticmouflon" %}

![made by frog#1626](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/WarGames%20-%20Holographic%20wall%20color1.png)

![made by frog#1626](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/WarGames%20-%20Holographic%20wall%20color2.png)

![made by frog#1626](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/WarGames%20-%20Holographic%20wall%20color3.png)

![Clear walls](../../../.gitbook/assets/titanfall-2-screenshot-2021.02.16-17.26.26.82.png)

## Repacking

{% content-ref url="../../../intro/duction/vpk-packpack.md" %}
[vpk-packpack.md](../../../intro/duction/vpk-packpack.md)
{% endcontent-ref %}

This guide will be updated with making the walls transparent, clear, changing colors, putting any picture on them, playing a gif, etc. if there is interest shown in the Discord community.
