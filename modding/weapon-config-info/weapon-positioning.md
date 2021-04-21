---
description: Position of the weapon on screen
---

# Weapon Positioning

## Preparation

Locate your game folder and find this folder if you are on Origin:

> Origin Games\Titanfall2\vpk\

Or this folder if you are on Steam:

> Steam\steamapps\common\Titanfall2\vpk\

Copy these files and paste them in a backup folder somewhere else:

* `englishclient_mp_common.bsp.pak000_dir.vpk`
* `client_mp_common.bsp.pak000_000.vpk`

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)

## Unpacking

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

## Editing

Navigate to this location in your extracted folder

> \scripts\weapons

This folder contains the "config files" for the weapons. Edit those files at your own risk, if you get banned because you edit some important value don’t blame me.

Find this part of code in the file:

```text
MP_BASE
	{
```

You want to add the following command in there:

```text
"viewmodel_offset_hip" 						"x z y"
```

So it should look like this: 

```text
MP_BASE
	{	"viewmodel_offset_hip" 						"x z y" 
```

### Position Values

The Standard value for each of the coordinates is "0". 

A positive "X" value is going to move the gun to the right, a negative one to the left.

A positive "Z" value is going to move the gun Forwards, a negative one backwards.

A positive "Y" value is going to move the gun up, a negative one down. 

### Examples

![&quot;viewmodel\_offset\_hip&quot; 						&quot;-10 0 -3&quot;](../../.gitbook/assets/another-kraber-edit.jpg)

![&quot;viewmodel\_offset\_hip&quot; 						&quot;2 -2 -3&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.04-16.25.20.77.png)

![&quot;viewmodel\_offset\_hip&quot; 						&quot;-6.5 1 -4&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.04-16.47.10.40.png)

## Repacking

[How to repack VPK files properly?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)

After closely following the previous link step by step:

Rename `pak000_000.vpk` _to_ `client_mp_common.bsp.pak000_000.vpk`

Rename `pak000_dir.vpk` _to_ `englishclient_mp_common.bsp.pak000_dir.vpk`

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new weapon position!

