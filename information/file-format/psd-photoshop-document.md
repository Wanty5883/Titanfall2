---
description: >-
  PSD, Photoshop Document, represents Adobe Photoshop's native file format used
  for graphics designing and development.
---

# PSD-Photoshop文档

PSD, Photoshop Document, represents Adobe Photoshop's native file format used for graphics designing and development. PSD files may include image layers, adjustment layers, layer masks, annotations, file information, keywords and other Photoshop-specific elements. Photoshop files have default extension as .PSD and has a maximum height and width of 30,000 pixels, and a length limit of two gigabytes.

## 文件格式规范

Data in a PSD file is stored in big endian byte order. This implies swapping the short and long integers when reading or writing on Windows platform. The Photoshop file format is divided into five major parts. It has many length markers that can be used to move from one section to the next. The length markers are usually padded with bytes to round to the nearest 2 or 4 byte interval. The five major parts are:

* File Header
* Color Mode Data
* Image Resources
* Layer and Mask Information
* Image Data

For conformance, data should be written to all these fields in the section, as Photoshop may try to read the entire section. It also implies that zeroes be written to skipped fields while writing to a file. The length field in the length-delimited sections should be used to decide when to stop reading. In most cases, the length field indicates the number of bytes, not records, following. The following points need to be remembered while reading a file.

* The values in "Length" column in all tables are in bytes.
* All values defined as Unicode string consist of:
* A 4-byte length field, representing the number of characters in the string \(not bytes\).
* The string of Unicode values, two bytes per character.

## 文件头

The file header contains the basic properties of the image.

| Length | Description |
| :--- | :--- |
| 4 | Signature: always equal to '8BPS' . Do not try to read the file if the signature does not match this value. |
| 2 | Version: always equal to 1. Do not try to read the file if the version does not match this value. \(\*\*PSB\*\* version is 2.\) |
| 6 | Reserved: must be zero. |
| 2 | The number of channels in the image, including any alpha channels. Supported range is 1 to 56. |
| 4 | The height of the image in pixels. Supported range is 1 to 30,000. |
| 4 | The width of the image in pixels. Supported range is 1 to 30,000. |
| 2 | Depth: the number of bits per channel. Supported values are 1, 8, 16 and 32. |
| 2 | The color mode of the file. Supported values are: Bitmap = 0; Grayscale = 1; Indexed = 2; RGB = 3; CMYK = 4; Multichannel = 7; Duotone = 8; Lab = 9. |

## 颜色模式数据部分

The color mode data section is structured as follows:

| Length | Description |
| :--- | :--- |
| 4 | The length of the following Color data |
| variable | The color data |

Color mode data is available only for indexed color and duotone as defined by the mode field in the File Header section. For all other modes, this section is represented by 4-byte zeroed values. For Indexed color images, the length is 768 and the color data contains the color table for the image, in non-interleaved order. For Duotone images, color data contains the duotone specification \(the format of which is not documented\). Other applications that read Photoshop files can treat a duotone image as a gray image, and just preserve the contents of the duotone information when reading and writing the file.

## 图像资源部分

The third section of the file contains image resources. It starts with a length field, followed by a series of resource blocks.

| Length | Description |
| :--- | :--- |
| 4 | Length of image resource section. The length may be zero. |
| Variable | Image Resources \(Image Resource Blocks\) |

Image resources are used to store non-pixel data associated with images such as pen tool paths. They are referred to as resource blocks because they hold data that was stored in the Macintosh's resource in early versions of Photoshop.The basic structure of image resource blocks is as shown below:

| Length | Description |
| :--- | :--- |
| 4 | Signature: '8BIM' |
| 2 | Unique identifier for the resource. Image resource IDs contains a list of resource IDs used by Photoshop. |
| Variable | Name: Pascal string, padded to make the size even \(a null name consists of two bytes of 0\) |
| 4 | Actual size of resource data that follows |
| Variable | The resource data, described in the sections on the individual resource types. It is padded to make the size even. |

Image resources use several standard ID numbers.

## 图层和遮罩信息

The fourth section of a Photoshop file contains information about layers and masks such as number of layers, channels in the layers, blending ranges, adjustment layer keys, effects layers, and mask parameters. If there are no layers or masks, this section is represented by zeroed 4-byte field. Special attention needs to be paid to the length of sections while reading this section due to the zeroed values. The arrangement of Layer and Mask section is as follow:

| Length | Description |
| :--- | :--- |
| 4 | Length of the layer and mask information section. \(\*\*PSB\*\* length is 8 bytes.\) |
| Variable | Layer info |
| Variable | Global layer mask info |
| Variable | Series of tagged blocks containing various types of data. |

### **图层信息**

The following table shows the high-level organization of the layer information.

| Length | Description |
| :--- | :--- |
| 4 | Length of the layers info section, rounded up to a multiple of 2. \(\*\*PSB\*\* length is 8 bytes.\) |
| 2 | Layer count. If it is a negative number, its absolute value is the number of layers and the first alpha channel contains the transparency data for the merged result. |
| Variable | Information about each layer. See Layer records describes the structure of this information for each layer. |
| Variable | Channel image data. Contains one or more image data records for each layer. The layers are in the same order as in the layer information  |

## 图像数据

The image pixel data is contained in the Image Data section of the file. Arrangement of data in Image Data section is in planar order i.e. first all the red data, then all the green data, etc. Each plane is stored in scan-line order, with no pad bytes, The image data section is arrange in a format as shown in the following table.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Length</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">
        <p>Compression method:</p>
        <p>0 = Raw image data</p>
        <p>1 = RLE compressed the image data starts with the byte counts for all
          the scan lines (rows * channels), with each count stored as a two-byte
          value. The RLE compressed data follows, with each scan line compressed
          separately. The RLE compression is the same compression algorithm used
          by the Macintosh ROM routine PackBits , and the TIFF standard.</p>
        <p>2 = ZIP without prediction</p>
        <p>3 = ZIP with prediction.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Variable</td>
      <td style="text-align:left">The image data. Planar order = RRR GGG BBB, etc.</td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
Source: [https://wiki.fileformat.com/image/psd/](https://wiki.fileformat.com/image/psd/)  
Reference:

* [PSD File Format Specifications - By Adobe](https://www.adobe.com/devnet-apps/photoshop/fileformatashtml/#50577409_pgfId-1030196)
* [Adobe Photoshop File Format](https://en.wikipedia.org/wiki/Adobe_Photoshop#File_format)
{% endhint %}

