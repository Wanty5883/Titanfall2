---
description: 一键更换你的武器视野
---

# 一键更换武器视野

## 前期准备

在本指南中，您需要去编辑一个配置文件，即 `.cfg` 文件。请注意：如果你没有 `autoexec.cfg`文件在`Origin Games\Titanfall2\r2\cfg\` 目录中，你需要手动去新建一个同名文件。  
  
进入以下文件目录，并查找 `autoexec.cfg` 文件：

> Origin Games\Titanfall2\r2\cfg\

使用你的文本编辑器打开它。

{% hint style="info" %}
您也可以为配置文件使用其他的名称，但需要使用命令来执行它。
{% endhint %}

## 介绍

Source Engine games handle magnification when aiming down sights by changing the FOV to a smaller number, which creates the effect of magnification.   
This guide will teach you how to apply this effect to your hipfire view. We can achieve this by binding a key to cycle between multiple FOVs.

## 编辑

Open your `autoexec.cfg` in your text editor and type in the following lines.

```text
bind "MOUSE4" fovtoggle
	alias fovtoggle "fov1"
		alias "fov1" "cl_fovScale 1.0; alias fovtoggle fov2"
		alias "fov2" "cl_fovScale 1.6875; alias fovtoggle fov1"
```

Note that `cl_fovScale` values below 1.0 will default to 1.0.

I bound my FOV toggle to "MOUSE4", you can bind it to any button you'd like.  
  
This will toggle between`cl_fovScale 1.6875 (118.125 FOV)`and `cl_fovScale 1.0 (70 FOV).`  
However you will not have sensitivity scaling so when zooming in your mouse movement, much like your image, will be magnified.  
  
To have your sensitivity scale properly with your zoom you will need to divide your sensitivity value by the amount that you are zooming in \(in my case that value is `1.6875 / 1.0 = 1.6875`\), in this case the zoomed in sensitivity is `3.848 / 1.6875 = 2.2802962963`.  
  
Now add the proper sensitivity values to `"fov1"` and `"fov2"`

```text
bind "MOUSE4" fovtoggle
	alias fovtoggle "fov1"
		alias "fov1" "cl_fovScale 1.0; alias fovtoggle fov2; m_sensitivity 2.2802962963"
		alias "fov2" "cl_fovScale 1.6875; alias fovtoggle fov1; m_sensitivity 3.848"
```

This will ensure that the mouse movement is not magnified and feels the same as it would when zoomed out.

## 样例

{% embed url="https://gfycat.com/vaguedazzlingbackswimmer" %}

{% embed url="https://gfycat.com/sizzlingunfitasiansmallclawedotter" %}

![EVA-8&#x653E;&#x5927; \(70 FOV\)](../../.gitbook/assets/titanfall2_pcjd3nma5s.jpg)

![EVA-8&#x7F29;&#x5C0F;\(118.125 FOV\)](../../.gitbook/assets/titanfall2_gsvomi4dfk.jpg)

![HCOG&#x7784;&#x51C6;&#x955C;&#x653E;&#x5927;\(70 FOV\)](../../.gitbook/assets/titanfall2_myp3treoft.jpg)

![HCOG&#x7784;&#x51C6;&#x955C;&#x7F29;&#x5C0F; \(118.125 FOV\)](../../.gitbook/assets/titanfall2_dmtalqxcbr.jpg)

{% hint style="info" %}
**资源：**

* [https://developer.valvesoftware.com/wiki/Field\_of\_View](https://developer.valvesoftware.com/wiki/Field_of_View)
* [https://en.wikipedia.org/wiki/Frustum](https://en.wikipedia.org/wiki/Frustum)
* [https://en.wikipedia.org/wiki/Angle\_of\_view](https://en.wikipedia.org/wiki/Angle_of_view)
* [https://en.wikipedia.org/wiki/Parallax](https://en.wikipedia.org/wiki/Parallax)
{% endhint %}

