# Valve Material Type - VMT

A **material** is a `.vmt` \("Valve Material Type"\) text file that defines a two-dimensional surface. It contains all of the information needed for Source to simulate the surface visually, aurally, and physically.

The contents of a material will fall into some or all of these categories:

1. [Texture](./) names
2. [Physical surface types](https://developer.valvesoftware.com/wiki/$surfaceprop)
3. [Shader](https://developer.valvesoftware.com/wiki/Shader) [parameters](https://developer.valvesoftware.com/wiki/Category:List_of_Shader_Parameters)
4. [Fallbacks](https://developer.valvesoftware.com/wiki/Material_optimization)
5. [Proxies](https://developer.valvesoftware.com/wiki/Material_Proxy)

## A simple example

```text
LightmappedGeneric
{
	$basetexture coast\shingle_01
	$surfaceprop gravel
}
```

This is a very basic [shingle beach](http://en.wikipedia.org/wiki/Shingle_beach) material.

1. The [`LightmappedGeneric`](https://developer.valvesoftware.com/wiki/LightmappedGeneric) shader is used, which means that the material is for use on surfaces with [lightmaps](https://developer.valvesoftware.com/wiki/Lightmap) \(i.e. [brushes](https://developer.valvesoftware.com/wiki/Brush)\).
2. The **{** character opens a set of parameters
3. The [`$basetexture`](https://developer.valvesoftware.com/wiki/$basetexture) parameter is given with `coast\shingle_01`, which is the location of a texture. This is what will be drawn on the screen.
4. [`$surfaceprop`](https://developer.valvesoftware.com/wiki/$surfaceprop) gives the material the physical properties of gravel.
5. The **}** character closes a set of parameters

It's important to remember that this material can only be used on brushes. If it needed to be used on [models](https://developer.valvesoftware.com/wiki/Model), for instance, another version would need to be created using the [`VertexLitGeneric`](https://developer.valvesoftware.com/wiki/VertexLitGeneric) shader.

Most of the time switching materials from one shader to another is as simple as changing their first line, since a great number of parameters are shared between them. Some params only work with certain shaders, like [Phong](https://developer.valvesoftware.com/wiki/Phong) effects, which are only available with `VertexLitGeneric`, but unfortunately you won't encounter any critical errors if a param isn't understood by the shader. It just won't have any effect.![](https://developer.valvesoftware.com/w/images/4/45/Tip.png) **Tip:**If you ever need to use a space or tab character in a parameter value, you must wrap the whole value with "quote marks". You'll often see absolutely everything wrapped like this - save yourself some typing, as that's unnecessary.

## Finding materials

### SteamPipe

When Valve updated some games to [SteamPipe](https://developer.valvesoftware.com/wiki/SteamPipe), the materials were moved from [GCF](https://developer.valvesoftware.com/wiki/GCF) into [VPK](https://developer.valvesoftware.com/wiki/VPK) files. VPK Files work with [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape).

More info on SteamPipe [here](https://support.steampowered.com/kb_article.php?ref=7388-QPFN-2491)

### Non-SteamPipe Games

in non [SteamPipe](https://developer.valvesoftware.com/wiki/SteamPipe) source games, Materials are stored in the `materials\` folder of your game or mod. The best way to browse them is from [Hammer](https://developer.valvesoftware.com/wiki/Hammer)'s texture selection screen.

If you want to edit or view the code of Valve's material files you will first need to extract them from their [GCF](https://developer.valvesoftware.com/wiki/GCF) package with [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape). They tend to be stored in GCFs with 'materials' in their name.

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Material](https://developer.valvesoftware.com/wiki/Material)
{% endhint %}

