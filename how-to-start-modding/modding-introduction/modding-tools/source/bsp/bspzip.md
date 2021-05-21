---
description: BSPZIP 是一个命令行文件，它允许你在BSP中嵌入任意文件。当地图被加载时，对应添加的文件也会被加载，相当于把文件添加到了游戏的实际文件夹。
---

# BSPZIP

**BSPZIP** 是一个[命令行工具](https://developer.valvesoftware.com/wiki/Command-line)，它允许你在[BSP](https://developer.valvesoftware.com/wiki/BSP)中嵌入任意文件。当地图被加载时，对应添加的文件也会被加载，相当于把文件添加到了游戏的实际文件夹。

{% hint style="info" %}
**提示：**用一些 [GUI工具](https://developer.valvesoftware.com/wiki/BSPZIP#GUIs_.2F_Replacements)创建可能比直接用BSPZIP要来的方便。
{% endhint %}

{% hint style="info" %}
**提示：**可以通过支持.zip的解包工具打开BSP并查看里面的内容。
{% endhint %}

虽然拿BSPZIP解包是可行的，但是有时候它会出现问题，或者根本不起作用 （比如说：[地图列表缩略图](https://developer.valvesoftware.com/wiki/Maplist_Thumbnails)）。当这种情况发生时，可以用[资源列表](https://developer.valvesoftware.com/wiki/Resource_list)代替

## Usage

{% hint style="info" %}
**Note:**Remember to set the appropriate [VPROJECT](https://developer.valvesoftware.com/wiki/VPROJECT) before starting to use the tool.
{% endhint %}

BSPZIP is found at `"common\<gamename>\<gamefolder>\bin\bspzip.exe"`. It performs several functions:

### Adding a list of files

The most common function. There are two related commands:

```text
-addlist <input bsp> <file list> <output bsp>
-addorupdatelist <input bsp> <file list> <output bsp>
```

Include file extensions. The former command packs all files in the list, the latter \(untested, Orange Box only\) packs only those that have changed since the last operation.

{% hint style="info" %}
 **Tip:**The input and output files can be the same.
{% endhint %}

The 'file list' is a .txt file containing this pattern:

```text
internal_path\file1
external_path\file1
internal_path\file2
external_path\file2
...
```

* Internal paths \('relative paths'\) are the location the file will take within the BSP, e.g. `materials/metal/new_steel.vmt`.
* External paths \('full paths'\) are the location of the file to be packed, e.g. `C:\Users\Public\our_maps\materials\metal\new_steel.vmt`.

### Adding a single file

The same principle as above, but without a file list.

```text
-addfile <input bsp> <internal path> <external path> <output bsp>
```

### Viewing and extracting files

If you have an archive tool installed that is able to look inside BSPs it's better to use that. If you don't, these are the commands you need:

```text
-extract <bsp file> <output.zip>
-extractfiles <bsp file>
-dir <bsp file>
```

### Handling cubemaps

Should be self-evident:

```text
-extractcubemaps <bsp file> <output folder>
-deletecubemaps <bsp file>
```

{% hint style="danger" %}
-deletecubemaps actually deletes all .vtf files in the .bsp - handle with caution!
{% endhint %}

## Testing

There are situations where files won't be loaded from BSP files correctly. As time goes on they become fewer in number, but it's always worth checking regardless. The easiest way to do so is moving all of the embedded content out of the game's folders -- or even better, not storing it there in the first place.

## Repacking

Repacking allows you to compress your map to save hard drive space and download times. To repack a map and compress it, these commands are used:

```text
-repack -compress <bsp file>
```

To uncompress repacked maps, run the same command but ommit the `-compress` command:

```text
-repack <bsp file>
```

{% hint style="danger" %}
 Repacked maps won't work in [Source Filmmaker](https://developer.valvesoftware.com/wiki/Source_Filmmaker) and will crash the program on load!
{% endhint %}

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/BSPZIP](https://developer.valvesoftware.com/wiki/BSPZIP)
{% endhint %}

