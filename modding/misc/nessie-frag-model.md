---
description: 把你的手榴弹或任何投掷物变成尼斯湖水怪
---

# 尼斯湖水怪模型

## 前期准备 <a id="preparation"></a>

In this guide you will have to edit vmt files. I would recommend you to use the software [VTFEdit](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## 解包 <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

## 编辑

You can now open the folder you created that contains the extracted VPK and head to this directory:

> "extracted folder name"\scripts\weapons

Once you reach this point you can open a text file named:

> mp\_weapon\_frag\_grenade.txt
>
> -Note: You don't have to use the frag grenade. You can use other ordinances if you wish.

Scroll down to the section named **//Models**, with 3 subsections named **"Viewmodel"** **"playermodel"** and **"Projectilemodel",** You leave these alone and only change the scripts to the right of them.

You can now replace **all** the model names from: 

**"models/weapons/grenades/ptpov\_frag\_grenade.mdl",  "models/weapons/grenades/m20\_f\_grenade.mdl", "models/weapons/grenades/m20\_f\_grenade\_projectile.mdl"**

to:

**"models/nessy\_doll.mdl"**

## 重新打包 <a id="repacking"></a>

​[How to repack VPK files properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

## 结果展示

eh...ill do it later ;\).....[maybe](https://gfycat.com/bestfilthykid)























