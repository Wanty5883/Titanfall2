---
description: >-
  Guide to changing the color of the sonar that cover your hands and weapon
  while being detected
---

# Sonar Detected

## Preparation

For this guide you will need a VPK tool and a text editor.

{% content-ref url="../../intro/duction/tools/" %}
[tools](../../intro/duction/tools/)
{% endcontent-ref %}

### Used VPK

{% hint style="success" %}
`englishclient_mp_common.bsp.pak000_dir.vpk`
{% endhint %}

## Extracting

{% content-ref url="../../intro/duction/vpk-packpack.md" %}
[vpk-packpack.md](../../intro/duction/vpk-packpack.md)
{% endcontent-ref %}

## Editing

Navigate to following location

`englishclient_mp_common.bsp.pak000_dir.vpk\scripts\vscripts\sh_highlight.gnut`

open this `.gnut` file in a text editor of your choice and look for the following line

```
global const HIGHLIGHT_COLOR_ENEMY = <1.0, 0.36, 0.12> //float3( 0.63, 0.80, 0.93 );
```

To change color, simply change values in "<1.0, 0.36, 0.12>".

### Examples

![global const HIGHLIGHT\_COLOR\_ENEMY = <0.2, 0.7, 0.9>](../../.gitbook/assets/titanfall-2-screenshot-2021.02.24-19.05.12.92.png)

## Repacking

{% content-ref url="../../intro/duction/vpk-packpack.md" %}
[vpk-packpack.md](../../intro/duction/vpk-packpack.md)
{% endcontent-ref %}
