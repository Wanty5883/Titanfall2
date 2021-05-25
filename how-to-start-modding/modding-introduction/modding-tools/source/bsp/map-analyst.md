---
description: Map Analyst (MAN) 是Rolf Hänisch发布的一个GUI工具，用于给. bsp文件嵌入自定义内容，如材料，纹理，模型或声音。
---

# Map Analyst 地图分析器

 **Map Analyst** \(MAN\) 是Rolf Hänisch发布的一个[GUI](https://developer.valvesoftware.com/wiki/GUI)工具，用于给[. bsp](https://developer.valvesoftware.com/wiki/BSP)文件嵌入自定义内容，如材料，纹理，模型或声音。 其他打包程序因为某些缺陷有时候不能够检测到自定义文件的更改。 MAN可以通过让使用者直接告诉它应该包装什么来规避这个问题。尽管此软件发布的年代久远\(2005年\)，但已被证实仍然适用于传送门2等较新的游戏。

{% hint style="info" %}
**注解：**本指南是原版德语ZIP文件中包含的压缩版本翻译而成的。当然，中文页面是根据英语翻译而成的。
{% endhint %}

特别感谢Gosuke，是他给了本文原作者这个项目的想法。在开始之后，很多地图制作者都很支持这个项目。除了Gosuke, 也特别感谢Thomas 'Flausch' Abts, DJ flyer\(别名Markus\)， Spice和Thor。如果没有他们的帮助，MAN可能现在还处于beta测试状态，也会缺失很多如今有的功能。谢谢你们！

## 安装

这个ZIP包可以被解包至任意位置。双击man.exe来启动程序。

在开始之前，你要在程序中设置[游戏目录](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaRzY1-2WFNul9taRjZ/v/chinese/how-to-start-modding/modding-introduction/modding-tools/source/game-directory)，例如：`C:\Program Files (x86)\Steam\steamapps\common\Portal 2\portal2_dlc3`.

请在 **Options-Game path-Set game path** 中设置游戏路径

请点击 **View game path** 查看目前的游戏路径。请浏览以下部分以了解如何加快打包速度：





![](../../../../../.gitbook/assets/man26ebeta01.png)

### 

为了打开一个地图，你需要打开**File - Read and scan map。**这个程序也支持拖拽，但是可能需要你更改游戏路径。

![](../../../../../.gitbook/assets/man26ebeta02.png)

![&#x7ECF;&#x5178;&#x7684;&#x8BFB;&#x53D6; .bsp &#x6210;&#x529F;&#x7684;&#x8F93;&#x51FA;&#x8BED;&#x53E5;](../../../../../.gitbook/assets/man26ebeta03.png)

### 指定所要包含的文件

打包内容有两种方法。如果所有需要打包的内容都在一个文件夹中，可以使用第一种方法，它更快且更容易。这两种方法都要求您将文件放在游戏目录下的一个子文件夹中，例如：`C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\csgo\materials\decals`

#### 选择文件……

选择**File - Include file - Choose file..** 然后选中所有您想打包至地图的独立文件。请注意，此窗口菜单无法选择文件夹本身或者两个不同文件夹中的文件。如果你遇到了这种情况，请看下面的方法。

![](../../../../../.gitbook/assets/man26ebeta07.png)

#### 读取文件列表

打开一个文本编辑器，比如说记事本。在这个文本中，放入需要打包到地图中的所有文件的文件路径。这些文件必须与你的游戏根目录文件夹有所关联。然后，请使用扩展名.txl保存这个文本。现在，在软件中选择**File - Include file - Read file list**。然后选择之前创建的.txl文件。这个文本文件的名称可以是任意名称，但是与当前地图相同的命名将允许您自动加载它。

![An example TXL file. Note this one was generated using the first method.](../../../../../.gitbook/assets/man26ebeta08.png)

## 分析一个地图

接下来，程序必须找出那些东西需要打包。请在软件里选择 **File-Analyze map content**。

地图上的文件将会一个接一个地被检查。可能会出现关于文件未被添加，丢失等的警告。您可以忽略所有这些警告，除非它提到了您准备的试图打包的内容。蓝色文本通常表示不需要打包的文件，因为它们不是您自定义添加的内容。

![](../../../../../.gitbook/assets/man26ebeta04.png)

![&#x7ECF;&#x5178;&#x7684;&#x5730;&#x56FE;&#x5206;&#x6790;&#x8F93;&#x51FA;&#x8BED;&#x53E5;&#xFF0C;&#x6CE8;&#x610F;&#xFF0C;&#x6B64;&#x622A;&#x56FE;&#x4E0D;&#x5B8C;&#x6574;&#xFF0C;&#x5B9E;&#x9645;&#x60C5;&#x51B5;&#x4F1A;&#x66F4;&#x957F;](../../../../../.gitbook/assets/288px-man26ebeta05.png)

## 打包

![](../../../../../.gitbook/assets/man26ebeta06.png)

在软件中选择 **File - Update game \(VBSP）**，然后就成了！ 被你打包的地图将会将会被默认命名为 **man\_betatest** ，除非你设置了下面提到的覆盖选项。请使用命令 [`sv_pure 2`](https://developer.valvesoftware.com/wiki/Sv_pure) 或者邀请你的朋友一起游玩这张地图来确认打包的正确性。

## 选项

### 自动化

在**Options - Automatic** 中有三个可以进行独立开关的设置，可以让你的打包速度更快：

* **Include**：附加文件列表将会自动加载
* **Analyze**：如果地图已经成功加载，分析将会自动启动。
* **Update**: 如果分析成功，BSP文件将会自动更新

### Verbosity

对于单个地图最大可以涵盖的文件数， MAN 在**Options - Display** 中有切换控制选项来控制输出文件的大小

### 覆盖

如果 **Options - Overwrite BSP** 处于开启状态， MAN 将覆盖原来的BSP，而不是创建一个名为man\_betatest 的新地图文件。

{% hint style="danger" %}
**警告：**这可能会破坏你原来的bsp文件。
{% endhint %}

{% hint style="info" %}
源文档链接： [https://developer.valvesoftware.com/wiki/Map\_Analyst](https://developer.valvesoftware.com/wiki/Map_Analyst)
{% endhint %}

