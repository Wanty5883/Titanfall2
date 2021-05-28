---
description: Vtex是一个用于转换TGA/PSD格式到 VTF格式的命令行工具
---

# Vtex

Valve Texture Tool，简称为 Vtex 是一个用于转换 [targa \(.tga\)](../../../../../../information/file-format/truevision-graphics-adapter-tga.md) 或 [Photoshop \(.psd\)](../../../../../../information/file-format/psd-photoshop-document.md) \(半条命橙盒版 SDK\)格式到可以用于起源引擎的 [Valve Texture Files \(.vtf\)](../../../../../../information/textures/valve-texture-format-vtf/)格式的[命令行](https://developer.valvesoftware.com/wiki/Command-line)工具。 它利用 [targa \(.tga\)](../../../../../../information/file-format/truevision-graphics-adapter-tga.md) 图像和一个可选编译参数列表来创建 [Valve Texture File \(.vtf\)](../../../../../../information/textures/valve-texture-format-vtf/) 格式的文件。

{% hint style="info" %}
**注解：**我们**推荐**使用 [**VTFEdit**](../vtfedit.md) 以代替VTEX。 VTFEdit拥有更友好的用户界面，更广泛的格式支持，能够再不重编译的情况下改变大多数的vtf的属性， 独立的预览查看器并能够直接地对[GCF（ **G**rid **C**ache **F**ile 网格缓存文件）](https://developer.valvesoftware.com/wiki/GCF)进行访问
{% endhint %}

VTFEdit 会让你的工作难度大大降低，但在某些特定情况下，你必须使用VTEX来完成某些任务。经典案例有：用 sprite sheet 修改或者创建VTF文件

{% page-ref page="../../../../../../information/textures/valve-texture-format-vtf/animated-particles.md" %}

## 基本用法

1. 确保 [Steam](https://developer.valvesoftware.com/wiki/Steam) 正在运行。
2. 将targa图像放置在`SteamApps/common/gamefolder/materialsrc/`文件夹中，其中`gamefolder`是当前游戏的根目录（如：`cstrike/dod/hl2/ hll2mp /tf`）。你也可以把图像放在这个文件夹的子文件夹中，让Vtex将自动从对应的`materials/`的子文件夹中编译纹理。（例如，将图像放置在`materialsrc/metal/`子文件夹中，Vtex将会从`materials/metal/`的子文件夹中编译纹理。）
3. 如果有必要的话，你可以编写一个包含一组[Vtex编译参数](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaayusPgFwEGXSZy-W-/v/chinese/how-to-start-modding/modding-introduction/modding-tools/source/vtf-and-vmt/vtex/vtex-compile-parameters/@drafts)的[文本\(.txt\)](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaayusPgFwEGXSZy-W-/v/chinese/information/file-format/txt-text-file/@drafts)文件。并赋予它与targa图像相同的名称\(扩展名.txt除外\)，并将其放在同一个文件夹中。如果您没有创建此列表，Vtex将在编译期间为您创建一个空列表。
4. Vtex可执行文件 \(Vtex.exe\) i位于 `/Steam/SteamApps/common/gamefolder/bin/` 文件夹， `gamefolder`是你游戏的根目录。 它可以通过以下两种方式之一来执行：通过简单的“拖放”方法（如下所述），或者是用[这里](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaayusPgFwEGXSZy-W-/v/chinese/how-to-start-modding/modding-introduction/modding-tools/source/vtf-and-vmt/vtex#firstHeading/@drafts)描述的更高级的命令提示方法。当然Steam必须在执行时保持运行。
5. 生成的Valve Texture File\(.vtf\)将会被编译到当前游戏的`materials/`文件夹中。例如，如果当前的游戏是[半条命2](https://developer.valvesoftware.com/wiki/Half-Life_2)，纹理文件将被编译到`SteamApps/common/Half-Life 2/hl2/materials/`文件夹中。如果targa图像位于子文件夹中，Vtex将会把纹理文件编译到相应的`materials/`的子文件夹中。如果该子文件夹不存在，Vtex将自动创建它。

### 拖放方法

拖放方法是最简单的使用Vtex的方法。只要拖拽要转换的targa图像的图标，或者它的编译参数列表（从`materialsrc/`文件夹）到Vtex可执行文件（Vtex.exe）的图标上，然后松开，Vtex就会自动编译纹理文件。

## Vtex 命令行界面的用法 <a id="firstHeading"></a>

除了拖放方法外，Vtex还可以通过命令行界面\(MS-DOS\)中的命令提示符执行。这将允许您使用其更高级的功能。您可以在编译纹理时提供额外的参数来创建基本的.vmt文件，当然还有其他的一些选项。

`vtex.exe` 的语法如下：

```text
vtex [-quiet] [-nopause] [-mkdir] [-shader ShaderName] [-vmtparam Param Value] texture1 texture2 ...
```

任何文件的扩展名都会被忽略。（你可以参考不存在的 texture1.asd，只要图像实际存在，就不会有问题）。

### 基本的 Vtex 用法 

[命令行](https://developer.valvesoftware.com/wiki/Command-line) 可以进行更好的说明：

可以利用Windows环境变量“`%sourcesdk%`”在命令行语句中轻松定位`vtex.exe`。这个变量需要包含Source SDK安装目录的位置。 

比如说，为了编译半条命2一个叫在"`sourcesdk_content/hl2/materialsrc/metal`"文件夹内，叫"`sample_material.tga`"的纹理你需要打开一个命令提示符，切换目录（cd）到  
 "`sourcesdk_content/hl2/materialsrc/metal`" ，然后再命令行输入以下内容：

```text
"%sourcesdk%\bin\vtex" sample_material.tga
```

编译后的 .vtf 文件将会被放到这个文件夹内 \(假设 **Half-Life 2** 是你当前需要修改的游戏\)：

```text
SteamApps\username\half-life 2\hl2\materials\metal
```

{% hint style="info" %}
 **注解：**在打开命令提示符编译纹理之前，在**SDK启动器**或**VConfig**中正确设置**当前游戏**目录位置是非常重要的。**当前游戏**的改变不会影响任何已经打开的命令提示符窗口。这是由Windows使用环境变量的方法造成的。
{% endhint %}

### Vtex 命令

#### -mkdir

您可以在vtex中输入 -mkdir 命令，如果目标路径不存在，它将创建目标路径。例如，如果有一个tag文件路径是`/sourcesdk_content/hl2/materialsrc/sample/sample_material.Tga，`你可以在命令行输入这个：

```text
"%sourcesdk%\bin\vtex" -mkdir sample_material.tga
```

这将会在 你的 `Half-Life 2/hl2/materials` 文件夹中创建一个名为“`sample`”的新文件夹。（如果还不存在的话），然后编译完成的文件将会被放在这里。如果此目录已存在， `-mkdir` 参数将会被忽略。

#### -shader

你可以使用 `-shader <shadername>` 命令让Vtex为某一指定[着色器（shader）](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaayusPgFwEGXSZy-W-/v/chinese/information/textures/shader/@drafts)的新材质创建一个.VMT文件。举例来说，为了创建一个基本的 `LightmappedGeneric` 材质，请像这样使用 `-shader` 命令：

```text
"%sourcesdk%\bin\vtex" -shader LightmappedGeneric sample_material.tga
```

这将会在`half-life 2/hl2/materials/metal`中编译材质 sample\_material.vtf 并在同一路径创建一个新的材质文件 `sample_material.vmt` ，请像这样使用`LightmappedGeneric` 着色器：

```text
"LightmappedGeneric"
{
	"$baseTexture" "sample/lightmappedgeneric"
}
```

#### -vmtparam

您可以使用`-vmtparam <parameter> <value>` 命令来为创建的.vmt文件添加额外的材料参数。如果在同一位置已经存在.vmt，则不会添加任何新参数。例如，要使一个材料半透明，你需要输入以下内容：

```text
"%sourcesdk%\bin\vtex" -shader LightmappedGeneric -vmtparam $translucent 1 sample_material.tga
```

此命令会生成下面这个 `sample_material.vmt`:

```text
"LightmappedGeneric"
{
	"$baseTexture" "sample/lightmappedgeneric"
	"$translucent" 1
}
```

你也可以在同一个VTEX命令中添加多个 `-vmtparam` 语句，如下所示：

```text
"%sourcesdk%\bin\vtex" -shader LightmappedGeneric -vmtparam "$bumpmap" "sdk/bumpspecular_normal" -vmtparam "$envmap" "env_cubemap" sample_material.tga
```

这将会创建下面这个指定凹凸镜面材质参数的 `sample_material.vmt` ：

```text
 "LightmappedGeneric"
 {
 	"$baseTexture" "sample/sample_material"
 	"$bumpmap" "sdk/bumpspecular_normal"
 	"$envmap" "env_cubemap"
 }
```

#### -quiet

此命令会使VTEX在执行命令时不向控制台产生任何输出，且在完成时不会暂停。

#### -nopause

移除在VTEX结束工作时出现的 "`Hit a key to continue`" 信息。

#### -outdir

你可以使用 `-outdir <parameter> <value>` 命令覆盖VTF文件的输出目录。

#### -quickconvert

用于快速地将旧的 VTF 格式转换为较新的 VTF 格式。

#### -dontusegamedir

将输入输出文件放在同一个文件夹中，最好配合`-quickconvert`命令使用。

### 通配符

在VTEX中你也可以使用命令行通配符，下面的的案例中，这个命令将会编译当前目录下所有的.tga文件：

```text
"%sourcesdk%\bin\vtex" *.tga
```

这个命令将会编译当前目录下所有以“sample"开头的.tga文件：

```text
"%sourcesdk%\bin\vtex" sample*.tga
```

在这个情况下，文件 "`sample_metal`" 和 "`sample3`" 将会被编译，但是 "`samp_metal`" 或者 "`sampl_2`"不会。

### 链

Vtex可以从同一命令行编译多个材料，你只需要将每个.tga文件的名称一个接一个排在第一个后面即可，如下所示：

```text
"%sourcesdk%\bin\vtex" sample_material1.tga sample_material2.tga sample_material3.tga
```

如果你在命令行中使用`-shader`命令生成一个.vmt文件，那么链中的每个.tga都会创建一个专属的.vmt文件，其中所有的参数都由`-shader`和`-vmtparam`命令决定。如果你需要对每个.tga的着色器参数单独进行更多的调试，可以使用批处理\(.bat\)文件来多次运行vtex。

{% hint style="info" %}
源文档链接：

* [https://developer.valvesoftware.com/wiki/Vtex](https://developer.valvesoftware.com/wiki/Vtex)
* [https://developer.valvesoftware.com/wiki/Vtex\_CLI\_use](https://developer.valvesoftware.com/wiki/Vtex_CLI_use)
{% endhint %}

