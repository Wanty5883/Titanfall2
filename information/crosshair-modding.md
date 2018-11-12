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

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://wanty5883.gitbook.io/titanfall2/information/modding-tools)

## Unpacking

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

[How to extract VPK's properly ?](https://wanty5883.gitbook.io/titanfall2/how-to-start-modding/2.-how-to-backup-extract-and-repack)

## Editing

Go to this location in your extracted folder

> \scripts\weapons

This folder containt the "config files" for the weapons. Edit those files at your own risk, if you get banned because you edit some important value don’t blame me.

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

### Crosshair example

![](https://camo.githubusercontent.com/1125e7858f23efb84e1713972512832d14857f83/687474703a2f2f7777772e6e6f736b696c6c2e65752f77702d636f6e74656e742f75706c6f6164732f323031372f30392f546974616e66616c6c2d322d30392e30322e323031372d32312e32342e33302e30322d31303234783537362e706e67)![](https://camo.githubusercontent.com/1b053f7b04d946910e84441d3bd78496721f197f/687474703a2f2f7777772e6e6f736b696c6c2e65752f77702d636f6e74656e742f75706c6f6164732f323031372f30392f546974616e66616c6c2d322d30392e30322e323031372d32312e32352e35302e30352d31303234783537362e706e67)![](https://camo.githubusercontent.com/6ae6b84445e47a4d68f9028169521e6689ad9791/687474703a2f2f7777772e6e6f736b696c6c2e65752f77702d636f6e74656e742f75706c6f6164732f323031372f30392f546974616e66616c6c2d322d30392e30322e323031372d32312e32352e31342e30342d31303234783537362e706e67)![](https://camo.githubusercontent.com/efb0ca5c2b27fdb621a2c3e06f69160a49513331/687474703a2f2f7777772e6e6f736b696c6c2e65752f77702d636f6e74656e742f75706c6f6164732f323031372f30392f546974616e66616c6c2d322d30392e30322e323031372d32312e32372e35332e30362d31303234783537362e706e67)

### Crosshair value

[Here](https://wanty5883.gitbook.io/titanfall2/information/weapon-config-info#ui-crosshair)

### Config file name

[Here](https://wanty5883.gitbook.io/titanfall2/information/weapon-config-info#file-location)

### My sample

Here is a list of what I'm using personally. You can have a preview in the screenshots above [here](https://github.com/Wanty5883/Titanfall2/wiki/Crosshair/_edit#crosshair-example). This table is wider than the page itself, must scroll to the right side.

| Weapon | Crosshair1 | Speard | Crosshair2 | Speard | Crosshair3 | Spread |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **AR** |  |  |  |  |  |  |
| Carbine | ui/crosshair\_plus | 0.0 | ui/crosshair\_wingman\_n | 0.0 | ui/crosshair\_alternator | 0.0 |
| G2A5 | ui/crosshair\_plus | -2.0 | ui/crosshair\_wingman\_n | 0.0 | ui/crosshair\_alternator | 0.0 |
| Hemlock | ui/crosshair\_plus | -2.0 | ui/crosshair\_wingman\_n | 0.0 | ui/crosshair\_alternator | 0.0 |
| Flatline | ui/crosshair\_alternator | 1.5 | ui/crosshair\_plus | 0.0 | ui/crosschair\_plus | 0.0 |
| **SMG** |  |  |  |  |  |  |
| Alternator | ui/crosshair\_plus | 1.0 | ui/crosshair\_shotgun | 2.0 | ui/crosshair\_wingman\_n | 0.0 |
| CAR | ui/crosshair\_plus | 0.0 | ui/crosshair\_lstar | 1.5 | ui/crosshair\_wingman\_n | 0.0 |
| R97 | ui/crosshair\_plus | 0.0 | ui/crosshair\_shotgun | 0.5 | ui/crosshair\_wingman\_n | 0.0 |
| Volt | ui/crosshair\_plus | 2.0 | ui/crosshair\_lstar | 1.5 | ui/crosshair\_wingman\_n | 0.0 |
| **Shotgun** |  |  |  |  |  |  |
| EVA 8 Auto | ui/crosshair\_shotgun | -4.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Mastiff | ui/crosshair\_mastiff | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| **Sniper** |  |  |  |  |  |  |
| Kraber | ui/crosshair\_wingman\_n | 0.0 |  |  |  |  |
| DMR | ui/crosshair\_wingman\_n | 0.0 |  |  |  |  |
| Double Take | ui/crosshair\_wingman\_n | 0.0 |  |  |  |  |
| **LMG** |  |  |  |  |  |  |
| Spitfire | ui/crosshair\_plus | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Devotion | ui/crosshair\_plus | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| LTAR | ui/crosshair\_lstar | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| **Grenadier** |  |  |  |  |  |  |
| Sidewinder | ui/crosshair\_flight\_core | 5.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| **Pistol** |  |  |  |  |  |  |
| RE-45 | ui/crosshair\_plus | -2.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Wingman | ui/crosshair\_plus | -0.25 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Wingman Elite | ui/crosshair\_plus | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| P2K16 | ui/crosshair\_plus | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| **Anti Titan** |  |  |  |  |  |  |
| Thunderbolt | ui/crosshair\_esmoke | 0.0 |  |  |  |  |
| Archer | ui/crosshair\_esmoke | 0.0 |  |  |  |  |
| **Titan Weapon** |  |  |  |  |  |  |
| Northstar | ui/crosshair\_charge\_rifle | 10.0 | ui/crosshair\_circle2\_small | 0.0 |  |  |
| Ion | ui/crosshair\_ion | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Tone | ui/crosshair\_40mm | 0.0 | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Monarch | ui/crosshair\_plus | -0.5 | ui/crosshair\_shotgun | 0.0 | ui/crosshair\_wingman\_n | 0.0 |
| **Titan Core** |  |  |  |  |  |  |
| Northstar | ui/crosshair\_tracker\_rockets | 0.0 |  |  |  |  |
| Ion | ui/crosshair\_circle2\_small | 0.0. | ui/crosshair\_wingman\_n | 0.0 |  |  |
| Ronin | ui/crosshair\_esmoke | 0.0 |  |  |  |  |
| **Titan offensive** |  |  |  |  |  |  |
| Northstar | ui/crosshair\_circle2 | 0.0 |  |  |  |  |

## Repacking

[How to repack VPK files proprely?](https://wanty5883.gitbook.io/titanfall2/how-to-start-modding/2.-how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

