---
description: Guide to change  crosshair
---

# Crosshair modding

## Preparation

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)

## Unpacking

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

## Editing

Go to this location in your extracted folder

> \scripts\weapons

This folder contains the "config files" for the weapons. Edit those files at your own risk, if you get banned because you edit some important value don’t blame me.

Find that code block to get where is the crosshair code part.

```text
active_crosshair_count                      “1”
rui_crosshair_index                         “0”

RUI_CrosshairData
```

From this part to the bottom of the _`RUI_CrosshairData`_ bracket that's the part that we will edit together ! \(finally getting into the interesting part !\)

To change the crosshair, you have to change the _`ui`_ with the one you want. You can find the value for the different crosshair in the game down bellow.

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

Don't copy paste the value from this example, use the one you have in the edited file! Note that is also important to change that value to the amount of crosshair you want to combine `active_crosshair_count "2"`.

You can change the _`base_spread`_ value to change the based size of the crosshair, this won't change the vector size but the distance between the center of the screen and the different parts of the crosshair. You can use positive or negative values

### Crosshair value

[Here](https://noskill.gitbook.io/titanfall2/information/weapon-config-info#ui-crosshair)

### RUI\_CrosshairData & Arguments

Args or arguments can change how the crosshair is acting

| Argument | Value | Note |
| :--- | :--- | :--- |
| adjustedSpread | weapon\_spread |  |
| adsFrac  | player\_zoomFrac |  |
| isSprinting  | player\_is\_sprinting |  |
| isReloading  | weapon\_is\_reloading |  |
| readyFrac  | progress\_ready\_to\_fire\_frac |  |
| teamColor  | crosshair\_team\_color |  |
| isAmped  | weapon\_is\_amped |  |
| chargeFrac  | player\_chargeFrac |  |
| crosshairMovementX  | crosshair\_movement\_x |  |
| crosshairMovementY  | crosshair\_movement\_y |  |
| isActive  | weapon\_is\_active |  |
| clipAmmo  | weapon\_ammo |  |
| chargeLevel  | player\_chargeLevel |  |
| clipSize  | weapon\_clipSize |  |
| isFiring  | weapon\_is\_firing |  |
| chargeStartTime  | weapon\_script\_time\_0 |  |
| chargeMaxTime  | eWeaponVar.custom\_float\_0 |  |
| ammoFrac  | "progress\_grapple\_power" |  |
| isGrappleInRange  | "grapple\_in\_range" |  |
| ammoFrac  | "progress\_weapon\_clip\_ammo\_frac" |  |
| dryfireTime  | "weapon\_latest\_dryfire\_time" |  |
| dryfireTime  | "weapon\_latest\_dryfire\_time" |  |
| regenRate  | "eWeaponVar.regen\_ammo\_refill\_rate" |  |
| isLocked  | smartammo\_locked |  |
| smartFov  | "eWeaponVar.smart\_ammo\_search\_angle" |  |

### Config file name

[Here](https://noskill.gitbook.io/titanfall2/information/file-location)

## Repacking

[How to repack VPK files proprely?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

