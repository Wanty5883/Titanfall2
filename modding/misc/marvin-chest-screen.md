---
description: Guide to edit texture on Marvin chest screen
---

# Marvin - Chest screen

## Preparation <a href="#preparation" id="preparation"></a>

In this guide you will have to edit vmt files. I would recommend you to use the software [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

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

To edit marvin screen chest, go to this location

> materials\models\robots\marvin

The file _`marvin_face_happy.vtf`_ and / or _`marvin_face_sad`_ can be replaced with any picture, their size have to be **128x128**.

[How to edit animated texture color](https://noskill.gitbook.io/titanfall2/information/color-and-texture-info#how-to-edit-animated-texture-color)

## Repacking <a href="#repacking" id="repacking"></a>

​[How to repack VPK files properly?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following step by step the previous link

Rename `pak000_000.vpk` _to_ `client_mp_common.bsp.pak000_000.vpk`

Rename `pak000_dir.vpk` _to_ `englishclient_mp_common.bsp.pak000_dir.vpk`

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your changes!
