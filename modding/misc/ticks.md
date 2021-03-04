---
description: Change the look of your Multiplayer Ticks
---

# Ticks - Model

## Results

{% embed url="https://gfycat.com/regalshrilldaddylonglegs" %}

## Preparation <a id="preparation"></a>

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

## Editing

To modify the tick model to look like the one in Single player, you will need to locate two separate file locations and 4 files total

Open these locations: 

> models\robots\drone\_frag
>
> models\weapons\sentry\_frag

The **drone\_frag** file is the Single player tick while the **sentry frag** is the multiplayer tick.

First you will need to rename the two single player tick file names to the multiplayer ones.

> drone\_frag.mdl ---- **&gt;**   sentry\_frag.mdl
>
> frag\_drone\_proj.mdl ----**&gt;**   sentry\_frag\_proj.mdl

Once you have renamed the files of the Singleplayer drones, you will need to copy and paste them to the multiplayer folder. Copy and Paste your renamed files \(sentry\_frag.mdl and sentry\_frag\_proj.mdl\) to:

> models\weapons\sentry\_frag

You will then want to replace your files with the ones already there, once that is done you can close out and proceed to the next step.

## Repacking <a id="repacking"></a>

​[How to repack VPK files proprely ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\







