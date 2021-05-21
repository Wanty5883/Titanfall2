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

## 使用

{% hint style="info" %}
**注解：**别忘了在使用工具之前设置适当的[VPROJECT](https://developer.valvesoftware.com/wiki/VPROJECT)。。
{% endhint %}

BSPZIP可以在`"common\<gamename>\<gamefolder>\bin\bspzip.exe"`路径中被发现。它具有以下的功能：

### 添加一个文件列表

这是最常见的功能。这里有两个相关的命令：

```text
-addlist <input bsp> <file list> <output bsp>
-addorupdatelist <input bsp> <file list> <output bsp>
```

这些命令包含文件的扩展名。前一个命令负责打包列表中所有的文件，后一个命令（未测试，暂时仅限半条命2橙盒版）只打包自上次操作以来更改的文件。

{% hint style="info" %}
 **提示：**输入和输出的文件可能会相同。
{% endhint %}

‘file list’（文件列表）是一个包含以下语句的.txt文件：

```text
internal_path\file1
external_path\file1
internal_path\file2
external_path\file2
...
```

* 内部路径（Internal paths  '相关路径'）是文件在BSP中的路径，比如说： `materials/metal/new_steel.vmt。`
* 外部路径（External paths '全部路径'）是要打包的文件的路径，比如说： `C:\Users\Public\our_maps\materials\metal\new_steel.vmt`.

### 添加单个文件

与上面的原理相同，但是没有文件列表：

```text
-addfile <input bsp> <internal path> <external path> <output bsp>
```

### 查看和导出文件

如果你安装了一个可以查看bsp内部文件的工具，那么你最好选择使用此工具。如果你还是选择使用BSPZIP，你可能需要以下的一些命令：

```text
-extract <bsp file> <output.zip>
-extractfiles <bsp file>
-dir <bsp file>
```

### 处理立方体贴图（cubemap）

同上，不用多说：

```text
-extractcubemaps <bsp file> <output folder>
-deletecubemaps <bsp file>
```

{% hint style="danger" %}
-deletecubemaps 命令一般用来删除.bsp中所有的.vtf 文件 -  请谨慎使用！
{% endhint %}

## 测试

一些情况下，文件是无法从BSP中被加载的。随着时间的推移和技术的进步，它们的数量将会越来越少。当然，无论如何，使用前测试一下总是没有坏处的。最简单的方法就是将所有bsp内的文件移出游戏文件夹 ，更棒的方法是不再将其存储在原此位置。

## 重新打包

重新打包可以使你压缩你的地图，以节省硬盘驱动器的空间和下载时间。你可以通过以下命令来重打包或者压缩地图：

```text
-repack -compress <bsp file>
```

要解压缩重打包的地图，你需要在执行一遍同样命令的情况下，再提交`-compress` 命令：

```text
-repack <bsp file>
```

{% hint style="danger" %}
 在[Source Filmmaker](https://developer.valvesoftware.com/wiki/Source_Filmmaker)中重新打包的地图不会正常工作并且会引起程序的崩溃！
{% endhint %}

{% hint style="info" %}
源文档连接： [https://developer.valvesoftware.com/wiki/BSPZIP](https://developer.valvesoftware.com/wiki/BSPZIP)
{% endhint %}

