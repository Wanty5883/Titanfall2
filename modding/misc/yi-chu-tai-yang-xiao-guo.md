# 移除太阳效果

## 前期准备

进入以下目录并找到所需的VPK文件（Origin端）:

> Origin Games\Titanfall2\vpk\

进入以下目录并找到所需的VPK文件（Steam端）:

> Steam\steamapps\common\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* `englishclient_frontend.bsp.pak000_dir.vpk`
* `client_frontend.bsp.pak000_000.vpk`

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

## 解包 <a id="unpacking"></a>

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Titanfall2\vpk\englishclient\_frontend.bsp.pak000\_dir.vpk

​[如何正确地解包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

## 编辑

太阳效果非常耀眼，它并没有真正增加太多的游戏体验，它是如此地明显，以至于你不得你低头。

![](../../.gitbook/assets/with-bloom.png)

举几个其他地图的例子，它同时也在遗迹，崛起，和系外行星中出现。

为了移除太阳闪耀的效果，在提取上文提到的VPK之后, 进入到解包文件夹下的 `\particles` 文件夹, 然后删除下面提到的三个文件:

`env_sun_red_dwarf.pcf`

`env_sun_haven.pcf`

`env_sun.pcf`

在修改完成后，你应该能够看到不至于让你瞎眼的太阳了。

![](../../.gitbook/assets/no-bloom.png)

## 重新打包 <a id="repacking"></a>

​[如何正确的重新打包VPK文件？​​](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack#ru-he-zheng-que-di-zhong-xin-da-bao-vpk)

在按步骤完成了上方链接的内容之后：

重命名 `pak000_000.vpk` _为_ `client_frontend.bsp.pak000_000.vpk`

重命名 `pak000_dir.vpk` _为_ `englishclient_frontend.bsp.pak000_dir.vpk`

将两个重命名完成的文件放回游戏目录之中并覆盖文件，然后启动《泰坦陨落2》。你就能看见修改后的游戏效果了！

