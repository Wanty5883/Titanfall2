---
description: 删除新闻和聚焦部分以获得更简洁的菜单
---

# 新闻和聚焦

![&#x4E3B;&#x83DC;&#x5355;&#x7684;&#x5C4F;&#x5E55;&#x622A;&#x56FE;&#x663E;&#x793A;&#x4E86;&#x4EC0;&#x4E48;&#x662F;&#x65B0;&#x95FB;&#x548C;&#x805A;&#x7126;&#x7684;&#x90E8;&#x5206;](../../../.gitbook/assets/snapshot0023.jpg)

## 工具

你需要到这些:

* [Titanfall VPK Tool](../../../how-to-start-modding/modding-introduction/modding-tools/)
* [VPK renamer / move \(Optional\)](../../../how-to-start-modding/modding-introduction/modding-tools/)

## 新闻

在主界面的右上角有一个UI元素，展示了游戏的更新内容。UI元素的资源位于我们无法修改的游戏**rpack**文件中，但是我们可以删除它，因为游戏不再会有更新。。。

为了删除UI元素，你需要解包`englishclient_frontend.bsp.pak000_dir.vpk` ，并编辑 `\resource\ui\menus\panels\mainmenu.res`文件。

在文件中找到 `WhatsNew` 部分代码块

```text
WhatsNew
    {
        ControlName				RuiPanel
        ypos					380
        wide					740
        tall					125
        rui                     "ui/whats_new.rpak"
        visible					1

        pin_to_sibling			PinFrame
        pin_corner_to_sibling	TOP_RIGHT
        pin_to_sibling_corner	TOP_RIGHT
    }
```

设置visible为0:

```text
visible					0
```

你现在可以重新打包VPK，你将不再看到**新闻**UI元素。

## 聚焦

在主菜单右侧，你将看到3个UI元素组合在一起：

* News - Frontier News Network: Operation Endeavor
* Rendy Gaming fires away in his Kraber G100 Montage.
* Check out the latest weapon skins

为了删除这些UI元素，你需要解包 `englishclient_frontend.bsp.pak000_dir.vpk` ，并编辑 `\resource\ui\menus\panels\spotlight.res`文件。

此文件中有3个代码块部分需要修改：

* `SpotlightLarge`
* `SpotlightSmall0`
* `SpotlightSmall1`

为了隐藏UI元素，请把 `visible` 都设置为0。

```text
visible					0
```

你现在可以重新打包VPK，你将不再看到聚焦的UI元素。

![&#x4E3B;&#x83DC;&#x5355;&#x7684;&#x5C4F;&#x5E55;&#x622A;&#x56FE;&#xFF0C;&#x65B0;&#x95FB;&#x548C;&#x805A;&#x7126;&#x90FD;&#x5DF2;&#x5220;&#x9664;](../../../.gitbook/assets/snapshot0022.jpg)

