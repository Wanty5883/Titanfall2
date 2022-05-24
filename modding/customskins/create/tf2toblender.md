---
description: This is going to take a lot of work omega lol.
---

# Getting a Model into Blender

## This is new.

This is a experimental Documentation/Video Mix concept. This is designed to provide the follow along/depth that a video can provide and the detail/explain-ability that a wiki/document can provide.

Yes this is like Khan Academy. Give me feedback on this idea. I wish this would become a sort of video hoster concept. Maybe, if this is a success.

## Prerequisites:&#x20;

### Required Tools:

On a separate tab head to:

{% content-ref url="../../../how-to-start-modding/modding-introduction/modding-tools/" %}
[modding-tools](../../../how-to-start-modding/modding-introduction/modding-tools/)
{% endcontent-ref %}

#### Download these tools from each category.&#x20;

### Titanfall

* Titanfall VPK Tool
* Legion
* Legion+

### 3D Models

* Blender
  * Blender Source Tool
  * S/G Shader

#### You should have 6 tools/files.&#x20;

1. `blender_source_tools_3.2.2.zip`
2. `blender-x.x.x-windows-x64.msi`
3. `Legion+x.x.x.zip`
4. `LegionReleasev2.43.zip`
5. `SG_Shader.blend`
6. `Titanfall_VPKTool3.4_Portable.zip`

{% hint style="info" %}
Don't unpack `blender_source_tools_3.2.2.zip. You don't need to. If you do. Don't worry just delete the unpacked folder.`
{% endhint %}

## Timeline:

### 0:00 - 0:53   Downloading Files/Tools

Downloading all required tools and files (the prerequisites listed above).&#x20;

### 0:55 - 1:03   Unpack the Files

Expecting you to unpack the file yourself lol.

### 1:21 - 1:43   VPKTool - Open VPK

On the top left of the VPKTool. Press the first icon to 'Open' and choose a VPK. You are looking for `englishclient_mp_common.bsp.pak000_dir.vpk` .&#x20;

### 1:46 - 2:08   VPKTool - Extract VPK

Click the second to last icon from left to right on the top left of the VPKTool. This is the 'Extract All' button if you just hover over it. Extract everything into a seperate folder (like i did).

{% hint style="info" %}
Don't forget to close out of your open VPK when exiting VPKTool.
{% endhint %}

### 2:20 - 3:14   Organizing Tools

Organizing tools because i'm better than you.

### 3:16 - 3:55   Legion - Settings SMD

Bottom right on Legion press the red outlined 'Settings' button to Change the 'Export Format' to 'Valve SMD'.

### 4:00 - 4:45   Legion - Converting .mdl

Find your desired model and drag & drop onto Legion (after pressing and opening the 'Titanfall 2' button.

### 4:50 - 5:16   Legion+ - Locate common.rpak&#x20;

A LOT of texture assets are in "common.rpak". This is the one i need for the mgl though. If you cannot find your textures using the search functions, try opening rpaks and starpaks `camo_skin00_col.rpak` through `common_sp(11).rpak` . You can open multiple at a time; I found myself only to open 50\~60 at a time with Legion+ though.

### 5:22 - 6:00   Legion+ - Find/Extract Textures

Using the search function on the top left. Search your weapons names, script names, beta name, or something like that. What to download? The skin31 textures are the 'same' as the regular textures as far as i can tell. So just download everything that has a standard name alongside a texture map extension. Much like

* `mgl_at`
* `mgl_at_ao`
* `mgl_at_cav`
* `mgl_at_col`
* `mgl_at_gls`
* `mgl_at_nml`

See how they sort of have a pattern? These are enough to fully texture the gun in Blender.
