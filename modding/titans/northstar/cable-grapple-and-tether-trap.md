---
description: 钩爪和拌索陷阱纹理修改指南
---

# 线缆-钩爪和绊索陷阱

## 前期准备 <a id="preparation"></a>

在本指南中，你需要去编辑vmt文件。我建议你使用软件VTFEdit来编辑它们。你也可以使用其他文本编辑器，例如Atom、NotePad++、VIM和许多其他编辑器都可以。（系统自带的记事本也可以）

进入以下目录并找到所需的VPK文件:

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)​

## 解包 <a id="unpacking"></a>

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[如何正确地解包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)​

## 编辑

要编辑钩爪和拌索陷阱线缆的纹理，请进入下面的文件夹：

> materials\cable

用VTFEdit打开文件 _`grapple_col.vtf`_ ，编辑这个纹理文件将更改钩爪和拌索陷阱线缆所使用的纹理效果。

[如何编辑何动态纹理颜色](https://noskill.gitbook.io/titanfall2/v/chinese/information/textures/colors/color-and-texture-info#how-to-edit-animated-texture-color)

## 重新打包 <a id="repacking"></a>

​​[如何正确的重新打包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack#ru-he-zheng-que-di-zhong-xin-da-bao-vpk)​​

在按步骤完成了上方链接的内容之后：

重命名 pak000\_000.vpk _为_ **client\_mp\_common.bsp.pak000\_000.vpk**

重命名 pak000\_dir.vpk _为_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

将两个重命名完成的文件放回下面所示的文件夹之中并覆盖文件，然后启动《泰坦陨落2》。你就能看见修改后游戏效果了！

> Origin Games\Titanfall2\vpk\

