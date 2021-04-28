---
description: 替换铁驭模型指南
---

# 模型-铁驭类

{% hint style="danger" %}
Note: Changing pilot models may result in broken animations or even crashes.  
  
 However, changing arm models works perfectly fine on any tactical.
{% endhint %}

## 前期准备 <a id="preparation"></a>

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## 解包 <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

## 编辑

To change pilot class models go to this directory:

> models\humans\pilots

If you want to change the look of the arms, you can go to:

> models\weapons\arms

To change the pilot class you want, first off find the file linked to this class. Then choose the class you want and duplicate them. Then just rename the duplicated files into the name of the class you wanted to change.

The files in the folder have different names that correspond to their pilot classes:

* pilot\_light\_jester = 激素
* pilot\_light\_ged = 相位转移
* pilot\_medium\_stalker = 幻影铁驭
* pilot\_medium\_reaper = 脉冲刀
* pilot\_medium\_geist = 钩爪
* pilot\_heavy\_roog = A盾
* pilot\_heavy\_drex = 隐身

The _f_ & _m_ at the end of the files correspond to the _female_ and _male_ versions of each pilot class.

## 重新打包 <a id="repacking"></a>

​[How to repack VPK files properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

