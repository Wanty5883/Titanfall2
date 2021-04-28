---
description: 替换铁驭模型指南
---

# 模型-铁驭类

{% hint style="danger" %}
注意：更改铁驭模型可能会破坏其动画甚至游戏崩溃。  
  
 然而，只改变手臂模型在任何情况下都能正常工作。
{% endhint %}

## 前期准备 <a id="preparation"></a>

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

要更改铁驭类模型，请进入以下文件目录：

> models\humans\pilots

如果要更改手臂模型，可以转到以下文件目录：

> models\weapons\arms

要更改所需的铁驭类型，首先查找链接到此类型的文件。然后选择你想要的类型并复制它们。然后将复制的文件重命名为您想要更改的类型的名称。

文件夹中的文件具有与其铁驭类型相对应的不同名称：

* pilot\_light\_jester = 兴奋剂铁驭
* pilot\_light\_ged = 相位铁驭
* pilot\_medium\_stalker = 幻影铁驭
* pilot\_medium\_reaper = 脉冲刀铁驭
* pilot\_medium\_geist = 钩爪铁驭
* pilot\_heavy\_roog = A盾铁驭
* pilot\_heavy\_drex = 隐身铁驭

文件末尾的_f_ & _m_ 对应每个铁驭类型的女性和男性版本。

## 重新打包 <a id="repacking"></a>

​[如何正确地重新打包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack#ru-he-zheng-que-di-zhong-xin-da-bao-vpk)​

在按步骤完成了上方链接的内容之后：

把pak000\_000.vpk重命名为**client\_mp\_common.bsp.pak000\_000.vpk**

把pak000\_dir.vpk重命名为**englishclient\_mp\_common.bsp.pak000\_dir.vpk**

将两个重命名完成的文件放回下面所示的文件夹之中并覆盖文件，然后启动《泰坦陨落2》。你就能看见修改后铁驭模型了！

> Origin Games\Titanfall2\vpk\

