---
description: 如何在不把事情搞砸的情况下玩转VPK
---

# 如何备份，解包和重新打包

## 如何正确地备份和提取VPK？

当你想要提取 [VPK](../../information/file-format/vpk-valve-pak-file.md)文件时，你需要创建一个文件目录来存放你选定的[VPK](../../information/file-format/vpk-valve-pak-file.md)文件提取出来的文件。这个文件夹**不应该**放在游戏目录中。我建议你创建一个名字简单好认的文件夹，比如 `Titanfall 2 modding` ，放在这个路径之中： `C:\Users\<username>\Documents` 

```text
C:\Users\<username>\Documents\Titanfall 2 modding
```

一旦你创建了这个用于存放的文件夹，我建议你马上创建一个名为`"Backup"` 的子文件夹。你猜怎么着。。。备份！（好耶！）

```text
C:\Users\<username>\Documents\Titanfall 2 Modding\backup
```

打开Titanfall VPK Tool，然后按 `CTRL+O`（也可以这样打开：_`File->Open`_ ）。进入你的游戏目录并选择指定的文件 \(基于你正在查看的指南\)。将[VPK](../../information/file-format/vpk-valve-pak-file.md)导入进工具之后, 单击名为 _`Extract All`_的菜单图标。我个人更喜欢将这些解包出来的文件放在一个和所提取的[VPK](../../information/file-format/vpk-valve-pak-file.md)同名的文件夹之中，让你从不同的VPK提取文件时更易于管理。.

在提取完成之后，打开目标文件夹并删除_`extracted_logs`_文件夹。

{% hint style="warning" %}
**只支持从游戏目录中提取**[**VPK**](../../information/file-format/vpk-valve-pak-file.md)**文件。如果你试图从你的备份文件夹提取**[**VPK**](../../information/file-format/vpk-valve-pak-file.md)**文件， 这将导致程序错误！**
{% endhint %}

{% hint style="warning" %}
请确保使用的是3.3或3.4版本的Titanfall VPK Tool。以前版本的工具可能存在不支持的操作。
{% endhint %}

## **如何正确地重新打包VPK？**

使用Titanfall VPK Tool中带有的打包工具。你有两种方式去打开它：单击名为_`Repack VPK`_ 的菜单图标， 或者通过_`Tools > Repacker`_打开。 打开工具后，在第一个文件目录选项选择你存放修改文件的文件夹。

> 例如： C:\Users\YourSessionName\Documents\Titanfall\_2\_modding\Extracted\englishclient\_mp\_common.bsp.pak000\_dir.vpk

然后第二个文件目录选项是输出重新打包文件后文件的位置，我建议你选择一个简单易懂的文件夹。

> C:\Users\YourSessionName\Documents\Titanfall 2 modding\Repack\

保持VPKFileName的内容不变，然后单击_`Build VPK`_。 在重新打包的VPK文件生成完成之后，进入上面你所选择的文件输出目录。你会找到两个文件名分别为_`pak000_000.vpk`_ _`pack000_dir.vpk`_的文件。 在将这两个文件覆盖游戏目录之前，你必须按照说明重新命名它们。 在每个指南之中，你都有必须备份的两个指定文件。你应该复制它们的文件名，然后粘贴到那两个新文件的文件名中。你要注意区分两个文件名中是否包含_`_dir`_ ，这有助于你分辨两个文件哪个应该命名为哪个。 \(好吧，我知道这听起来很奇怪，让我给你举个例子！\)

**例如：**

把 pak000\_000.vpk _重命名为_ **client\_mp\_common.bsp.pak000\_000.vpk**

把 pak000\_dir.vpk _重命名为_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

## VPK重命名/移动批处理脚本

{% hint style="success" %}
厌倦了手动重命名/移动VPK文件回到游戏目录？
{% endhint %}

这里有一个小小的批处理脚本可供你使用！

```bash
ren "pak000_000.vpk" "client_mp_common.bsp.pak000_000.vpk"
ren "pak000_dir.vpk" "englishclient_mp_common.bsp.pak000_dir.vpk"
move "client_mp_common.bsp.pak000_000.vpk" "<ORIGINGAMES>\Titanfall2\vpk\client_mp_common.bsp.pak000_000.vpk"
move "englishclient_mp_common.bsp.pak000_dir.vpk" "<ORIGINGAMES>\Titanfall2\vpk\englishclient_mp_common.bsp.pak000_dir.vpk"
```

这是 _`englishclient_mp_common.bsp.pak000_dir.vpk`_的脚本，它也可以替换为你经常修改的任何其他VPK文件。 

{% hint style="danger" %}
在运行此脚本时，请你确保你的VPK工具没有处于运行状态，因为这将导致程序错误。
{% endhint %}

**不要忘记用正确的游戏目录去替换掉**_`<ORIGINGAMES>`_ 。例如： `C:\Program Files\Origin\Library` 这是Origin平台下载游戏的目录（注意，是Origin下载的目录），而不是包含《泰坦陨落2》游戏的目录。 \(比如我Origin游戏的目录是`H:\Orishit\Games`\)

{% page-ref page="modding-tools/" %}

