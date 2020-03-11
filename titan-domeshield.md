# Titan Domeshield

## Preparation

In this guide you will have to edit vmt and vtf files. I would recommend you to use the software [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones for vmt, however you'd need [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) and an image editing software for the vtf files.

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)

## Unpacking

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

## Editing

To edit the domeshield you'd need to find the .vmt and .vtf files. You will find the different file locations details about what to modify in the different files.

You can edit the texture on the domeshield, [here](https://noskill.gitbook.io/titanfall2/information/color-and-texture-info) is more information about vtf and how to edit it the way you like.

You will also need a photo editor, [here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) is some tools that you can use for graphics changes.

### Editing the texture

For editing the texture for the domeshield, go to this location.

> \materials\effects\black

Copy and paste the `black.vtf` into the same folder and rename it to whatever you want. For consistancy I'll rename it and refer to it as `dome.vtf`.

Now you'd want to edit the `dome.vtf` texture, open it with the [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) tool, export the image as an png and open it up in in your photo editor. Add the picture you want ontop of the texture and resize it so it fits within the size of the texture, save it as a png and import it back into the [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) tool, saving it as `dome.vtf` in the same directory.

### Applying the texture

For changing the texture for the domshield to the one we just created, go to this location.

> \materials\models\fx\xo\_shield\_edgedetect

Open the xo\_shield\_edgedetect.vmt file and locate these lines, these are what you want to change.

```text
"$color2" "[1 1 1]"

"$basetexture" "effects\black"
"$Texture2" "effects\black"
```

Change `black` to whatever you named your vtf file, which in my case is `dome`. I would also recommend increasing the color values a bit so the texture becomes easier to see as it is normally quite hard to see.

```text
"$color2" "[3 3 3]"

"$basetexture" "effects\dome"
"$Texture2" "effects\dome"
```

{% hint style="info" %}
If the texture is either too bright or too dark then you should try and increase or decrease the color values until it has the right brightness/color. In the example below the values are increased to 5.
{% endhint %}

### Example

![domeshield texture replaced with doge](.gitbook/assets/titanfall-2-screenshot-2020.03.11-19.41.56.68.png)

## Repacking

​[How to repack VPK files proprely ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new domeshield texture!

> Origin Games\Titanfall2\vpk\

