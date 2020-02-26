# Sword block color

## Preparation

In this guide you will have to edit vmt files. I would recommend you use the software [VTFEdit](https://github.com/Wanty5883/Titanfall2/wiki/General-Info#tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://wanty5883.gitbook.io/titanfall2/information/modding-tools)

## Unpacking

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

[How to extract VPK's properly ?](https://wanty5883.gitbook.io/titanfall2/information/modding-tools)

## Editing

For editing the Sword Block FX color, go to this directory:

> materials\models\fx

Open the file _`titan_sword_block_fx.vmt`_ and find this string _`"$color2" "[1 1.5 2]"`_

[Here](https://wanty5883.gitbook.io/titanfall2/information/color-and-texture-info#usdlayercolor) more information about that value and how to edit the way you like.

### Example

[Here](https://gfycat.com/LivelyEqualDevilfish) is a little example.

## Repacking

[How to repack VPK files proprely ?](https://wanty5883.gitbook.io/titanfall2/how-to-start-modding/2.-how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

