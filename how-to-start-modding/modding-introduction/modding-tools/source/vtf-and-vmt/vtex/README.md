---
description: Vtex is the command-line tool to convert TGA/PSD files into VTF
---

# Vtex

Valve Texture Tool, or Vtex  is the [command-line](https://developer.valvesoftware.com/wiki/Command-line) tool used to convert [targa (.tga)](../../../../../../documentation/file-format/truevision-graphics-adapter-tga.md) or [Photoshop (.psd)](../../../../../../documentation/file-format/psd-photoshop-document.md) (Orange box SDK) image files into [Valve Texture Files (.vtf)](../../../../../../documentation/textures/valve-texture-format-vtf/) for use in the Source engine. It takes a [targa (.tga)](../../../../../../documentation/file-format/truevision-graphics-adapter-tga.md) image and an optional list of compile parameters, and creates a [Valve Texture File (.vtf)](../../../../../../documentation/textures/valve-texture-format-vtf/) from them.

{% hint style="info" %}
&#x20;**Note:**It is **recommended** that you use the third-party tool [**VTFEdit**](../vtfedit.md) instead. VTFEdit boasts a user-friendly interface, a wider array of accepted formats, the ability to change most VTF's properties without recompiling, a standalone viewer, and direct GCF access.
{% endhint %}

VTFEdit will make your life so much easier but in certain cases, you have to use Vtex to do certain task. Modding or creating VTF files with spritesheet is a good example

{% content-ref url="../../../../../../documentation/textures/valve-texture-format-vtf/animated-particles.md" %}
[animated-particles.md](../../../../../../documentation/textures/valve-texture-format-vtf/animated-particles.md)
{% endcontent-ref %}

## Basic usage

1. Make sure that [Steam](https://developer.valvesoftware.com/wiki/Steam) is running.
2. Place the targa image to be converted inside the `SteamApps/common/gamefolder/materialsrc/` folder, where gamefolder is the game folder of the current game (`cstrike`/`dod`/`hl2`/`hl2mp`/`tf`). You can also place the image within a subfolder of this folder, to make Vtex compile the texture to the corresponding `materials/` subfolder. (For instance, placing the image in a `materialsrc/metal/` subfolder, will make Vtex compile the texture to the `materials/metal/` subfolder.)
3. If necessary, write a [text (.txt) file](../../../../../../documentation/file-format/txt-text-file.md) containing a set of [Vtex compile parameters](vtex-compile-parameters.md). Give it the same name as the targa image (with the exception of the .txt extension) and put it in the same folder. If you choose to omit this list, Vtex will create an empty one for you during compilation.
4. The Vtex executable (Vtex.exe) is located in the `/Steam/SteamApps/common/gamefolder/bin/` folder, again where `gamefolder` is the folder that corresponds with the target game. It can be executed in one of two ways: Through the easy "drag-and-drop" method (described below), or the more advanced command prompt method, described [here](./#firstHeading). Steam must run while it is executed.
5. The resulting Valve Texture File (.vtf) will be compiled to the `materials/` folder of the current game by default. For instance, if the current game would be [Half-Life 2](https://developer.valvesoftware.com/wiki/Half-Life\_2), the texture file would be compiled to the `SteamApps/common/Half-Life 2/hl2/materials/` folder. If the targa image resided within a subfolder, Vtex will compile the texture file to the corresponding `materials/` subfolder. If that subfolder doesn't exist, Vtex will create it automatically.

### The drag-and-drop method

The drag-and-drop method is the easy way to use Vtex. Just drag the icon of either the targa image to be converted, or its list of compile parameters (from its `materialsrc/` folder) on top of the icon of the Vtex executable (Vtex.exe) and let go, and Vtex will compile the texture file automatically.

## Vtex CLI use <a href="#firstheading" id="firstheading"></a>

Apart from the drag-and-drop method, Vtex can also be executed via the command prompt in the Command Line Interface (MS-DOS). This will allow you to use its more advanced features. You can provide additional parameters to create a basic .vmt file when the texture is compiled, as well as other options.

The syntax for `vtex.exe` is as follows:

```
vtex [-quiet] [-nopause] [-mkdir] [-shader ShaderName] [-vmtparam Param Value] texture1 texture2 ...
```

Any file extentions are ignored. (You can refer to the non-existant texture1.asd without problems, as long as the tga image is still present.)

### Basic Vtex usage

[Command-line](https://developer.valvesoftware.com/wiki/Command-line) may explain this better.

The Windows environment variable "`%sourcesdk%`" can be utilized to locate `vtex.exe` easily in a command-line statement. This variable contains the location of the Source SDK installation directory.

For example, to compile a Half-Life 2 material called "`sample_material.tga`" in the directory "`sourcesdk_content/hl2/materialsrc/metal`", you would open a command prompt, change to the directory to "`sourcesdk_content/hl2/materialsrc/metal`" and type this at the command-line:

```
"%sourcesdk%\bin\vtex" sample_material.tga
```

The compiled .vtf file would be compiled to this folder (assuming you had set **Half-Life 2** as your current game directory):

```
SteamApps\username\half-life 2\hl2\materials\metal
```

{% hint style="info" %}
&#x20;**Note:**It is very important that you set the **Current Game** in either the **SDK Launcher** or **VConfig** to the correct game directory before you open a command prompt to compile textures. Changing the **Current Game** will not affect any command prompt windows that are already open. This is due to how Windows uses environment variables.
{% endhint %}

### Vtex commands

#### -mkdir

You can add the `-mkdir` command to vtex, and it will add the destination directory if it does not exist. For example, if you had a .tga at `/sourcesdk_content/hl2/materialsrc/sample/sample_material.tga` you would type this at the command-line:

```
"%sourcesdk%\bin\vtex" -mkdir sample_material.tga
```

This would create a new directory called "`sample`" in your `Half-Life 2/hl2/materials` directory, if it didn't already exist, and then place the compiled .VTF file in that new location. If the directory already exists, the `-mkdir` parameter is ignored.

#### -shader

You can use the `-shader <shadername>` command to have Vtex create a .VMT for the new material with the [shader](../../../../../../documentation/textures/shader/) specified. For example, to create a basic `LightmappedGeneric` material, use the `-shader` command like this:

```
"%sourcesdk%\bin\vtex" -shader LightmappedGeneric sample_material.tga
```

This would compile the material sample\_material.vtf in `half-life 2/hl2/materials/metal` as well as create a new material file `sample_material.vmt` in the same location, using the `LightmappedGeneric` shader, like this:

```
"LightmappedGeneric"
{
	"$baseTexture" "sample/lightmappedgeneric"
}
```

#### -vmtparam

You can use the `-vmtparam <parameter> <value>` command to additional material parameters to the created .vmt file. If a .vmt already exists in the same location, any new parameters will not be added. For example, to make a material translucent, you would type the following:

```
"%sourcesdk%\bin\vtex" -shader LightmappedGeneric -vmtparam $translucent 1 sample_material.tga
```

Which would create the following `sample_material.vmt`:

```
"LightmappedGeneric"
{
	"$baseTexture" "sample/lightmappedgeneric"
	"$translucent" 1
}
```

You can add multiple `-vmtparam` statements in the same Vtex command, like this:

```
"%sourcesdk%\bin\vtex" -shader LightmappedGeneric -vmtparam "$bumpmap" "sdk/bumpspecular_normal" -vmtparam "$envmap" "env_cubemap" sample_material.tga
```

This would create the following `sample_material.vmt` specifying parameters for a bumpmapped specular material:

```
 "LightmappedGeneric"
 {
 	"$baseTexture" "sample/sample_material"
 	"$bumpmap" "sdk/bumpspecular_normal"
 	"$envmap" "env_cubemap"
 }
```

#### -quiet

When added, this commands will cause Vtex to do its work without producing any output to the console and will not pause when finished.

#### -nopause

Removes the "`Hit a key to continue`" message that appears when Vtex has finished working.

#### -outdir

You can use the `-outdir <parameter> <value>` command to override the output directory out the VTF file.

#### -quickconvert

Used to quickly convert an older VTF file format to a newer VTF file format.

#### -dontusegamedir

Puts output files in same folder as input files. Best used with `-quickconvert`

### Wildcards

Command-line wildcards can also be used with Vtex. This command-line would compile all .tga files in the current directory:

```
"%sourcesdk%\bin\vtex" *.tga
```

This command-line would compile all .tga files in the current directory with names than begin with "sample":

```
"%sourcesdk%\bin\vtex" sample*.tga
```

In this case, the files "`sample_metal`" and "`sample3`" would be compiled, but not "`samp_metal`" or "`sampl_2`".

### Chaining

Vtex can compile multiple materials from the same command-line. Simply add the name of each .tga after the first, like this:

```
"%sourcesdk%\bin\vtex" sample_material1.tga sample_material2.tga sample_material3.tga
```

If a .vmt is generated on the command-line using the `-shader` command, a unique .vmt will be created for each .tga in the chain, all with the same parameters specified by the `-shader` and `-vmtparam` commands. If you need more individual control of the shader parameters of each .tga, use a batch (.bat) file to run vtex multiple times instead.

{% hint style="info" %}
Source:

* [https://developer.valvesoftware.com/wiki/Vtex](https://developer.valvesoftware.com/wiki/Vtex)
* [https://developer.valvesoftware.com/wiki/Vtex\_CLI\_use](https://developer.valvesoftware.com/wiki/Vtex\_CLI\_use)
{% endhint %}
