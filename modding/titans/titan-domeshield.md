# 泰坦的穹顶护盾

## 前期准备

在本指南中，你需要去编辑vmt和vtf文件；我建议使用[VTFEdit](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)来编辑文件。要编辑vmt文件，你需要[VTFEdit](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)和用于编辑vtf文件的图像软件。你也可以使用任何文本编辑器，如Atom、NotePad++、VIM等（系统自带的记事本也行），或是使用带有VTF插件的软件来进行图像编辑，比如Gimp，Photoshop等等。

进入以下目录并找到所需的VPK文件:

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。[工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

## 解包

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[如何正确地解包文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

## 编辑

要编辑穹顶护盾的表面纹理，需要进入以下文件夹之中：

> \materials\effects\

穹顶护盾的纹理使用的是`black.vtf`，你可以修改此纹理或是创建新的纹理替换他。  
修改此纹理将影响游戏中的其他相关效果。

建议你创建一个新的纹理，这样就可以为游戏的特定部分定制效果。

想要挑选已有的纹理？你可以在[纹理库](../../assets/texture-library.md)中找到。选择你要使用的纹理，用[VTFEdit](../../how-to-start-modding/modding-introduction/modding-tools/source/vtf-and-vmt/vtfedit.md)编译它。 为保持文件完整性，将 [`.vtf`](../../information/textures/valve-texture-format-vtf/)文件重命名为`dome.vtf`。

对于相关参数，你可以使用与原始纹理相同的方法，也可以自己制作并测试！随时欢迎您将测试结果发送到我们的Discord服务器，我们可能会在wiki中添加您的成果！ ![](../../.gitbook/assets/08c0a077780263f3df97613e58e71744.svg) 

### 纹理应用

要将穹顶护盾的纹理更改为刚刚创建的纹理，需要进入以下文件夹之中：

> materials\models\fx\

打开`xo_shield_edgedetect.vmt` 文件，找到以下代码行，这两行代码就是你所想要更改的。

```text
"$basetexture" "effects\black"
"$Texture2" "effects\black"
```

修改`black` 为你所创建的 [`.vtf`](../../information/textures/valve-texture-format-vtf/) 文件，在本例中是dome。

```text
"$basetexture" "effects\dome"
"$Texture2" "effects\dome"
```

{% hint style="info" %}
Color can be changed. If the texture is black then the color applied in your [material file](../../information/textures/valve-material-type-vmt.md) will be accurate. If the texture is not black, then the color won't be accurate as the starting point is no longer the set color. Find more information on this [page](../../information/textures/colors/) about colors in material files.
{% endhint %}

### 样例

![domeshield texture replaced with doge. &quot;$color2&quot; &quot;\[5 5 5\]&quot;](../../.gitbook/assets/titanfall-2-screenshot-2020.03.11-19.41.56.68.png)

## 重新打包

​[如何正确地重新打包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack#ru-he-zheng-que-di-zhong-xin-da-bao-vpk)​

在按步骤完成了上方链接的内容之后：

把pak000\_000.vpk重命名为**client\_mp\_common.bsp.pak000\_000.vpk**

把pak000\_dir.vpk重命名为**englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Pl将两个重命名完成的文件放回下面所示的文件夹之中并覆盖文件，然后启动《泰坦陨落2》。你就能看见修改后的泰坦穹顶护盾了！

> Origin Games\Titanfall2\vpk\

