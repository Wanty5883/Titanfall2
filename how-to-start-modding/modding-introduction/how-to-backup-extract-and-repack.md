---
description: How to play around with VPKs without messing everything up
---

# How to backup, extract & repack

## How to backup & extract VPK's properly?

When you are about to extract [VPK ](../../information/file-format/vpk-valve-pak-file.md)files, you need a directory where the files will be extracted to from the selected [VPK](../../information/file-format/vpk-valve-pak-file.md). This folder **should not** be inside your game directory. I would recommend for you to create a folder with an easy name like `Titanfall 2 modding` in this path: `C:\Users\<username>\Documents` 

```text
C:\Users\<username>\Documents\Titanfall 2 modding
```

Once you have created this folder I recommend creating a subfolder called `"Backup"` dedicated for, guess what.. backups. \(Yey!\)

```text
C:\Users\<username>\Documents\Titanfall 2 Modding\backup
```

Open the Titanfall VPK Tool and press `CTRL+O`. Navigate to your game folder and open the right file \(based on the guide you are reading\). Once you loaded the [VPK ](../../information/file-format/vpk-valve-pak-file.md)into the tool, click on the menu icon called _`Extract All`_. I personally put those files in a folder with the same name as the extracted [VPK](../../information/file-format/vpk-valve-pak-file.md), this makes it way easier to manage when you extract files from different VPK's.

After the extraction is complete, open the folder where you extracted your files to and delete the _`extracted_logs`_ folder.

{% hint style="warning" %}
**Only extract** [**VPK** ](../../information/file-format/vpk-valve-pak-file.md)**files from the game directory. If you try to extract** [**VPK** ](../../information/file-format/vpk-valve-pak-file.md)**files from your backup folder errors are caused!**
{% endhint %}

{% hint style="warning" %}
Make sure to use version 3.3 or 3.4 of the VPK tool. You may have unwanted behavior with previous version of the tool.
{% endhint %}

## **How to repack VPK files properly?**

Open the repacker tool inside the Titanfall VPK Tool. You have 2 ways to do that, click on the _`Repack VPK`_ icon, or go in _`Tools > Repacker`_. Once the tool opened, give as first directory your extracted folder

> e.g. C:\Users\YourSessionName\Documents\Titanfall\_2\_modding\Extracted\englishclient\_mp\_common.bsp.pak000\_dir.vpk

Then the second directory is to give your output, meaning where repack files will go. I would recommend that to be simple to find.

> C:\Users\YourSessionName\Documents\Titanfall 2 modding\Repack\

Leave the VPK file name as is, then click _`Build VPK`_. Once the VPK file has been built, navigate to their location. You will find two files named _`pak000_000.vpk`_ _`pack000_dir.vpk`_. Before moving those 2 files into your game directory, they have to be renamed. For each guide, you will be given the option to backup 2 files, their names have to be pasted on the 2 new files. You have to consider _`_dir`_ in the name, that would indicate to you which file gets the right name. \(Yeah I know, weird. Let me show you an example!\)

**e.g.**

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

## **VPK rename / move batch script**

{% hint style="success" %}
Bored of renaming / moving VPK files back to game directory?
{% endhint %}

There is a little batch script you can use!

```bash
ren "pak000_000.vpk" "client_mp_common.bsp.pak000_000.vpk"
ren "pak000_dir.vpk" "englishclient_mp_common.bsp.pak000_dir.vpk"
move "client_mp_common.bsp.pak000_000.vpk" "<ORIGINGAMES>\Titanfall2\vpk\client_mp_common.bsp.pak000_000.vpk"
move "englishclient_mp_common.bsp.pak000_dir.vpk" "<ORIGINGAMES>\Titanfall2\vpk\englishclient_mp_common.bsp.pak000_dir.vpk"
```

That's the script for _`englishclient_mp_common.bsp.pak000_dir.vpk`_, it can be adapted to any other VPKs you edit quite often. 

{% hint style="danger" %}
Make sure not to keep the VPK tool open while executing this script, as this will cause an error.
{% endhint %}

**Don't forget to add the correct game directory by replacing** _`<ORIGINGAMES>`_ with e.g. `C:\Program Files\Origin\Library` This is the directory in which your origin games are downloaded. Not the directory containing Titanfall 2 files. \(Mine is `H:\Orishit\Games`\)

{% page-ref page="modding-tools/" %}

