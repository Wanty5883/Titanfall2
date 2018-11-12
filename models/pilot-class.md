---
description: Guide to swap pilot models
---

# Pilot class

## Preparation <a id="preparation"></a>

In this guide you will have to edit vmt files. I would recommend you to use the software [VTFEdit](https://wanty5883.gitbook.io/titanfall2/information/modding-tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://wanty5883.gitbook.io/titanfall2/information/modding-tools)​

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://wanty5883.gitbook.io/titanfall2/how-to-start-modding/2.-how-to-backup-extract-and-repack)​

## Editing

To change pilot class models go to this directory:

> models\humans\pilots

To change the pilot class you want, first off find the file linked to this class. Then choose the class you want and duplicate them. Then just rename the duplicated files into the name of the class you wanted to change.

The files in the folder have different name who correspond to those pilot classes:

* pilot\_jester = Stim
* pilot\_medium\_stalker = Holo
* pilot\_medium\_reaper = Pulse Blade
* pilot\_medium\_geist = Grapple
* pilot\_heavy\_roog = A-wall

The _f_ & _m_ at the end of the files are about female and male version of each pilot classes.

## Repacking <a id="repacking"></a>

​[How to repack VPK files proprely ?](https://github.com/Wanty5883/Titanfall2/wiki/General-Info#how-to-repack-vpk-files-proprely-)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

