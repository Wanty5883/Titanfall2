# Titan Domeshield

## Preparation

In this guide you will have to edit vmt and vtf files. I would recommend to use the software [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) to edit them.To edit vmt files you can use any text editor such as Atom, NotePad++, VIM and many more, however you need [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) and an image editing software for the vtf files. Alternatively you can use VTF plugins for photo editing software such as Gimp, Photoshop and many more.

Navigate to your VPK folder and find the following VPK files:

> Origin Games\Titanfall2\vpk\

Copy these files and paste them into an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. You can find that [here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools).

## Unpacking

Now that your files have been backed up and everything is installed, navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

## Editing

To edit the texture of the doomshield go to this location.

> \materials\effects\

The texture used for doomshield is `black.vtf`, you can either change this texture or create a new one.  
Editing this texture will have impact on other effect in the game.

It is recommended to create a new texture so it is possible to make custom effect for specific part of the game.

Choose a texture, you can check [here](../../information/textures/colors/texture-library.md). With your chosen texture, compile it with [VTFEdit](../../how-to-start-modding/modding-tools/source/vtf-and-vmt/vtfedit.md). For consistency the [`.vtf`](../../information/textures/valve-texture-format-vtf/) file will be renamed as`dome.vtf`.

For the parameters you can apply the same as the original texture or you can make your own and test things around! Feel free to send us your results on our Discord server. We might add what you obtained in the wiki! ![](../../.gitbook/assets/08c0a077780263f3df97613e58e71744.svg) 

### Applying the texture

To change the texture of the doomshield to the one just created, go to this location.

> materials\models\fx\

Open the `xo_shield_edgedetect.vmt` file and locate these lines, they are what you want to change.

```text
"$basetexture" "effects\black"
"$Texture2" "effects\black"
```

Change `black` to whatever you named your [`.vtf`](../../information/textures/valve-texture-format-vtf/) file, in this case dome.

```text
"$basetexture" "effects\dome"
"$Texture2" "effects\dome"
```

{% hint style="info" %}
Color can be changed. If the texture is black then the color applied in your [material file](../../information/textures/valve-material-type-vmt.md) will be accurate. If the texture is not black, then the color won't be accurate as the starting point is no longer the set color. Find more information on this [page](../../information/textures/colors/) about colors in material files.
{% endhint %}

### Example

![domeshield texture replaced with doge. &quot;$color2&quot; &quot;\[5 5 5\]&quot;](../../.gitbook/assets/titanfall-2-screenshot-2020.03.11-19.41.56.68.png)

## Repacking

​[How to repack VPK files proprely ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following the previous link closely:

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new domeshield texture!

> Origin Games\Titanfall2\vpk\

