---
description: Change the Skybox of different maps
---

# Maps - Skyboxes

## Preparation

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these files and paste them into an empty folder somewhere else:

`englishclient_mp_`**`<<mapname>>`**`.bsp.pak000_dir.vpk`

`client_mp_`**`<<mapname>>`**`.bsp.pak000_000.vpk`

{% hint style="danger" %}
Make sure to make a Backup of every single Map you edit, Since every map has it's own VPK.
{% endhint %}

You will need the Titanfall VPK Tool, a program which allows you to open and repack Titanfall VPK files. It can be found in the Modding Tools page

{% page-ref page="../../how-to-start-modding/modding-introduction/modding-tools/" %}

## Unpacking

Now that these files have been backed up and everything is installed. Navigate to your game folder and open this file:

`Origin Games\Titanfall2\vpk\englishclient_mp_`**`<<mapname>>`**`.bsp.pak000_dir.vpk`

{% page-ref page="../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

## Editing

Navigate to this location in your extracted folder

`\models\vistas`

This folder contains the models for the skyboxes and scene elements. Edit those files at your own risk.

{% page-ref page="../../information/textures/skybox-basics/" %}

The only working Skybox is the extraction scene named `planet_blue_sun.mdl` which is present in every `\models\vistas` directory \(except live fire maps, excluding deck\). Because it is mandatory for the successful extraction phase process of every map.  

To swap skyboxes simply duplicate `planet_blue_sun.mdl` and rename the duplicate to the name of the skybox of the map. 

![duplicate &quot;planet\_blue\_sun.mdl&quot;](../../.gitbook/assets/step-1.PNG)

![rename the duplicate](../../.gitbook/assets/step-2.PNG)

![delete the original skybox](../../.gitbook/assets/step-3.PNG)

#### Exceptions

{% hint style="warning" %}
Some maps have the ending **\_**_**se**_ instead of _**\_sky**_. It is the exact same editing process though.

![](../../.gitbook/assets/exception.PNG)

Some maps feature an additional file in the directory.  Make sure not to swap the wrong ones.

![Don&apos;t touch &quot;angel\_city\_scrolling\_uv.mdl&quot;  ](../../.gitbook/assets/exception-1.PNG)

![Don&apos;t touch &quot;timeshift\_warm\_se.mdl&quot;](../../.gitbook/assets/exception-2.PNG)
{% endhint %}

#### What _**NOT**_ to do

{% hint style="danger" %}
Removing the Files will result in the disappearing of the skybox.

![No skybox on Kodai](../../.gitbook/assets/desktop-screenshot-2020.03.01-17.23.57.22.png)
{% endhint %}

{% hint style="danger" %}
Renaming other [skyboxes ](../../information/textures/skybox-basics/)to the existing ones of the map and replacing them leads to the textures not loading in, since they are applied via a script, which is not in the VPK itself. 

![Kodai Skybox on Glitch](../../.gitbook/assets/desktop-screenshot-2020.03.01-17.07.41.44.png)
{% endhint %}

The reason behind this not working is because the textures are not applied via a VPK. Every map has a different VPK. Textures that are not normally on the map stay missing because the script applying them does not apply them there. Once we figured out how to edit `.rpak` files changing actual [skyboxes ](../../information/textures/skybox-basics/)becomes a possibility. 

## Examples

Obviously this wasn't made to be the skybox for normal maps. So there are little errors all around the place.

**Note that the old scene lights are still present and might look a little out of place on some maps.**

{% embed url="https://gfycat.com/alldecisivefinwhale" %}

![Kodai with &quot;mat\_sky\_color 0.5 0.5 0.5;mat\_sun\_color 0.5 0.5 0.5&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.05-17.44.46.45.png)

![Glitch with&quot;mat\_sky\_color 0.5 0.5 0.5;mat\_sun\_color 0.5 0.5 0.5&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.05-17.46.24.61.png)

![Homestead with &quot;mat\_sky\_color 0.5 0.5 0.5;mat\_sun\_color 0.5 0.5 0.5&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.05-17.18.16.92.png)

**Note that the** _**ENTIRE**_ **surrounding scenery disappears.**

![Angel City with &quot;mat\_sky\_color 0 0 0; mat\_sun\_color 0 0 0&quot; ](../../.gitbook/assets/desktop-screenshot-2020.03.04-18.47.58.92.png)

![Drydock with&quot;mat\_sky\_color 0.5 0.5 0.5;mat\_sun\_color 0.5 0.5 0.5&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.05-17.27.28.28.png)

![Complex with &quot;mat\_sky\_color 0.5 0.5 0.5;mat\_sun\_color 0.5 0.5 0.5&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.05-17.20.31.33.png)

## Repacking

{% page-ref page="../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

After closely following the previous link step by step:

Rename `pak000_000.vpk` _to_ **`client_mp_` `<<mapname>>` `.bsp.pak000_000.vpk`**

Rename `pak000_dir.vpk` _to_ **`englishclient_mp_` `<<mapname>>`** **`.bsp.pak000_dir.vpk`**

{% hint style="danger" %}
Make sure to pay attention when renaming them because every map has it's own VPK.
{% endhint %}

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see the changed [skybox](../../information/textures/skybox-basics/)!

> Origin Games\Titanfall2\vpk\

{% page-ref page="../../information/textures/skybox-basics/" %}

