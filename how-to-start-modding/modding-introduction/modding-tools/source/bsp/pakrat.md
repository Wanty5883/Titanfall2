# Pakrat

**Notice:** Pakrat does not seem to work very well with newer builds of the Source engine. See [VIDE](vide.md).

**Pakrat** is a GUI replacement for Valve's [Bspzip](bspzip.md) application.

Pakrat has the ability to scan a .[BSP](https://developer.valvesoftware.com/wiki/BSP) file for all texture, material, and model files used in the map and automatically embed custom content into the .BSP file.

{% hint style="danger" %}
Pakrat is known to corrupt files in the .bsp file if you delete and re-save packed content. For Pakrat to correctly pack your custom items, you must make sure to add everything to the .BSP file without missing anything before you save the .BSP again. Also, overwriting an existing version \(For example overwriting your currently opened map in Pakrat\) will also corrupt your files.
{% endhint %}

Pakrat is known to corrupt navigation files as well, so include those separately.

{% hint style="info" %}
**Tip:**If adding a .nav to the .bsp, do not allow it to automatically fix-up the .nav file. [Demonstration](http://youtu.be/nRqfv8Cmc9Y)
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=nRqfv8Cmc9Y" %}

{% hint style="danger" %}
 **Use at your own risk.**
{% endhint %}

![](../../../../../.gitbook/assets/pakrat1.gif)

## Usage

Pakrat is useful for packing textures and custom assets etc. into your BSP before uploading to Steam Workshop, as with [p2map\_publish](https://developer.valvesoftware.com/wiki/P2map_publish). This short how-to assumes you're working in Portal 2 for example, and you've placed your custom assets in subfolders of SteamApps/common/Portal 2/portal2/ -- in theory, this process would be the same for CS:GO or whatever, just use the main path to CS:GO instead.

1. Download Pakrat and unzip it to somewhere on your computer.
2. In Hammer, compile your map as usual. Also build the [cubemaps](https://developer.valvesoftware.com/wiki/Cubemaps) in-game if you have to. Once we pack our files with Pakrat, we won't want to mess with the BSP file again, since Pakrat will often corrupt the map file if you try to re-pack the same files again.
3. In Pakrat, load your BSP.
4. In Pakrat, File &gt;&gt; Preferences, and configure the "game root" directory by browsing to your \portal2\ folder... so the full path should look something like "...Steam/SteamApps/common/Portal 2/portal2/"
5. In Pakrat, now click "Auto" and add the files it detects. If you want to see what it's really doing, click "Scan" instead -- it is looking in the "game root" directory for file paths it detected in your BSP. It will fail to find any files that already come with the game \(e.g. packed in VPKs\) which is good, because you only want to distribute your custom content.
6. In Pakrat, make sure you save and overwrite the BSP with the same filename, or else it will break your cubemaps.

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Pakrat](https://developer.valvesoftware.com/wiki/Pakrat)
{% endhint %}

