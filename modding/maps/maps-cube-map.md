---
description: 编辑立体地图的步骤指南
---

# 地图-立体地图

## 前期准备

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these files and paste them into an empty folder somewhere else:

* englishclient\_mp\_**mapname**.bsp.pak000\_dir.vpk
* client\_mp\_**mapname**.bsp.pak000\_000.vpk

{% hint style="info" %}
Check the [list of VPK archives](https://noskill.gitbook.io/titanfall2/game-values/file-location/vpk-file-names), their names can be confusing
{% endhint %}

{% hint style="danger" %}
Make sure to make a Backup of every single Map you edit, Since every map has it's own VPK.
{% endhint %}

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)

## 解包

Now that these files have been backed up and everything is installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_**mapname**.bsp.pak000\_dir.vpk

[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

## 编辑

Navigate to this location in your extracted folder

> \materials\skies

This folder contains the texture for the cubemap. The file we are looking for are `.vtf` files. Once you did open them you can view the different faces of the cubemap by using the face parameters in [VTFedit](../../how-to-start-modding/modding-introduction/modding-tools/#vtf-and-vmt).

![](../../.gitbook/assets/image%20%282%29.png)

A cube map have 6 individual pictures as a cube have 6 faces. When each individual faces are put together they should look like this

![All the faces of a cubemap](../../.gitbook/assets/retrosun%20%281%29.png)

To make a new cubemap from scratch. You need to split a 360° picture into 6 individual picture. You can use this website to do so [https://jonaszeitler.se/cubemap-toastmap-generator/](https://jonaszeitler.se/cubemap-toastmap-generator/)  
Using the plan bellow you should rename each individual faces according the number to be loaded in the correct order in VTFedit.

{% hint style="info" %}
You also need to rotate the faces as in the map. The color code give you the correct rotation.
{% endhint %}

![](../../.gitbook/assets/retrosun.png)

Once renaming and rotating the faces you need to import all of them in VTFedit. You do so by selecting multiple files at once.

![Selecting the 6 faces of the cubemap](../../.gitbook/assets/image%20%285%29.png)

When the picture are loaded into VTFedit you will have some parameters to select. Use the parameters as it is showed in the examples bellow

![](../../.gitbook/assets/image%20%284%29.png)

![You are not looking for parameters outside of the red zone](../../.gitbook/assets/vtfeditcubemap.png)

Once you click OK, VTFedit will process for some seconds then you will have your texture generated. You can navigate through the different faces by changing its values. It does not change the file, it is only a preview.

![](../../.gitbook/assets/vtfeditfaces.png)

You are now done making a custom cubemap. You now need to replace it with the vanilla one.

{% hint style="info" %}
Making backup of the original texture is very handy !
{% endhint %}

## 天空盒列表

{% hint style="info" %}
Here is some ready to use skyboxes: [Skybox list](https://github.com/Wanty5883/Titanfall2/tree/master/picture/skyboxes)
{% endhint %}

## 重新打包

[How to repack VPK files proprely?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)

After closely following the previous link step by step:

Rename pak000\_000.vpk _to_ **client\_mp\_\*mapname\*.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_\*mapname\*.bsp.pak000\_dir.vpk**

{% hint style="danger" %}
Make sure to pay attention when renaming them because every map has it's own VPK.
{% endhint %}

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see the changed [skybox](../../information/textures/skybox-basics/)!

> Origin Games\Titanfall2\vpk\

