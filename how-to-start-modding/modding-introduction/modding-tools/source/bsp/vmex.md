---
description: Valve Map Extractor (VMEX) is a decompiler for Source engine maps.
---

# VMEX

**Valve Map Extractor** (**VMEX**) is a decompiler for [Source](https://developer.valvesoftware.com/wiki/Source) engine maps. It converts [BSP](https://developer.valvesoftware.com/wiki/BSP) format files back into [VMF](https://developer.valvesoftware.com/wiki/VMF) format maps that can be loaded into [Hammer](https://developer.valvesoftware.com/wiki/Hammer). Since version 0.98g it supports all of Valve's games up to Left 4 Dead.

{% hint style="info" %}
**Note:**Decompiling maps with VMEX may not always result in 100% accurate builds. Some differences (keyvalues, materials, etc) may not be an exact match as the original map.
{% endhint %}

## The Ship

To decompile maps for [The Ship](https://developer.valvesoftware.com/wiki/The\_Ship), download the modified version: VMEX (v0.98e) [here](http://www.bagthorpe.org/bob/cofrdrbob/files/vmex-098e-ts.zip).

### Left 4 Dead

A modified version of vmex was created for decompiling [Left 4 Dead](https://developer.valvesoftware.com/wiki/Left\_4\_Dead) maps by [TerabyteDragon](https://developer.valvesoftware.com/wiki/User:TerabyteDragon) with permission by the original author. This modification resolves an issue with static props (specifically how large the entries are in the BSP file). This version can be downloaded from the link below. Note: This version of vmex is NOT guaranteed to work with maps from any other game.

### Left 4 Dead 2

A pre-processor to modify [Left 4 Dead 2](https://developer.valvesoftware.com/wiki/Left\_4\_Dead\_2) BSPs to be decompilable by VMEX written by [Omnicoder](https://developer.valvesoftware.com/wiki/User:Omnicoder) can be downloaded below.

### Windows Vista Java fix

The current VMEx version (098g) does not work with Windows Vista until you manually set the environmental variable path for Java. (The application will refuse to open, and if you run it from a command prompt, you will also get the error message "Java is not recognized as an internal or external command".)

To set the path, follow these steps:

1. Locate the Java executable (`Java.exe`) and make a note of where it is located. It should be either in `C:\Program Files\Java\jre6\bin` (on 32 bit Windows) or in `C:\Program Files (x86)\Java\jre6\bin` (on 64 bit Windows). Remember this path. (If you are unable to locate a Java executable, this might mean that Java (Runtime Environment) is not even installed on your computer. If not, go to [Javas official site](http://www.java.com/) to download and install it.)
2. Click on the Start icon in the lower left corner, then Control Panel, then System, and then System again.
3. Click on the Advanced System Settings link on the left.
4. Under the current tab, click the Environment Variables button.
5. In the lower section (labeled System Variables), scroll through and find the item labeled Path and double-click it to edit it.
6. In the field labeled Variable value, go to the end of the long line, and add a semicolon (;), and then the previously mentioned path of Java.exe (either `C:\Program Files\Java\jre6\bin` or `C:\Program Files (x86)\Java\jre6\bin`).

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/VMEX](https://developer.valvesoftware.com/wiki/VMEX)
{% endhint %}
