# TGA - Truevision Graphics Adapter

**Truevision Graphics Adapter** (**TGA**), commonly referred to as "targa" (Truevision Advanced Raster Graphics Adapter), is a non-proprietary image format from Truevision that is favoured by [Valve](https://developer.valvesoftware.com/wiki/Valve). The file extension for targas is `.tga`. It is the base format for [Valve Texture Files (.vtf)](../textures/valve-texture-format-vtf/), and used to store images used by the [Steam client](https://developer.valvesoftware.com/wiki/Category:Steam).

The format stores the basic RGB (red, green, blue) channels with 8 bit precision (0-255) each, for a total of 24 bits/pixel, with an optional additional 8 bit [alpha channel](https://developer.valvesoftware.com/wiki/Alpha\_channel), for a total of 32 bits/pixel. The extra channel contains information that the [VMT](../textures/valve-material-type-vmt.md) [shaders](https://developer.valvesoftware.com/wiki/Shader) can use for effects such as transparency or specularity.

Most Textures in Source start life as **TGAs** which are edited and adjusted with any suitable [image editor](../../how-to-start-modding/modding-introduction/modding-tools/#graphics-animation-color-editors). The TGA is then compiled into the Valve Texture Format ([VTF](../textures/valve-texture-format-vtf/)) using [Vtex](https://developer.valvesoftware.com/wiki/Vtex).exe (or a third-party tool such as [VTFEdit](../../how-to-start-modding/modding-introduction/modding-tools/#vtf-and-vmt)) to participate in the [Material System](https://developer.valvesoftware.com/wiki/Material\_System).

## History

The TGA file format was originally defined and specified by [AT\&T](https://en.wikipedia.org/wiki/AT%26T\_Corporation) EPICenter with feedback from Island Graphics Inc in 1984. AT\&T EPICenter was an internal spin-off of AT\&T created to market new technologies AT\&T had developed for color [frame buffers](https://en.wikipedia.org/wiki/Framebuffer). What later became Truevision was the result of a leveraged employee buyout from AT\&T in 1987.

## Technical details

All values are [little-endian](https://en.wikipedia.org/wiki/Endianness); field and subfield numbers are per Version 2.0 of the specification.

Version 2 added the extension area and footer. The developer area exists to store application-specific information.

### Header

| Field no. | Length   | Field name              | Description                     |
| --------- | -------- | ----------------------- | ------------------------------- |
| 1         | 1 byte   | ID length               | Length of the image ID field    |
| 2         | 1 byte   | Color map type          | Whether a color map is included |
| 3         | 1 byte   | Image type              | Compression and color types     |
| 4         | 5 bytes  | Color map specification | Describes the color map         |
| 5         | 10 bytes | Image specification     | Image dimensions and format     |

**Image ID length (field 1)**

0–255 The number of bytes that the image ID field consists of. The image ID field can contain any information, but it is common for it to contain the date and time the image was created or a serial number.

As of version 2.0 of the TGA spec, the date and time the image was created is catered for in the extension area.

**Color map type (field 2)**

has the value:

* 0 if image file contains no color map
* 1 if present
* 2–127 reserved by Truevision
* 128–255 available for developer use

**Image type (field 3)**

is enumerated in the lower three bits, with the fourth bit as a flag for RLE. Some possible values are:

* 0 no image data is present
* 1 uncompressed color-mapped image
* 2 uncompressed true-color image
* 3 uncompressed black-and-white (grayscale) image
* 9 run-length encoded color-mapped image
* 10 run-length encoded true-color image
* 11 run-length encoded black-and-white (grayscale) image

**Color map specification (field 4)**

has three subfields:

* First entry index (2 bytes): index of first color map entry that is included in the file
* Color map length (2 bytes): number of entries of the color map that are included in the file
* Color map entry size (1 byte): number of bits per pixel

In case that not the entire color map is actually used by the image, a non-zero first entry index allows to store only a required part of the color map in the file.

**Image specification (field 5)**

has six subfields:

* X-origin (2 bytes): absolute coordinate of lower-left corner for displays where origin is at the lower left
* Y-origin (2 bytes): as for X-origin
* Image width (2 bytes): width in pixels
* Image height (2 bytes): height in pixels
* Pixel depth (1 byte): bits per pixel
* Image descriptor (1 byte): bits 3-0 give the alpha channel depth, bits 5-4 give direction

### Image and color map data

| Field no. | Length                             | Field          | Description                                       |
| --------- | ---------------------------------- | -------------- | ------------------------------------------------- |
| 6         | From image ID length field         | Image ID       | Optional field containing identifying information |
| 7         | From color map specification field | Color map data | Look-up table containing color map data           |
| 8         | From image specification field     | Image data     | Stored according to the image descriptor          |

### Developer area (optional)

Version 1.0 of the TGA specification was very basic, and many developers had a need to store more information, and so opted to add on extra sections to their files, specific to their application only.

In Version 2.0 of the specification, these application-specific enhancements/extras are supported by the developer area. Only the offset and size of the developer area are relevant to the spec, and developers are free to add whatever they want in the area.

If a TGA decoder cannot interpret the information in the developer area, it will generally ignore it, since it is assumed to have been created by a different application. It is recommended that developers build logic into their applications to determine whether the data in the developer area is compatible with the application; one step towards this is to check the software ID in the file footer.

#### Extension area (optional)

| Field no. | Length    | Field                   | Description                                                                             |
| --------- | --------- | ----------------------- | --------------------------------------------------------------------------------------- |
| 10        | 2 bytes   | Extension size          | Size in bytes of the extension area, always 495                                         |
| 11        | 41 bytes  | Author name             | Name of the author. If not used, bytes should be set to NULL (\0) or spaces             |
| 12        | 324 bytes | Author comment          | A comment, organized as four lines, each consisting of 80 characters plus a NULL        |
| 13        | 12 bytes  | Date/time stamp         | Date and time at which the image was created                                            |
| 14        | 41 bytes  | Job ID                  |                                                                                         |
| 15        | 6 bytes   | Job time                | Hours, minutes and seconds spent creating the file (for billing, etc.)                  |
| 16        | 41 bytes  | Software ID             | The application that created the file.                                                  |
| 17        | 3 bytes   | Software version        |                                                                                         |
| 18        | 4 bytes   | Key color               |                                                                                         |
| 19        | 4 bytes   | Pixel aspect ratio      |                                                                                         |
| 20        | 4 bytes   | Gamma value             |                                                                                         |
| 21        | 4 bytes   | Color correction offset | Number of bytes from the beginning of the file to the color correction table if present |
| 22        | 4 bytes   | Postage stamp offset    | Number of bytes from the beginning of the file to the postage stamp image if present    |
| 23        | 4 bytes   | Scan line offset        | Number of bytes from the beginning of the file to the scan lines table if present       |
| 24        | 1 byte    | Attributes type         | Specifies the alpha channel                                                             |

### File footer (optional)

If a TGA file contains a footer, it is likely to be a TGA version 2 file. The footer is the final 26 bytes of the file, of which the last 18 are constant.

| Field no. | Length   | Field                 | Description                                    |
| --------- | -------- | --------------------- | ---------------------------------------------- |
| 28        | 4 bytes  | Extension offset      | Offset in bytes from the beginning of the file |
| 29        | 4 bytes  | Developer area offset | Offset in bytes from the beginning of the file |
| 30        | 16 bytes | Signature             | Contains "TRUEVISION-XFILE"                    |
| 31        | 1 byte   |                       | Contains "."                                   |
| 32        | 1 byte   |                       | Contains NULL                                  |

### Specification discrepancies

The older version of the TGA file format specification taken from the Appendix C of the Truevision Technical Guide states that run-length encoded (RLE) packets may cross scan lines: "For the run length packet, the header is followed by a single color value, which is assumed to be repeated the number of times specified in the header. The packet **may cross scan lines** (begin on one line and end on the next)".

However, page 24 of the TGA v2.0 specification states the exact opposite: "Run-length Packets **should never encode pixels from more than one scan line**. Even if the end of one scan line and the beginning of the next contain pixels of the same value, the two should be encoded as separate packets. In other words, Run-length Packets should not wrap from one line to another".

Consequently TGA readers need to be able to handle RLE data packets that cross scan lines since this was part of the original specification. However, when saving (creating) TGA files it will be necessary to limit RLE data packets to scanline boundaries in order to be compliant with the newer v2.0 TGA specification.

## Targa for [Vtex](https://developer.valvesoftware.com/wiki/Vtex)

### Valid format

For a targa image to be recognized as valid by Vtex, it must meet the following criteria:

* It must be 24 or 32 bits/pixel in depth. (16 bits/pixel is not recognized.)
* Its dimensions (height and width) must have a pixel size equal to a power of 2. (i.e. 2^4=16, 2^5=32, 2^6=64, 2^7=128, 2^8=256, 2^9=512, etc.)
* Its dimensions can not be bigger than 2048 pixels.
* The height and width doesn't need to be the same - 64x128, 256x512 works fine - but square images are preferred by the Source engine, so use them whenever possible, even when it doesn't seem like the best way to go.
* RLE compression is optional, but should be avoided due to occasional conversion troubles.

### Scale

The default texture scale in Hammer is `0.25`. This means that 1 texture pixel = 0.25 [map units](https://developer.valvesoftware.com/wiki/Dimensions) in Hammer and in game, or a 512x512 texture covers 128x128 map units (equivalent to 8x8 feet or 2.4x2.4 meters).

&#x20;Relative [Dimensions](https://developer.valvesoftware.com/wiki/Dimensions) for (Default) Texture Scale 0.25

| Texture     | Hammer    | FileSize     |                                                                                                                                                                                                             |
| ----------- | --------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| pixels      | map units | kB (32bit)   |                                                                                                                                                                                                             |
| 4 x 4       | 1 x 1     | 0.06         |                                                                                                                                                                                                             |
| 8 x 8       | 2 x 2     | 0.25         |                                                                                                                                                                                                             |
| 16 x 16     | 4 x 4     | 1            |                                                                                                                                                                                                             |
| 32 x 32     | 8 x 8     | 4            |                                                                                                                                                                                                             |
| 64 x 64     | 16 x 16   | 16           |                                                                                                                                                                                                             |
| 128 x 128   | 32 x 32   | 64           |                                                                                                                                                                                                             |
| 256 x 256   | 64 x 64   | 256          |                                                                                                                                                                                                             |
| 512 x 512   | 128 x 128 | 1024 (1MB)   | This is the most common size for archictextures : brickwork, concrete, etc.                                                                                                                                 |
| 1024 x 1024 | 256 x 256 | 4096 (4MB)   |                                                                                                                                                                                                             |
| 2048 x 2048 | 512 x 512 | 16384 (16MB) | This is the largest size that [vtex](https://developer.valvesoftware.com/wiki/Vtex) can cope with and is only used for large non-tiling brushes like [2D skyboxes](../textures/skybox-basics/2d-skybox.md). |

* **Texture (pixels)** : Square format is preferred but rectangles are acceptable. Each dimension must be a power of two upto 2048.
* **Hammer (map units)** : using the default Texture Scale of 0.25. This can be overridden locally per surface in Hammer or per material by using the [$basetexturetransform](https://developer.valvesoftware.com/wiki/$basetexturetransform) scale factor in the [VMT](../textures/valve-material-type-vmt.md). For example A 512x512 texture with a scale of 0.5 will cover only 64x64 map units, and when viewed up close should appear highly detailed.
* **Filesize (kB)** : is given for 32bit uncompressed rasta image. **To do: **[VTF](../textures/valve-texture-format-vtf/) uses it's own compression system ...

**Note:**3D Skybox scale is 1/16th of map scale, so textures for 3D skybox surfaces should be designed accordingly.

### Save location

Remember that Vtex is only able to locate targa images located inside the `/materialsrc/` folder of the current game, so you may want to save it there directly to spare you the trouble of having to move it there later.

{% hint style="info" %}
Source:

* [https://en.wikipedia.org/wiki/Truevision\_TGA](https://en.wikipedia.org/wiki/Truevision\_TGA)
* [https://developer.valvesoftware.com/wiki/TGA](https://developer.valvesoftware.com/wiki/TGA)

Reference:

* &#x20;.tga [MIME](https://en.wikipedia.org/wiki/MIME) type not [registered](http://www.iana.org/assignments/media-types/media-types.xhtml#image) at [IANA](https://en.wikipedia.org/wiki/Internet\_Assigned\_Numbers\_Authority)
* James D. Murray, William vanRyper (April 1996). [Encyclopedia of Graphics File Formats, Second Edition](https://archive.org/details/mac\_Graphics\_File\_Formats\_Second\_Edition\_1996). [O'Reilly](https://en.wikipedia.org/wiki/O'Reilly\_Media). [ISBN](https://en.wikipedia.org/wiki/International\_Standard\_Book\_Number) [1-56592-161-5](https://en.wikipedia.org/wiki/Special:BookSources/1-56592-161-5). Retrieved 2014-03-07.
* ["Truevision TGAª — FILE FORMAT SPECIFICATION — Version 2.0"](http://www.dca.fee.unicamp.br/\~martino/disciplinas/ea978/tgaffs.pdf) (PDF).
* ["Truevision TGA, version 2.0"](http://www.digitalpreservation.gov/formats/fdd/fdd000180.shtml). Digital Preservation. [Library of Congress](https://en.wikipedia.org/wiki/Library\_of\_Congress). 2013-09-13. Retrieved 2014-03-11.
{% endhint %}
