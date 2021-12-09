---
description: >-
  A 2D skybox is a skybox that lacks geometrical depth, consisting only of a
  skybox texture (without using the sky_camera entity to display a 3D miniature
  model).
---

# 2D Skybox

A 2D skybox is a [skybox](./) that lacks geometrical depth, consisting only of a skybox texture (without using the [sky\_camera](https://developer.valvesoftware.com/wiki/Sky\_camera) entity to display a 3D miniature model).

![](../../../.gitbook/assets/skybox\_template.jpg)

## Adding sky to a map

Simply texture a [world brush](https://developer.valvesoftware.com/wiki/World\_brush) (not a [brush entity](https://developer.valvesoftware.com/wiki/Brush\_entity)) with the [**`tools/toolsskybox`**](https://developer.valvesoftware.com/wiki/Tool\_textures) or (if you are mapping for the [Orange box](https://developer.valvesoftware.com/wiki/Orange\_box)) the [**`tools/toolsskybox2d`**](https://developer.valvesoftware.com/wiki/Tool\_textures) material.

In-game, the skybox will be seen through each surface that `toolsskybox` is applied to.

`toolsskybox` Brushes do not need to be box-shaped.

{% hint style="info" %}
**Note:**In [HL2](https://developer.valvesoftware.com/wiki/HL2) the default skybox has visible seams. This is not your fault. See the next section for how to change the default.
{% endhint %}

{% hint style="info" %}
**Note:**You should avoid making a skybox by drawing a big hollowed out cube with the Skybox texture around your map.
{% endhint %}

****

## Changing the displayed skybox

See also [Sky List](https://developer.valvesoftware.com/wiki/Sky\_List)

If you don't like the standard "sky\_day01\_01" sky, you can change it by setting the skybox name in Hammer's Map Properties dialog. With the correct map opened, follow these steps:

1. Go to the [Map menu](https://developer.valvesoftware.com/wiki/Hammer\_Map\_Menu)
2. Choose **Map Properties...** from the drop down list
3. In the Object Properties window, select the **Skybox Texture Name** field.
4. Replace the sky listed there with the name of the skybox you wish to display.

![](../../../.gitbook/assets/sky\_change.png)

## Skybox Lighting

Skybox Lighting enters the map through every [toolsskybox](https://developer.valvesoftware.com/wiki/Skybox)-textured [brush](https://developer.valvesoftware.com/wiki/Brush), representing direct sun/moonlight and diffuse skylight. Its basic properties are controlled by three entities used in combination (four in some games):

* [`light_environment`](https://developer.valvesoftware.com/wiki/Light\_environment) defines the direction, color and intensity of the direct sunlight, and the color and intensity of the diffuse skylight.
* [`shadow_control`](https://developer.valvesoftware.com/wiki/Shadow\_control) defines the color, direction, and attenuation distance of the [dynamic shadows](https://developer.valvesoftware.com/wiki/Dynamic\_Shadows) that are created by `light_environment`. Dynamic shadows will be buggy and unconfigurable without this entity.
* [`env_sun`](https://developer.valvesoftware.com/wiki/Env\_sun) places a glowing sprite in the skybox to represent the Sun's apparent position in the sky.
* [`env_cascade_light`](https://developer.valvesoftware.com/wiki/Env\_cascade\_light) casts harsh, real-time shadows onto the map, usually copying settings from the `light_environment`. [![\<Counter-Strike: Global Offensive>](https://developer.valvesoftware.com/w/images/3/35/Csgo.png)](https://developer.valvesoftware.com/wiki/Counter-Strike:\_Global\_Offensive)[![\<Insurgency>](https://developer.valvesoftware.com/w/images/a/af/Insurgency\_16x\_icon.png)](https://developer.valvesoftware.com/wiki/Insurgency)[![\<Black Mesa (Source)>](https://developer.valvesoftware.com/w/images/c/cc/Black\_mesa\_icon.png)](https://developer.valvesoftware.com/wiki/Black\_Mesa\_\(Source\)) only.

To make sense of it all, just make sure you have only one of each of these entities in your map, and that the **Pitch and Yaw \<angles>** are set the same for all three of them. (Pitch is equivalent to the Sun's angle of elevation from the ground, and Yaw is its compass bearing.)

These lighting settings - direction, color, brightness, etc are fairly specific to the actual image used for the 2D skybox. The [Sky List](https://developer.valvesoftware.com/wiki/Sky\_List) article suggests some settings for official game skyboxes. The [`worldspawn`](https://developer.valvesoftware.com/wiki/Worldspawn) entity defines which [skybox](https://developer.valvesoftware.com/wiki/Sky\_List) to use. Also note that fog will look wrong if [`env_fog_controller`](https://developer.valvesoftware.com/wiki/Env\_fog\_controller)'s settings don't correspond to the particular skybox in use.![](https://developer.valvesoftware.com/w/images/c/cc/Note.png) **Note:Pitch** can be overriden for `light_environment` and `env_sun`, but not `shadow_control`. The **Pitch** override also cannot be switched off and its rotation is measured counter-clockwise from the horizontal (so straight down is -90°) whereas the **\<angles> Pitch'**s rotation is clockwise (so straight down is +90°). The workaround for this is to make sure your **Pitch** override merely repeats the **\<angles>** value; for example, if your `shadow_control`, `light_environment` and `env_sun` **\<angles>** are "45 -60 0", set the **Pitch** override to "-45".

## Creating a Custom 2D Skybox Texture

1. Prepare your image files. You need six images of the same resolution:
   * \<skyname>BK
   * \<skyname>DN
   * \<skyname>FT
   * \<skyname>LF
   * \<skyname>RT
   * \<skyname>UP
2. [Convert them to VTF.](https://developer.valvesoftware.com/wiki/Creating\_a\_Material) Make sure that you enable "Clamp S" and "Clamp T" flags or you'll see seams when running with lower texture detail.
3. Create materials for each texture in `\materials\skybox\`, using the following template:

```
unlitgeneric
{
	$basetexture "<VTF>"
	$hdrcompressedtexture "<VTF>"
	$nofog 1
	$ignorez 1
}
```

Now, in [Hammer](https://developer.valvesoftware.com/wiki/Hammer), go to Map > Map Properties > Skybox Texture Name and type in your skybox name without any side tags.

## Creating a 2D skybox for [Goldsource](https://developer.valvesoftware.com/wiki/Goldsource), using Source

It is possible to create an area of your map into a 2D Skybox to be used in Goldsource (the HL1-engine). Here's an simple example:

1. Create a large outdoor area with some displacement maps and treelines, and fog to hide the edges. Lets call it **carrotjuice** .
2. Load the map ingame and turn cheats on ( sv\_cheats 1 ).
3. Activate the noclip-mode by simply opening the console and enter "**noclip**" and hit Enter.
4. Fly to the center of where you want the skybox.
5. Open up the console and type "**mat\_envmaptgasize 256**", hit Enter.
6. Now type "**envmap**" and press Enter. Now, 6 TGA-files are now created and saved into a folder named "cubemap\_screenshots" in your modfolder ( i.e. for Portal 2: Steam\SteamApps\common\Portal 2\portal2 ).

Since the mapname was **carrotjuice** , the name of the 6 TGA-files are as following:

```
carrotjuicert.tga (Right)
carrotjuiceft.tga (Front)
carrotjuicelf.tga (Left)
carrotjuicebk.tga (Back)
carrotjuiceup.tga (Up)
carrotjuicedn.tga (Down)
```

You can now copy or move these to your HL1-mods gfx\env-folder, to use it as skybox in a level.

## Source & reference

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Skybox\_(2D)](https://developer.valvesoftware.com/wiki/Skybox\_\(2D\))
{% endhint %}
