---
description: 如何一次性将几乎所有的武器换成同样的准星。
---

# 批量修改准星

## 前期准备

本指南要求您了解修改指南中概述的基础知识、如何备份、提取和重新打包以及修改工具。如果您不理解这些概念，请点击下面的文章链接：

{% page-ref page="../../../how-to-start-modding/modding-introduction/" %}

本指南还要求您下载一个名为TextCrawler 3的软件。软件可以在[这里](https://www.digitalvolcano.co.uk/tcdownloads.html)找到。 任何其他能够基于正则表达式进行批量修改的程序也可以做同样的事情。在“修改工具”页面中可以找到其他必需的工具：

{% page-ref page="../../../how-to-start-modding/modding-introduction/modding-tools/" %}

本指南只支持Windows10，很抱歉我们不会为其他操作系统提供扩展支持。

## 指南

### 第一步. 单独放置要修改的文件

Create a folder for yourself to perform these edits within, mine is called `CrosshairMods`. Place the config files for weapons you'd like to modify. We don't recommend setting titan weapons to all the same, as most of these have alternate states and etc not friendly to static, stock crosshairs. Once this folder is created and it contains your config files move on to the next step.

### 第二步. 打开TextCrawler，然后修改设置。

![](../../../.gitbook/assets/image%20%284%29%20%281%29.png)

This step consists of 5 parts, listed below.

1. Slap the path to that folder containing configs you made before into this box
2. Select the "Regular Expression" tab.
3. Change the "Rex Ex:" box to `ui/crosshair_\w+` this filters for all strings beginning with `ui/crosshair_` and stops the selection at the end of the "word" \(section of text with no spaces\)
4. Set the "Replace:" box to the full id of the crosshair you would like to make your base.
5. Click "Find"

### 第三步. 检验设置是否正常工作

![](../../../.gitbook/assets/image%20%283%29.png)

If all is done correctly, you should see a list of your configs appear with the crosshair settings within them highlighted. Make sure that all of your configs have the "Matches" column value of 1. If this is not the case you will have to manually modify as these configs have multiple overlaid crosshairs.

### 第四步.批量更改配置文件

If all is to your satisfaction, click the "Replace" button, and confirm your choice in the popup.

### 第五步. 清理文件夹和配置文件

Open up a config, and verify that the change has gone through, and delete all the `.bak` files created during your edit. Once finished, move all of your configs back into your scripts/weapons folder and repack.

## 脚注

如果你不恰当地使用这个程序把事情搞砸了，那是你的问题，不是我们的问题。如果本指南有任何错误，请在Discord服务器中标记`@Frontier Militia`来提醒我们查看并关注您的建议。

{% page-ref page="../../../" %}

