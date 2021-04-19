---
description: 修改电能步枪变为单机剧情中电弧枪的指南。
---

# 电能步枪-电弧枪

## 使用的VPK文件

{% hint style="success" %}
* englishclient\_mp\_common.bsp.pak000\_dir.vpk
{% endhint %}

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

{% page-ref page="../../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

## 介绍

As 虽然自定义模型在泰坦陨落中还不能实现，但我们仍然可以使用游戏中已有的模型去替换模型。但是这种方法对枪械动画有一定的要求，不兼容的动画可能会产生非常奇怪的效果。

对于本指南来说，它与电能步枪的预期效果相同。

## 编辑

### 取得电弧枪模型

首先，你需要取得单机内容中的电弧枪模型；您需要从这个VPK中提取模型：

{% hint style="info" %}
* englishclient\_sp\_beacon.bsp.pak000\_dir.vpk
{% endhint %}

在本次使用VPK工具中，你不需要提取全部文件出来。只需提取你所需要的文件即可，你可以在以下路径中找到相关文件：

```text
\models\weapons\arc_tool_sp\ptpov_arc_tool_sp.mdl
```

### 替换模型

一旦你找到了电弧枪所需的模型，返回到你提取的Common VPK\(即下面的VPK\)目录中

{% hint style="success" %}
* englishclient\_mp\_common.bsp.pak000\_dir.vpk
{% endhint %}

Navigate to this location in your extracted folder

> \models\weapons\defender

This folder contains the models for the charge rifle, otherwise called defender internally. Now you have to rename `ptpov_arc_tool_sp.mdl` into `ptpov_defender.mdl`. Obviously you want to delete or rename the original file.

You can also do the same process with those two files: `w_defender.mdl` `w_defender_stow.mdl` with `w_arc_tool_sp.mdl` from the arc tool folder.

That's it ! You are done with it. Now it should work as intended as shown in the examples down bellow

### 样例

{% embed url="https://gfycat.com/cloudyshinyflies" %}

{% embed url="https://gfycat.com/alldecisivefinwhale" %}

### 重新打包

{% page-ref page="../../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

