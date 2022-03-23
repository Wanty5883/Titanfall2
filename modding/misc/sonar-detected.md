---
description: >-
  Guide to changing the color of the sonar that cover your hands and weapon
  while being detected
---

# Sonar Detected

## Preparation

For this guide you will need a VPK tool and a text editor.

{% page-ref page="../../how-to-start-modding/modding-introduction/modding-tools/" %}

### Used VPK

{% hint style="success" %}
`englishclient_mp_common.bsp.pak000_dir.vpk`
{% endhint %}

## Extracting

{% page-ref page="../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

## Editing

Navigate to following location

`englishclient_mp_common.bsp.pak000_dir.vpk\scripts\vscripts\sh_highlight.gnut`

open this `.gnut` file in a text editor of your choice and look for the following line

```text
global const HIGHLIGHT_COLOR_ENEMY = <1.0, 0.36, 0.12> //float3( 0.63, 0.80, 0.93 );
```

To change color, simply change values in "&lt;1.0, 0.36, 0.12&gt;".

### Examples

![global const HIGHLIGHT\_COLOR\_ENEMY = &amp;lt;0.2, 0.7, 0.9&amp;gt;](../../.gitbook/assets/titanfall-2-screenshot-2021.02.24-19.05.12.92.png)

## Repacking

{% page-ref page="../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

