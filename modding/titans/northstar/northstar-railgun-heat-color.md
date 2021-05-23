# 电浆磁轨炮-蓄力特效

## 前期准备 <a id="preparation"></a>

在本指南中，你需要去编辑vmt文件。我建议你使用软件VTFEdit来编辑它们。你也可以使用其他文本编辑器，例如Atom、NotePad++、VIM和许多其他编辑器都可以。（系统自带的记事本也可以）

进入以下目录并找到所需的VPK文件:

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接​](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

## 解包 <a id="unpacking"></a>

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[如何正确地解包VPK文件？​](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

## 编辑 <a id="editing"></a>

要编辑下面武器的枪焰特效，你需要找到对应的.vmt文件。在本指南中，你将进一步了解不同的文件位置以及可以进行哪些修改的详细信息。

You can edit the heat color, [here](https://noskill.gitbook.io/titanfall2/information/color-and-texture-info#usdlayercolor) more information about color and how to edit the way you like.

You can change the heat effect texture to any other texture in the game. Some texture would work, some wouldn't look good and some other texture would just not work. More info [here](https://noskill.gitbook.io/titanfall2/information/color-and-texture-info#usdtexture2-and-usdbasetexture) how to edit the texture value.

### Heat effect

For editing Northstar railgun heat effect, go to this location.

> \materials\models\weapons\_r2\titan\_plasma\_railgun

Open the file _`titan_sniper_charge_fx.vmt`_ and refer to the different info provided

#### 例子

{% embed url="https://gfycat.com/unlawfulcompetentfairybluebird" %}

{% embed url="https://gfycat.com/infantilescholarlyaracari" %}

## 重新打包 <a id="repacking"></a>

​[How to repack VPK files proprely ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

