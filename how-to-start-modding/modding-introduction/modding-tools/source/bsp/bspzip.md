---
description: >-
  BSPZIP is a command-line tool that allows arbitrary files to be embedded
  within a BSP. When the map is being loaded the files will be mounted as if
  they were present in the game's real content folders
---

# BSPZIP

**BSPZIP** is a [command-line](https://developer.valvesoftware.com/wiki/Command-line) tool that allows arbitrary files to be embedded within a [BSP](https://developer.valvesoftware.com/wiki/BSP). When the map is being loaded the files will be mounted as if they were present in the game's real content folders.

{% hint style="info" %}
**Tip:**Several [GUI utilities](https://developer.valvesoftware.com/wiki/BSPZIP#GUIs\_.2F\_Replacements) have been created that may be more convenient than using BSPZIP directly.
{% endhint %}

{% hint style="info" %}
**Tip:**Embedded content can be examined with archive tools that support .zip by opening the BSP file.
{% endhint %}

While it is usually a good idea to BSPZIP content, there are times when it can cause problems and other times when it won't work at all (e.g. for [Maplist Thumbnails](https://developer.valvesoftware.com/wiki/Maplist\_Thumbnails)). When this happens a [resource list](https://developer.valvesoftware.com/wiki/Resource\_list) can be used instead.

## Usage

{% hint style="info" %}
**Note:**Remember to set the appropriate [VPROJECT](https://developer.valvesoftware.com/wiki/VPROJECT) before starting to use the tool.
{% endhint %}

BSPZIP is found at `"common\<gamename>\<gamefolder>\bin\bspzip.exe"`. It performs several functions:

### Adding a list of files

The most common function. There are two related commands:

```
-addlist <input bsp> <file list> <output bsp>
-addorupdatelist <input bsp> <file list> <output bsp>
```

Include file extensions. The former command packs all files in the list, the latter (untested, Orange Box only) packs only those that have changed since the last operation.

{% hint style="info" %}
&#x20;**Tip:**The input and output files can be the same.
{% endhint %}

The 'file list' is a .txt file containing this pattern:

```
internal_path\file1
external_path\file1
internal_path\file2
external_path\file2
...
```

* Internal paths ('relative paths') are the location the file will take within the BSP, e.g. `materials/metal/new_steel.vmt`.
* External paths ('full paths') are the location of the file to be packed, e.g. `C:\Users\Public\our_maps\materials\metal\new_steel.vmt`.

### Adding a single file

The same principle as above, but without a file list.

```
-addfile <input bsp> <internal path> <external path> <output bsp>
```

### Viewing and extracting files

If you have an archive tool installed that is able to look inside BSPs it's better to use that. If you don't, these are the commands you need:

```
-extract <bsp file> <output.zip>
-extractfiles <bsp file>
-dir <bsp file>
```

### Handling cubemaps

Should be self-evident:

```
-extractcubemaps <bsp file> <output folder>
-deletecubemaps <bsp file>
```

{% hint style="danger" %}
\-deletecubemaps actually deletes all .vtf files in the .bsp - handle with caution!
{% endhint %}

## Testing

There are situations where files won't be loaded from BSP files correctly. As time goes on they become fewer in number, but it's always worth checking regardless. The easiest way to do so is moving all of the embedded content out of the game's folders -- or even better, not storing it there in the first place.

## Repacking

Repacking allows you to compress your map to save hard drive space and download times. To repack a map and compress it, these commands are used:

```
-repack -compress <bsp file>
```

To uncompress repacked maps, run the same command but ommit the `-compress` command:

```
-repack <bsp file>
```

{% hint style="danger" %}
&#x20;Repacked maps won't work in [Source Filmmaker](https://developer.valvesoftware.com/wiki/Source\_Filmmaker) and will crash the program on load!
{% endhint %}

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/BSPZIP](https://developer.valvesoftware.com/wiki/BSPZIP)
{% endhint %}
