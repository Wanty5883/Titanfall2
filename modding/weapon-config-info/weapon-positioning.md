---
description: 武器在屏幕上的位置
---

# 武器定位

## 前期准备

进入以下目录并找到所需的VPK文件:

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。​[工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

## 解包

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

[如何正确地解包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

## 编辑

进入下面的解包目录

> \scripts\weapons

这个文件夹包含所有武器的"配置文件"，修改文件所产生的风险由你自己承担。如果因为你修改核心数值而导致的账号封禁，别把责任归咎于我。

在文件中找到这部分代码：

```text
MP_BASE
	{
```

要在其中添加以下命令：

```text
"viewmodel_offset_hip" 						"x z y"
```

所以它应该是这样的：

```text
MP_BASE
	{	"viewmodel_offset_hip" 						"x z y" 
```

### 位置数值

每个坐标的标准值为“0”。

“X”值为正会使武器移到右边，为负则移到左边。

“Z”值为正会使武器向前移动，为负则向后移动。

“Y”值为正会使武器向上移动，为负则向下移动。

### 样例

![&quot;viewmodel\_offset\_hip&quot; 						&quot;-10 0 -3&quot;](../../.gitbook/assets/another-kraber-edit.jpg)

![&quot;viewmodel\_offset\_hip&quot; 						&quot;2 -2 -3&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.04-16.25.20.77.png)

![&quot;viewmodel\_offset\_hip&quot; 						&quot;-6.5 1 -4&quot;](../../.gitbook/assets/desktop-screenshot-2020.03.04-16.47.10.40.png)

## 重新打包

[如何正确地重新打包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack#ru-he-zheng-que-di-zhong-xin-da-bao-vpk)

在按步骤完成了上方链接的内容之后：

重命名pak000\_000.vpk为**client\_mp\_common.bsp.pak000\_000.vpk**

重命名pak000\_dir.vpk为**englishclient\_mp\_common.bsp.pak000\_dir.vpk**

将两个重命名完成的文件放回下面所示的文件夹之中并覆盖文件，然后启动《泰坦陨落2》。你就能看见修改后武器定位了！

> Origin Games\Titanfall2\vpk\

