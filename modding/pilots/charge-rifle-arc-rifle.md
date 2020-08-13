---
description: >-
  A guide to change the charge rifle for the arc tool from the single player
  content of the game.
---

# Charge Rifle - Arc Rifle

## Used VPK

{% hint style="success" %}
* englishclient\_mp\_common.bsp.pak000\_dir.vpk
{% endhint %}

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)

{% page-ref page="../../how-to-start-modding/how-to-backup-extract-and-repack.md" %}

## Introduction

As custom models are not _yet_ possible in Titanfall, we still can change models with already existing models within the game. However this method have some restrictions about animations. Animations might give really weird results.

For this guide, it works as intended with the charge rifle.

## Editing

### Get the Arc Tool model

In the first place you need to get your hands on the arc tool model. You will need to extract the model from this VPK

{% hint style="info" %}
* englishclient\_sp\_beacon.bsp.pak000\_dir.vpk
{% endhint %}

With the VPK tool you do not need to extract the entire archive, you can just extract the file you are looking for. Which you will find at this location

```text
\models\weapons\arc_tool_sp\ptpov_arc_tool_sp.mdl
```

### Swapping the models

Once you have the desired model, return to your extracted Common VPK

{% hint style="success" %}
* englishclient\_mp\_common.bsp.pak000\_dir.vpk
{% endhint %}

Navigate to this location in your extracted folder

> \models\weapons\defender

This folder contains the models for the charge rifle, otherwise called defender internally. Now you have to rename `ptpov_arc_tool_sp.mdl` into `ptpov_defender.mdl`. Obviously you want to delete or rename the original file.

You can also do the same process with those two files: `w_defender.mdl` `w_defender_stow.mdl` with `w_arc_tool_sp.mdl` from the arc tool folder.

That's it ! You are done with it. Now it should work as intended as shown in the examples down bellow

### Examples

{% embed url="https://gfycat.com/cloudyshinyflies" %}

{% embed url="https://gfycat.com/alldecisivefinwhale" %}

### Repacking

{% page-ref page="../../how-to-start-modding/how-to-backup-extract-and-repack.md" %}

