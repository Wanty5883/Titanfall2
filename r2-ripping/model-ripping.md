---
description: How To Rip Game Models With Textures into blender
---

# Exporting Models

## Required Software

* Blender
  * Blender Source Tool - For importing models into blender
  * S/G Shader - For linking textures
* Legion - RPAK ripping tool
* Crowbar - Source Engine model tool
* Titanfall VPK Tool - Titanfall VPK tool

{% hint style="info" %}
Check down bellow for the tools page where all the link are provided
{% endhint %}

{% page-ref page="../how-to-start-modding/modding-introduction/modding-tools/" %}

## Getting The Models

First, we need to actually obtain the models. You can do this by extracting this VPK file you can learn how to extract VPKs

{% page-ref page="../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

For the most part, models can be found in the common vpk. But you will find other models in the other vpk from Titanfall 2.

```text
"Titanfall2\vpk\englishclient_mp_common.bsp.pak000_dir.vpk"
```

Next, you need to find the model you want. In this guide, as an example, the CAR SMG will be chosen. Which is located here

```text
ExtractedVPK\models\weapons\car101
```

However, we can't just straight import this into blender, we will need to decompile the model using crowbar. So first, extract crowbar using your archive software of choice, and load up `crowbar.exe` 

![Copy these settings here, with the filepath to your model and click decompile](../.gitbook/assets/crowbar-settings.png)

Once you've decompiled the model into the folder of your choice, we need to open up blender and install blender source tools. 

![Go into your preferences panel](../.gitbook/assets/desktop-2020.08.10-14.13.29.22_1.gif)

![Click the install button on top of the blender preferences window](../.gitbook/assets/install%20%281%29.png)

![Locate your add-on and install it as shown.](../.gitbook/assets/adding-the-addon.gif)

## Importing The Models

Next, we need to import the models using blender source tools. This can easily be done by clicking on `File > import`, and importing the `.qc` file as shown

![](../.gitbook/assets/importing-the-model.gif)

After the model is imported, if you zoom out it should look like this

![](../.gitbook/assets/carsmg-import-without-delete.png)

As you can see, it has addons equipped, such as the proscreen. We can delete this as shown below

![](../.gitbook/assets/deleting-the-proscreen.gif)

## Texturing The Model

Finally, we can begin to texture our model, this is perhaps the most tedious step, so buckle up

![We can begin to import the nodetree which helps with texturing the model](../.gitbook/assets/appending-the-nodes.gif)

![Change your workspace from layout, to shading. ](../.gitbook/assets/shading-workspace.png)

![Press File / Append](../.gitbook/assets/append-me.png)

![Select your SG\_Shader blend file](../.gitbook/assets/sg-shader.png)

![Select The Nodetree folder, and then the S/G shader](../.gitbook/assets/nodetree.png)



![Delete / Import the nodes as shown](../.gitbook/assets/removing-adding-nodes.gif)

![Set your legion settings to these here](../.gitbook/assets/legion-settings.png)

![Copy paste the texture name and paste it into the legion extractor search bar. ](../.gitbook/assets/copy-paste.gif)

![The textures are located within the &quot;exported\_files/materials&quot; path for legion.](../.gitbook/assets/car-smg.png)

Now, we need to link up the textures to the blender node, however. we need to figure out which texture is which type. I've created a handy little image to help you identify them 

![](../.gitbook/assets/texture-linking.png)

Link them up using the visual guide above

![](../.gitbook/assets/adding-the-nodes.gif)

## Congrats!

Once its all textured up, your model should look like this, congrats!

![](../.gitbook/assets/spijny-car.gif)



