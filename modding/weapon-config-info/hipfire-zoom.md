---
description: Change your FOV with the click of a button.
---

# Hipfire zoom

## Preparation

In this guide you will have to edit a config file, otherwise known as `.cfg` file. Please be aware that you will need to create an `autoexec.cfg`file in `Origin Games\Titanfall2\r2\cfg\` if you do not have one.\
\
Navigate to your folder and find your `autoexec.cfg` file:&#x20;

> Origin Games\Titanfall2\r2\cfg\\

Or:

> Steam\steamapps\common\Titanfall2\r2\cfg\\

Open it in your text editor of choice.

{% hint style="info" %}
You can use a different name for your config file, but you will need to use a command to execute it.
{% endhint %}

## Introduction

Source Engine games handle magnification when aiming down sights by changing the FOV to a smaller number, which creates the effect of magnification. \
This guide will teach you how to apply this effect to your hipfire view. We can achieve this by binding a key to cycle between multiple FOVs.

## Editing

Open your `autoexec.cfg` in your text editor and type in the following lines.

```
bind "MOUSE4" fovtoggle
	alias fovtoggle "fov1"
		alias "fov1" "cl_fovScale 1.0; alias fovtoggle fov2"
		alias "fov2" "cl_fovScale 1.6875; alias fovtoggle fov1"
```

Note that `cl_fovScale` values below 1.0 will default to 1.0.

I bound my FOV toggle to "MOUSE4", you can bind it to any button you'd like.\
\
This will toggle between`cl_fovScale 1.6875 (118.125 FOV)`and `cl_fovScale 1.0 (70 FOV).`\
However you will not have sensitivity scaling so when zooming in your mouse movement, much like your image, will be magnified.\
\
To have your sensitivity scale properly with your zoom you will need to divide your sensitivity value by the amount that you are zooming in (in my case that value is `1.6875 / 1.0 = 1.6875`), in this case the zoomed in sensitivity is `3.848 / 1.6875 = 2.2802962963`.\
\
Now add the proper sensitivity values to `"fov1"` and `"fov2"`

```
bind "MOUSE4" fovtoggle
	alias fovtoggle "fov1"
		alias "fov1" "cl_fovScale 1.0; alias fovtoggle fov2; m_sensitivity 2.2802962963"
		alias "fov2" "cl_fovScale 1.6875; alias fovtoggle fov1; m_sensitivity 3.848"
```

This will ensure that the mouse movement is not magnified and feels the same as it would when zoomed out.

## Examples

{% embed url="https://gfycat.com/vaguedazzlingbackswimmer" %}

{% embed url="https://gfycat.com/sizzlingunfitasiansmallclawedotter" %}

![EVA-8 zoomed in (70 FOV)](../../.gitbook/assets/titanfall2\_pcjd3nma5s.jpg)

![EVA-8 zoomed out (118.125 FOV)](../../.gitbook/assets/titanfall2\_gsvomi4dfk.jpg)

![HCOG Ranger zoomed in (70 FOV)](../../.gitbook/assets/titanfall2\_myp3treoft.jpg)

![HCOG Ranger zoomed out (118.125 FOV)](../../.gitbook/assets/titanfall2\_dmtalqxcbr.jpg)

{% hint style="info" %}
**Resources:**

* [https://developer.valvesoftware.com/wiki/Field\_of\_View](https://developer.valvesoftware.com/wiki/Field\_of\_View)
* [https://en.wikipedia.org/wiki/Frustum](https://en.wikipedia.org/wiki/Frustum)
* [https://en.wikipedia.org/wiki/Angle\_of\_view](https://en.wikipedia.org/wiki/Angle\_of\_view)
* [https://en.wikipedia.org/wiki/Parallax](https://en.wikipedia.org/wiki/Parallax)
{% endhint %}
