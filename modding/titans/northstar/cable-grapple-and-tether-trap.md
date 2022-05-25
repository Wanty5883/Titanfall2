---
description: Guide to edit Grapple & Tather Trap texture
---

# Cable - Grapple & Tether Trap

## Preparation <a href="#preparation" id="preparation"></a>

In this guide you will have to edit vmt files. I would recommend you to use the software [VTFEdit](https://wanty5883.gitbook.io/titanfall2/information/modding-tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

Locate your game folder and find this folder if you are on Origin:

> Origin Games\Titanfall2\vpk\\

Or this folder if you are on Steam:

> Steam\steamapps\common\Titanfall2\vpk\\

Copy these files and paste them in a backup folder somewhere else:

* `englishclient_mp_common.bsp.pak000_dir.vpk`
* `client_mp_common.bsp.pak000_000.vpk`

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## Unpacking <a href="#unpacking" id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

## Editing

To edit grapple and tether trap cable color, go to this location

> materials\cable

Open the file _`grapple_col.vtf`_ with VTFEdit. Editing this texture file will change cable color of grapple hook and tether trap.

[How to edit animated texture color](https://noskill.gitbook.io/titanfall2/information/color-and-texture-info#how-to-edit-animated-texture-color)

## Repacking <a href="#repacking" id="repacking"></a>

​[How to repack VPK files properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following step by step the previous link

Rename `pak000_000.vpk` _to_ `client_mp_common.bsp.pak000_000.vpk`

Rename `pak000_dir.vpk` _to_ `englishclient_mp_common.bsp.pak000_dir.vpk`

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your changes!
