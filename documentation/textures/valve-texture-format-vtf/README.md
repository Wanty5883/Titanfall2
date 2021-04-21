# Valve Texture Format - VTF

The **Valve Texture Format \(VTF\)** is the propietary [texture ](../)format used by the [Source ](https://developer.valvesoftware.com/wiki/Source)engine. VTF files are generally referenced in a material instead of being accessed directly, which almlows re-use in different ways.

VTF files can be created from TGA images using the Source SDK Tool VTEX, or from most common image formats with [third-party tools](../../../how-to-start-modding/modding-introduction/modding-tools/#vtf-and-vmt). Both textures and materials are stored in subfolders of `game_dir/materials/`.

## Storage capabilities

 The VTF image format can store either a flat texture, an environment map, or a volumetric texture. Each of these can have multiple frames.

* An environment map is a six-faced [cube map](../cube-mapping.md).
* A volumetric texture is a texture with depth, where each frame is a "layer" which are layered in the third dimension. So a 16x16x16 volumetric texture has 16 separate 16x16 textures stacked to give depth. This format is used internally by Source, and you shouldn't have any need to actually create one yourself.
* For each frame and face, the VTF file contains both the basic original source-image data \(pixel map\) and a series of [**mipmaps** ](../mip-mapping.md)used for rendering the texture over varying distances. Because each successive mipmap is exactly 1/2 the dimension \(height and width\) of the previous one, the source-image dimensions must be a multiple of 4. Although the source-image may be rectangular, square mipmaps are stored more efficiently in the VTF.
* Start frame \(for animations\)
* **Bump map** scale
* A **Reflectivity** value for use by **VRAD**
* A very low resolution copy of the VTF for color sampling by the engine.

### Resources

VTF 7.3 added an extensible "resource data" system. Anything can be added, but Source will recognise only the following:

* A **CRC** value, for detecting data corruption.
* An **U/V** LOD control. This is the highest mipmap which should be loaded when game's Texture Detail setting is "High" \(`mat_picmip 0`\). An U LOD Control value of 11 selects the mipmap which is 2048 pixels \(211\) across.

{% hint style="info" %}
Since users are currently only presented with one texture detail setting above High, there is little point setting this value to anything except 50% or 100% of your texture's size.
{% endhint %}

* \*\*\*\*[**Animated particle sheet**](animated-particles.md) data.
* Expanded texture settings. This is a collection of 32 flags, none of which are in use by Valve. Unlike the built-in VTF flags these can be defined on a game-by-game basis.

## Image data formats

The VTF image format can store image data in a variety of formats. Some formats were meant for the engine, some only as an interim format for conversions. The uncompressed formats are not lossy and the compressed \(DXT\) formats are.

![](https://developer.valvesoftware.com/w/images/c/cc/Note.png) **Note:**The VTF format can actually store many more formats than those listed below -- consult your engine branch's `public/bitmap/imageformat.h` to see exactly what it supports. However, these formats are not GUARANTEED to work and their enum values are prone to being shuffled around between engine branches.

### Image data format table

| Format | Red Bits | Green Bits | Blue Bits | Alpha Bits | Total Bits | Compresses | Supported | Comments |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| A8 | 0 | 0 | 0 | 8 | 8 | False | True |  |
| ABGR8888 | 8 | 8 | 8 | 8 | 32 | False | True | Uncompressed texture with alpha |
| ARGB8888 | 8 | 8 | 8 | 8 | 32 | False | True |  |
| BGR565 | 5 | 6 | 5 | 0 | 16 | False | True | Uncompressed texture, limited color depth |
| BGR888 | 8 | 8 | 8 | 0 | 24 | False | True | Uncompressed texture |
| BGR888\_BLUESCREEN | 8 | 8 | 8 | 0 | 24 | False | True |  |
| BGRA4444 | 4 | 4 | 4 | 4 | 16 | False | True | Uncompressed texture with alpha, half color depth |
| BGRA5551 | 5 | 5 | 5 | 1 | 16 | False | True |  |
| BGRA8888 | 8 | 8 | 8 | 8 | 32 | _Either_ | True | Also used for compressed HDR |
| BGRX5551 | 5 | 5 | 5 | 1 | 16 | False | True |  |
| BGRX8888 | 8 | 8 | 8 | 8 | 32 | False | True |  |
| DXT1 | N/A | N/A | N/A | 0 | 4 | True | True | Standard compression, no alpha |
| DXT1\_ONEBITALPHA | N/A | N/A | N/A | 1 | 4 | True | True | Standard compression, one bit alpha |
| DXT3 | N/A | N/A | N/A | 4 | 8 | True | True | Uninterpolated Alpha |
| DXT5 | N/A | N/A | N/A | 8 | 8 | True | True | Interpolated Alpha \(recommended\) |
| I8 | N/A | N/A | N/A | N/A | 8 | False | True | Luminance \(Grayscale\) |
| IA88 | N/A | N/A | N/A | 8 | 16 | False | True | Luminance \(Grayscale\) |
| P8 | N/A | N/A | N/A | N/A | 8 | False | False | Paletted |
| RGB565 | 5 | 6 | 5 | 0 | 16 | False | True |  |
| RGB888 | 8 | 8 | 8 | 0 | 24 | False | True |  |
| RGB888\_BLUESCREEN | 8 | 8 | 8 | 0 | 24 | False | True |  |
| RGBA16161616 | 16 | 16 | 16 | 16 | 64 | False | True | Integer HDR Format |
| RGBA16161616F | 16 | 16 | 16 | 16 | 64 | False | True | Floating Point HDR Format |
| RGBA8888 | 8 | 8 | 8 | 8 | 32 | False | True |  |
| UV88 | N/A | N/A | N/A | N/A | 16 | False | True | Uncompressed du/dv Format |
| UVLX8888 | N/A | N/A | N/A | N/A | 32 | False | True |  |
| UVWQ8888 | N/A | N/A | N/A | N/A | 32 | False | True |  |

**HDR compression**

HDR textures can be stored in compressed form using the BGRA8888 format.

The formula to convert these colors back to integer HDR is:

`RGB = RGB * (A * 16)`

and for floating point HDR:

`RGB = (RGB * (A * 16)) / 262144`

### Choosing an image format

Though the VTF image format provides support for a wide range of image data formats, there are only a handful of image data formats you are likely to use. These formats and their criteria are described below:

* **BGR888:** use this format for textures with no alpha channel and very fine gradients \(i.e. normal maps or light halos\).
* **BGRA8888:** use this format for textures with an alpha channel and very fine gradients \(i.e. normal maps or light halos\). It can also be used to produce Very High quality textures.
* **DXT1:** use this format for typical textures with no alpha channel. \(Also known as BC1.\)
  * **Note:** DXT1 supports 1 bit of alpha precision. **However**, any areas of 0 alpha will be fully black. This functionality is therefore best used for textures using $alphatest.
* **DXT3:** **DXT5 should almost always be used over DXT3**, but DXT3 is acceptable \(not necessarily better\) for textures with an alpha channel with sharp gradients. \(Also known as BC2.\)
* **DXT5:** use this format for typical textures with an alpha channel. \(Also known as BC3\).
* **I8:** use this format for black and white textures with no alpha channel and very fine gradients \(i.e. light halos\).
* **IA88:** use this format for black and white textures with an alpha channel and very fine gradients \(i.e. smoke or light halos\).
* **RGBA16161616F:** use this format for **HDR** textures.
* **UV88:** use this format for **DuDv** maps.

Find technical details on the various DXT compression formats here and here.

## Image flags

**Tip:**Most shader settings are configured as material parameters, not texture flags.

A VTF file can contain the following flags \(version 7.5\):

| Flag |  **Value** |  **Comment** |
| :--- | :--- | :--- |
| Point Sampling | 0x0001 | Low quality, "pixel art" texture filtering. |
| Trilinear Sampling | 0x0002 | Medium quality texture filtering. |
| Clamp S | 0x0004 | Clamp S coordinates. |
| Clamp T | 0x0008 | Clamp T coordinates. |
| Anisotropic Sampling | 0x0010 | High quality texture filtering. |
| Hint DXT5 | 0x0020 | Used in [skyboxes](../skybox-basics/). Makes sure edges are seamless. |
| PWL Corrected | 0x0040 | Purpose unknown. |
| SRGB | n/a | Uses space RGB. Useful for High Gamuts. Deprecated in 7.5. |
| No Compress | 0x0040 | No DXT compression used. Deprecated |
| Normal Map | 0x0080 | Texture is a normal map. |
| No Mipmaps | 0x0100 | Render largest mipmap only. \(Does not delete existing mipmaps, just disables them.\) |
| No Level Of Detail | 0x0200 | Not affected by texture resolution settings. |
| No Minimum Mipmap | 0x0400 | If set, load mipmaps below 32x32 pixels. |
| Procedural | 0x0800 | Texture is an procedural texture \(code can modify it\). |
| One Bit Alpha | 0x1000 | One bit alpha channel used. |
| Eight Bit Alpha | 0x2000 | Eight bit alpha channel used. |
| Environment Map | 0x4000 | Texture is an environment map. |
| Render Target | 0x8000 | Texture is a render target. |
| Depth Render Target | 0x10000 | Texture is a depth render target. |
| No Debug Override | 0x20000 |  |
| Single Copy | 0x40000 |  |
| Pre SRGB | 0x80000 | SRGB correction has already been applied |
| One Over Mipmap Level In Alpha | 0x80000 | Fill the alpha channel with 1/Mipmap Level. Deprecated \(Internal to VTEX?\) |
| Premultiply Color By One Over Mipmap Level | 0x100000 | \(Internal to VTEX?\) |
| Normal To DuDv | 0x200000 | Texture is a DuDv map. \(Internal to VTEX?\) |
| Alpha Test Mipmap Generation | 0x400000 | \(Internal to VTEX?\) |
| No Depth Buffer | 0x800000 |  Do not **buffer** for Video Processing, generally render distance. |
| Nice Filtered | 0x1000000 |  Use **NICE filtering** to generate mipmaps. \(Internal to VTEX?\) |
| Clamp U | 0x2000000 | Clamp U coordinates \(for volumetric textures\). |
| Vertex Texture | 0x4000000 | Usable as a vertex texture |
| SSBump | 0x8000000 |  Texture is a **SSBump**. \(SSB\) |
| Border | 0x20000000 | Clamp to border colour on all texture coordinates |

## File format

The VTF image format is described as follows.

### VTF layout

{% tabs %}
{% tab title="Version 7.2" %}
1. VTF Header
2. VTF Low Resolution Image Data
3. For Each Mipmap \(Smallest to Largest\)
   * For Each Frame \(First to Last\)
     * For Each Face \(First to Last\)
       * For Each Z Slice \(Min to Max; Varies with Mipmap\)
         * VTF High Resolution Image Data
{% endtab %}

{% tab title="Version 7.3 +" %}
1. VTF Header
2. Resource entries
   * VTF Low Resolution Image Data
   * Other [resource data](./#resources)
   * For Each Mipmap \(Smallest to Largest\)
     * For Each Frame \(First to Last\)
       * For Each Face \(First to Last\)
         * For Each Z Slice \(Min to Max; Varies with Mipmap\)
           * VTF High Resolution Image Data
{% endtab %}
{% endtabs %}

### VTF enumerations

```text
enum
{
	IMAGE_FORMAT_NONE = -1,
	IMAGE_FORMAT_RGBA8888 = 0,
	IMAGE_FORMAT_ABGR8888,
	IMAGE_FORMAT_RGB888,
	IMAGE_FORMAT_BGR888,
	IMAGE_FORMAT_RGB565,
	IMAGE_FORMAT_I8,
	IMAGE_FORMAT_IA88,
	IMAGE_FORMAT_P8,
	IMAGE_FORMAT_A8,
	IMAGE_FORMAT_RGB888_BLUESCREEN,
	IMAGE_FORMAT_BGR888_BLUESCREEN,
	IMAGE_FORMAT_ARGB8888,
	IMAGE_FORMAT_BGRA8888,
	IMAGE_FORMAT_DXT1,
	IMAGE_FORMAT_DXT3,
	IMAGE_FORMAT_DXT5,
	IMAGE_FORMAT_BGRX8888,
	IMAGE_FORMAT_BGR565,
	IMAGE_FORMAT_BGRX5551,
	IMAGE_FORMAT_BGRA4444,
	IMAGE_FORMAT_DXT1_ONEBITALPHA,
	IMAGE_FORMAT_BGRA5551,
	IMAGE_FORMAT_UV88,
	IMAGE_FORMAT_UVWQ8888,
	IMAGE_FORMAT_RGBA16161616F,
	IMAGE_FORMAT_RGBA16161616,
	IMAGE_FORMAT_UVLX8888
};
```

```text
enum CompiledVtfFlags
{
	// Flags from the *.txt config file
	TEXTUREFLAGS_POINTSAMPLE = 0x00000001,
	TEXTUREFLAGS_TRILINEAR = 0x00000002,
	TEXTUREFLAGS_CLAMPS = 0x00000004,
	TEXTUREFLAGS_CLAMPT = 0x00000008,
	TEXTUREFLAGS_ANISOTROPIC = 0x00000010,
	TEXTUREFLAGS_HINT_DXT5 = 0x00000020,
	TEXTUREFLAGS_PWL_CORRECTED = 0x00000040,
	TEXTUREFLAGS_NORMAL = 0x00000080,
	TEXTUREFLAGS_NOMIP = 0x00000100,
	TEXTUREFLAGS_NOLOD = 0x00000200,
	TEXTUREFLAGS_ALL_MIPS = 0x00000400,
	TEXTUREFLAGS_PROCEDURAL = 0x00000800,

	// These are automatically generated by vtex from the texture data.
	TEXTUREFLAGS_ONEBITALPHA = 0x00001000,
	TEXTUREFLAGS_EIGHTBITALPHA = 0x00002000,

	// Newer flags from the *.txt config file
	TEXTUREFLAGS_ENVMAP = 0x00004000,
	TEXTUREFLAGS_RENDERTARGET = 0x00008000,
	TEXTUREFLAGS_DEPTHRENDERTARGET = 0x00010000,
	TEXTUREFLAGS_NODEBUGOVERRIDE = 0x00020000,
	TEXTUREFLAGS_SINGLECOPY	= 0x00040000,
	TEXTUREFLAGS_PRE_SRGB = 0x00080000,
        
        TEXTUREFLAGS_UNUSED_00100000 = 0x00100000,
	TEXTUREFLAGS_UNUSED_00200000 = 0x00200000,
	TEXTUREFLAGS_UNUSED_00400000 = 0x00400000,

	TEXTUREFLAGS_NODEPTHBUFFER = 0x00800000,

	TEXTUREFLAGS_UNUSED_01000000 = 0x01000000,

	TEXTUREFLAGS_CLAMPU = 0x02000000,
	TEXTUREFLAGS_VERTEXTEXTURE = 0x04000000,
	TEXTUREFLAGS_SSBUMP = 0x08000000,			

	TEXTUREFLAGS_UNUSED_10000000 = 0x10000000,

	TEXTUREFLAGS_BORDER = 0x20000000,

	TEXTUREFLAGS_UNUSED_40000000 = 0x40000000,
	TEXTUREFLAGS_UNUSED_80000000 = 0x80000000,
};
```

### VTF header

```text
typedef struct tagVTFHEADER
{
	char		signature[4];		// File signature ("VTF\0"). (or as little-endian integer, 0x00465456)
	unsigned int	version[2];		// version[0].version[1] (currently 7.2).
	unsigned int	headerSize;		// Size of the header struct  (16 byte aligned; currently 80 bytes) + size of the resources dictionary (7.3+).
	unsigned short	width;			// Width of the largest mipmap in pixels. Must be a power of 2.
	unsigned short	height;			// Height of the largest mipmap in pixels. Must be a power of 2.
	unsigned int	flags;			// VTF flags.
	unsigned short	frames;			// Number of frames, if animated (1 for no animation).
	unsigned short	firstFrame;		// First frame in animation (0 based).
	unsigned char	padding0[4];		// reflectivity padding (16 byte alignment).
	float		reflectivity[3];	// reflectivity vector.
	unsigned char	padding1[4];		// reflectivity padding (8 byte packing).
	float		bumpmapScale;		// Bumpmap scale.
	unsigned int	highResImageFormat;	// High resolution image format.
	unsigned char	mipmapCount;		// Number of mipmaps.
	unsigned int	lowResImageFormat;	// Low resolution image format (always DXT1).
	unsigned char	lowResImageWidth;	// Low resolution image width.
	unsigned char	lowResImageHeight;	// Low resolution image height.

	// 7.2+
	unsigned short	depth;			// Depth of the largest mipmap in pixels.
						// Must be a power of 2. Is 1 for a 2D texture.

	// 7.3+
	unsigned char	padding2[3];		// depth padding (4 byte alignment).
	unsigned int	numResources;		// Number of resources this vtf has. The max appears to be 32.
} VTFHEADER;
```

### VTF Resource Entry

```text
struct ResourceEntryInfo {
	unsigned char	tag[3]; 		// A three-byte "tag" that identifies what this resource is.
	unsigned char	flags;			// Resource entry flags. The only known flag is 0x2, which indicates that no data chunk corresponds to this resource.
	unsigned int	offset;			// The offset of this resource's data in the file. 
};
```

#### Tags

```text
{ '\x01', '\0', '\0' } - Low-res (thumbnail) image data.
{ '\x30', '\0', '\0' } - High-res image data.
{ '\x10', '\0', '\0' } - Animated particle sheet data.
{ 'C', 'R', 'C' } - CRC data.
{ 'L', 'O', 'D' } - Texture LOD control information.
{ 'T', 'S', 'O' } - Game-defined "extended" VTF flags.
{ 'K', 'V', 'D' } - Arbitrary KeyValues data.
```

### VTF lo-res image data

Tightly packed low resolution image data in the format described in the header. The low resolution image data is always stored in the DXT1 compressed image format. Its dimensions are that of the largest mipmap with a width or height that does not exceed 16 pixels. i.e. for a 256x256 pixel VTF: 16x16, for a 256x64 pixel VTF: 16x4, for a 1x32 pixel VTF: 1x16, for a 4x4 pixel VTF: 4x4.

### VTF hi-res image data

Tightly packed interleaved high resolution image data in the format described in the header. Common image formats include DXT1, DXT5, BGR888, BGRA8888 and UV88. All dimensions must be a multiple of 4.

### Version history

**To do:** Address game-specific compatibility issues

#### **v7.5**

* Released July 19th, 2010 as part of **Alien Swarm**
* Bitwise equivalent to v7.4.
* Redefines and revises two texture flags.
* Spheremaps now officially redundant.
* Most changes internal to the VTF creation process with VTEX, e.g. [MipMap ](../mip-mapping.md)fading, Alpha decay and XBox360 formats.

#### **v7.4**

* Released October 10th, 2007 as part of [The Orange Box](http://en.wikipedia.org/wiki/The_Orange_Box).
* Bitwise equivalent to v7.3.
* Addresses issues related to how gamma-correction is performed on textures for TV-output on XBOX 360 combined with hunting down OS Paged Pool Memory.

#### **v7.3**

* Added an extensible resource orientated structure.
* Added CRC, Texture LOD Control and Sheet resources, along with backwards compatible Image and Low Resolution Image resources.
* Added several vendor specific depth-stencil formats \(for internal engine use\), along with normal map formats and linear uncompressed formats.
* Released September 18th, 2007 as part of the [Team Fortress 2](https://developer.valvesoftware.com/wiki/Team_Fortress_2) beta.

#### **v7.2**

* Added volumetric texture support.
* Released September 23rd, 2005 as a [Steam](https://developer.valvesoftware.com/wiki/Steam) engine update.

#### **v7.1**

* Added spheremap support to environment maps. \(This was intended for DirectX 6 support which was later cut.\)

#### **v7.0**

* Initial release. \(Internal release only, however, some v7.0 textures made it to the published title.\)

#### Implementation

An example Steam independent implementation of the VTF image file format can be found in the LGPL C/C++ library [VTFLib](https://developer.valvesoftware.com/wiki/VTFLib).

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Valve\_Texture\_Format](https://developer.valvesoftware.com/wiki/Valve_Texture_Format)
{% endhint %}

