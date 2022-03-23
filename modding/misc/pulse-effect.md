---
description: Guide to modify your pulse effect
---

# Pulse Effect

## Preparation

In this guide you will have to edit vmt and vtf files. I would recommend to use the software [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) to edit them.To edit vmt files you can use any text editor such as Atom, NotePad++, VIM and many more, however you need [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) and an image editing software for the vtf files. Alternatively you can use VTF plugins for photo editing software such as Gimp, Photoshop and many more.

Locate your game folder and find this folder if you are on Origin:

> Origin Games\Titanfall2\vpk\

Or this folder if you are on Steam:

> Steam\steamapps\common\Titanfall2\vpk\

Copy these files and paste them in a backup folder somewhere else:

* `englishclient_mp_common.bsp.pak000_dir.vpk`
* `client_mp_common.bsp.pak000_000.vpk`

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. You can find that [here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools).

## Unpacking

Now that your files have been backed up and everything is installed, navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

## Editing

To edit the pulse effect you'll need to find the .vmt and .vtf files. You will find the different file locations details about what to modify in the different files.

You can edit the texture of the pulse effect, [here](https://noskill.gitbook.io/titanfall2/information/color-and-texture-info) is more information about vtf and how to edit it the way you like.

You will also need a graphic editor, [here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) are some tools that you can use for graphics changes.

### Editing the texture

To edit the texture of the pulse effect go to this location.

> \materials\effects\

The texture used for pulse effect is `black.vtf`, you can either change this texture or create a new one.  
Editing this texture will have impact on other effect in the game.

It is recommended to create a new texture so it is possible to make custom effect for specific part of the game.

Choose a texture, you can check [here](../../assets/texture-library.md). With your chosen texture, compile it with [VTFEdit](../../how-to-start-modding/modding-introduction/modding-tools/source/vtf-and-vmt/vtfedit.md). For consistency the [`.vtf`](../../documentation/textures/valve-texture-format-vtf/) file will be renamed as`pulse.vtf`.

For the parameters you can apply the same as the original texture or you can make your own and test things around! Feel free to send us your results on our Discord server. We might add what you obtained in the wiki! ![](../../.gitbook/assets/08c0a077780263f3df97613e58e71744.svg) 

### Applying the texture

To change the texture of the pulse effect to the one just created, go to this location.

> materials\models\fx\

Open the `ar_impact_pilot.vmt` file and locate these lines, they are what you want to change.

```text
"$basetexture" "effects\black"
"$Texture2" "effects\black"
```

Change `black` to whatever you named your [`.vtf`](../../documentation/textures/valve-texture-format-vtf/) file, in this case pulse.

```text
"$basetexture" "effects\pulse"
"$Texture2" "effects\pulse"
```

{% hint style="info" %}
Color can be changed. If the texture is black then the color applied in your [material file](../../documentation/textures/valve-material-type-vmt.md) will be accurate. If the texture is not black, then the color won't be accurate as the starting point is no longer the set color. Find more information on this [page](../../documentation/textures/colors/) about colors in material files.
{% endhint %}

### Example

{% tabs %}
{% tab title="Fractal" %}
{% embed url="https://gfycat.com/damagedcluelesscirriped" %}

{% embed url="https://gfycat.com/farcavernousequestrian" caption="Fractal 01" %}

{% embed url="https://gfycat.com/clumsywickedbonobo" caption="Fractal 02" %}
{% endtab %}

{% tab title="Alien Pulse" %}
{% embed url="https://gfycat.com/alertaggravatingfly" caption="\"$basetexture\" & \"$Texture2\" edited" %}

{% embed url="https://gfycat.com/blaringhospitableaddax" caption="\"$Texture2\" edited" %}

{% embed url="https://gfycat.com/glossyscaredekaltadeta" caption="\"$basetexture\" edited" %}
{% endtab %}

{% tab title="Others" %}
{% embed url="https://gfycat.com/mellowklutzydavidstiger" %}
{% endtab %}
{% endtabs %}



## Repacking

​[How to repack VPK files properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following the previous link closely:

Rename `pak000_000.vpk` _to_ `client_mp_common.bsp.pak000_000.vpk`

Rename `pak000_dir.vpk` _to_ `englishclient_mp_common.bsp.pak000_dir.vpk`

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new pulse effect!

