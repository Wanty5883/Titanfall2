---
description: >-
  Windows BSP Converter ("WinBSPC") is a utility used to recreate .map files for
  Goldsource BSP files.
---

# WinBSPC

Windows BSP Converter \("**WinBSPC**"\) is a utility used to recreate .map files for [Goldsource](https://developer.valvesoftware.com/wiki/Goldsource) [BSP](https://developer.valvesoftware.com/wiki/BSP) files. Results vary depending on the complexity of a given map.

To create an output file, WinBSPC converts the map into a single solid brush and carves out the geometry it finds in the BSP. The end result is a moderately acceptable brushwork, comparable to other decompilers such as [BSP2MAP](bsp2map.md), with a comparison available below.

![WinBSPC after opening](../../../../../.gitbook/assets/winbspc.jpg)

![WinBSPC&apos;s attempt to decompile HL crossfire.](../../../../../.gitbook/assets/crossfire_winbspc.png)

![BSP2MAP&apos;s attempt to decompile HL crossfire.](../../../../../.gitbook/assets/crossfire_bsp2map.png)

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/WinBSPC](https://developer.valvesoftware.com/wiki/WinBSPC)
{% endhint %}

