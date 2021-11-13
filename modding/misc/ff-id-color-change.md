---
description: >-
  This is how to change the Identification color of Titanfall 2 which includes
  pilot glow and titan glow.
---

# FF ID Color change

Pilot glow: Any light that is emitted from the pilot. ie: Visor color and jumpkit color.

Titan glow: Any light that is emitted from the titan. ie: Eye color and thruster color.

### Walkthrough:

1. Go to the path Titanfall2/bin/x64\_retail
2. Backup the file "Client.dll"
3. Open the file "Client.dll" in a hexeditor and go to the offset 0090FAA0

These are the values you want to change.  Values: R G B

![](<../../.gitbook/assets/Base Id color offset.png>)

{% hint style="info" %}
Before converting your color to hex:&#x20;

RGB values are written in vectors where 0 is a minimum value and 1 is max (255 in regular format). If you're not familiar with this format, check [**Color & Texture info**](../../documentation/textures/colors/color-and-texture-info.md#usdlayercolor)** **page.
{% endhint %}

#### Example values for one color:

| **HEX value**       | 302E303020302E373320302E3733 |
| ------------------- | ---------------------------- |
| **Vector value**    | 0.00 0.73 0.73               |
| **Plain RGB value** | 0 185 185                    |



#### Original values for all id colors.&#x20;

![](<../../.gitbook/assets/Original Id color values.png>)
