---
description: >-
  Particles are animated by using a material comprised of a collection of
  materials all built together into a "sheet". This is accomplished by using the
  mksheet.exe and vtex tools.
---

# Creating Animated Particles

Particles are animated by using a material comprised of a collection of materials all built together into a "sheet". This is accomplished by using the **mksheet.exe** and **vtex** tools.

## Creating an MKS File

First, place your materials that will make up the sheet in a separate sub-directory, usually named for the material they will ultimately represent. For instance, the smoke1.vmt is placed under the materials/particles/smoke1 subdirectory.

Next, create a file with the same name as the material you'd like to make, and give it an .mks file extension. For the smoke1.vmt, you would call this smoke1.mks.

The .mks file defines how the sheet is interpreted when the particle is rendered. You can organize materials in to sequences for playback, define the number of frames and their playback rate, and whether a sequence should loop continuously.

In the .mks file, this looks like:

```text
// First sequence
sequence 0
loop
frame mymaterial1.tga 1
frame mymaterial2.tga 1

// Second sequence
sequence 1
frame mymaterial3.tga 1

// multiple image sequence (two images per frame, for multi-texturing)
sequence 2
frame fire_base0.tga fire_additive0.tga 1
frame fire_base1.tga fire_additive1.tga 1

// Sequence that combines the alpha channels of two frames at a time
//  into the alpha and green channels of a frame for a special shader
sequence 3
frame frame0.tga{g=a},frame1.tga{a=a} 1
frame frame2.tga{g=a},frame3.tga{a=a} 1
```

### sequence

Tells mksheet that the following frames are to be grouped together into a sequence, which can be referred to by number. This allows you to pick different animations or frame groups when the particle is created.

### frame

Takes two parameters. The first is the material to use for this frame. The second is the playback rate. A value of 1 tells the renderer to playback this frame for the normal time duration. A value of 0.5 would play the frame for half as long as was specified in the particle definition, and a value of 2 would make the frame render for twice as long.

### loop

Tells the renderer to loop the frames continuously. Without this identifier the renderer would play all the frames in the sequence once and stop on the last frame.

Additionally, frames can be packed separately in RGB from Alpha. This takes the alphas from a set of input frames and stores them in the alpha of the output sheet. It takes the RGBs and stores them in the RGB. The interesting thing about this is that each get their own sequences. They also have their frame sizes entirely decoupled, so the RGB's can have 200x200 images while the alpha has 150x150, for example. See Below :

```text
// Sequence that stores separate frame data in the RGB from the alpha
//  for dual sequencing combining one set of RGBs and another set of alphas

// Packmode sets mksheet to separate the RGB frames from the Alpha ones.
packmode rgb+a

// First Sequence - Looping Alpha Frames
sequence-a 0
LOOP
frame reframedSmokeSprites170_0033.tga 1
frame reframedSmokeSprites170_0035.tga 1

// Second Sequence - Looping RGB Frames
sequence-rgb 1
LOOP
frame smokeTex0001_341.tga 1
frame smokeTex0002_341.tga 1
```

The output from this .mks file can be seen below. The RGB and alpha channels are shown. Note that the individual frame sizes are all non-power-of-two and that they are different between the RGB and Alpha frames.

![](../../../.gitbook/assets/vista_smoke_rgb.jpg)

![](../../../.gitbook/assets/vista_smoke_alpha.jpg)

## Compiling the Sheet

Once the materials are created, move all of your .tga and .mks files to the `"Steamapps/common/SourceSDK/bin/orangebox/bin"` folder. Inside this directory, create a .bat file, and inside it, write:

```text
mksheet <sheetname>.mks <sheetname>.sht <sheetname>.tga
```

The tool takes one main parameter and two optional ones. The first is the .mks sheet which will define how the .sht and .tga files are created. The second, optional parameter is the .sht file. Finally, the third optional parameter is the .tga file to create, consisting of all the tga files previously specified. The second and third parameters must bear the name of the final material you wish to create. For example, the build call for the smoke1.vmt material would be:

```text
mksheet smoke1.mks smoke1.sht smoke1.tga
```

From this, you will get a/some compiled tga files, a .sht file and a blank .file file. feel free to delete the .file file.

## Compiling the Texture

At this point you should have a .tga file. You can now compile the output .tga file using the vtex.exe tool. Drag both the final .tga file/s, and the .sht file to your game's "materialsrc" file. For Half Life 2, this folder is located at "common/Half-Life 2/hl2/materialsrc". From there, open a new window, and navigate to the location of vtex.exe. Then, simply drag the .sht file onto the vtex.exe. Your finished material will be located in the base materials folder. For Half Life 2, this folder is located at ""common/Half-Life 2/hl2/materials".

{% hint style="warning" %}
[VTFEdit](../../../how-to-start-modding/modding-introduction/modding-tools/#vtf-and-vmt) probably doesn't support this type of compiling yet.
{% endhint %}

## Notes

You can use the same image file in multiple sequences \(or multiple times within the same sequence\) without it being duplicated in the output sheet. Examples where you would want to do this are sequences with different timing, particle sequences, looped and non-looped versions of a sequence, etc.

To the extent practical, you should combine as many sprite textures into one sheet as possible, and use different sequences for the different particle systems \(hmm this implies that we might want named sequences for sanity's sake\). This will allow particle systems to be drawn with fewer state changes or even as one batch.

## Automation in 3ds Max

You can now export rendered sequences directly into Source with Wall Worm. The system allows you to export IFL \(Image File List\) bitmaps made of TGA bitmaps. Based on the bitmap parameters, the MKS is generated automatically, then sent to mkshheet with the .SHT file and TGA files. See complete documentation at [http://dev.wallworm.com/document/187/exporting\_animated\_particle\_textures.html](http://dev.wallworm.com/document/187/exporting_animated_particle_textures.html)

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Animated\_Particles](https://developer.valvesoftware.com/wiki/Animated_Particles)
{% endhint %}

