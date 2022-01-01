---
description: Guide to swap pilot models
---

# Models - Pilot class

{% hint style="danger" %}
Note: Changing pilot models may result in broken animations or even crashes.  
  
 However, changing arm models works perfectly fine on any tactical.
{% endhint %}

## Preparation <a id="preparation"></a>

Locate your game folder and find this folder if you are on Origin:

> Origin Games\Titanfall2\vpk\

Or this folder if you are on Steam:

> Steam\steamapps\common\Titanfall2\vpk\

Copy these files and paste them in a backup folder somewhere else:

* `englishclient_mp_common.bsp.pak000_dir.vpk`
* `client_mp_common.bsp.pak000_000.vpk`

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

## Editing

To change pilot class models go to this directory:

> models\humans\pilots

If you want to change the look of the arms, you can go to:

> models\weapons\arms

To change the pilot class you want, first off find the file linked to this class. Then choose the class you want and duplicate them. Then just rename the duplicated files into the name of the class you wanted to change.

The files in the folder have different names that correspond to their pilot classes:

* pilot\_light\_jester = Stim
* pilot\_light\_ged = Phase Shift
* pilot\_medium\_stalker = Holo Pilot
* pilot\_medium\_reaper = Pulse Blade
* pilot\_medium\_geist = Grapple
* pilot\_heavy\_roog = A-Wall
* pilot\_heavy\_drex = Cloak

The _f_ & _m_ at the end of the files correspond to the _female_ and _male_ versions of each pilot class.

## Repacking <a id="repacking"></a>

​[How to repack VPK files properly?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)​

After following step by step the previous link

Rename `pak000_000.vpk` _to_ `client_mp_common.bsp.pak000_000.vpk`

Rename `pak000_dir.vpk` _to_ `englishclient_mp_common.bsp.pak000_dir.vpk`

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your changes!

