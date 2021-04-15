---
description: 准星图标修改指南
---

# 准星修改

## 前期准备

进入以下目录并找到所需的VPK文件：

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。[工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

## 解包

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

[如何正确地解包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

## 编辑

进入解压文件夹中下面的目录：

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\weapons
```

这个文件夹包含所有武器的"配置文件"，修改文件所产生的风险由你自己承担。如果因为你修改核心数值而导致的账号封禁，别把责任归咎于我。

查找下面的代码块来得到准星代码部分的位置。

```text
active_crosshair_count                      “1”
rui_crosshair_index                         “0”

RUI_CrosshairData
```

从这部分到_`RUI_CrosshairData`_ 括号的底部都是我们将要修改的地方！\(终于到有意思的地方了！\)

想要修改准星，你需要去把_`ui`_ 成你想要的。You can find the value for the different crosshair in the game down bellow.

For example, change

_`ui/crosshair_tri`_ to _`ui/crosshair_alternator`_

That will change the classic AR / SMG \(used on R201, CAR, R97...\) to the Alternator crosshair.

Is possible to combine multiple crosshair at the same time, for that you need to duplicate _`Crosshair_1`_ bracket and is value inside like this example

```text
Crosshair_1
{
    “ui”                                     “ui/crosshair_plus”
    “base_spread”                            “0.0”
    Args
    {
        //isFiring weapon_is_firing
    }
}
```

Don't copy paste the value from this example, use the one you have in the edited file!

### active\_crosshair\_count

```text
active_crosshair_count "2"
```

This value set the amount of crosshair you would like to use at once. To use multiple crosshair at once, you need to change that value to the amount of `Crosshair_x` bracket you want to combine.

You can change the _`base_spread`_ value to change the based size of the crosshair, this won't change the vector size but the distance between the center of the screen and the different parts of the crosshair. You can use positive or negative values

### ui/crosshair

These values are the crosshair itself. They can be swapped to any other ui/crosshair value you can find in other config files. You can send me a message if you find other ones.

Some crosshairs are dynamic, like the charge rifle, frag grenade and a couple of other crosshairs that have animations. In some cases changing to another dynamic crosshair will work fine, in other cases it won't. As a working example: my favorite crosshair combo is using the charge rifle crosshair for the Northstar railgun. For a non working example: the frag grenade crosshair on the CAR won't work well.

![](../../../.gitbook/assets/crosshair1.PNG)

![](../../../.gitbook/assets/crosshair2.PNG)

![](../../../.gitbook/assets/crosshair3.PNG)

Some crosshair are dynamics, like the charge rifle, frag grenade and some other crosshair which have animation. In some case changing to another dynamic crosshair will work fine, in other cases it won't. As an example my favorite one is using the charge rifle crosshair for the Northstar railgun. For an opposite example, the frag grenade crosshair to the CAR won't work well.

### base\_spread

This value set the based size of the crosshair, this won't change the vector size but the distance between the center of the screen and the different parts of the crosshair. You can use positive or negative values.

### RUI\_CrosshairData & Arguments

Args or arguments can change how the crosshair is acting

| Argument | Value | Note |
| :--- | :--- | :--- |
| adjustedSpread | weapon\_spread |  |
| adsFrac | player\_zoomFrac |  |
| ammoFrac | "progress\_weapon\_clip\_ammo\_frac" |  |
| ammoFrac | "progress\_grapple\_power" |  |
| chargeFrac | player\_chargeFrac |  |
| chargeLevel | player\_chargeLevel |  |
| chargeMaxTime | eWeaponVar.custom\_float\_0 |  |
| chargeStartTime | weapon\_script\_time\_0 |  |
| clipAmmo | weapon\_ammo |  |
| clipSize | weapon\_clipSize |  |
| crosshairMovementX | crosshair\_movement\_x |  |
| crosshairMovementY | crosshair\_movement\_y |  |
| dryfireTime | "weapon\_latest\_dryfire\_time" |  |
| isActive | weapon\_is\_active |  |
| isAmped | weapon\_is\_amped |  |
| isFiring | weapon\_is\_firing |  |
| isGrappleInRange | "grapple\_in\_range" |  |
| isLocked | smartammo\_locked |  |
| isReloading | weapon\_is\_reloading |  |
| isSprinting | player\_is\_sprinting |  |
| readyFrac | progress\_ready\_to\_fire\_frac |  |
| regenRate | "eWeaponVar.regen\_ammo\_refill\_rate" |  |
| smartFov | "eWeaponVar.smart\_ammo\_search\_angle" |  |
| teamColor | crosshair\_team\_color |  |

More argument information on this page

{% page-ref page="../" %}

### Config文件名

List of the different weapon config files. Sometimes names are not the same as in game name.

{% page-ref page="../../../game-values/file-location/weapon-config-file-name.md" %}

## 重新打包

[How to repack VPK files proprely?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

