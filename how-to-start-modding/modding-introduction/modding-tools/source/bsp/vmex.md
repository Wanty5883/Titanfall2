---
description: Valve Map Extractor (VMEX)是一个起源引擎地图的反编译器。
---

# VMEX

**Valve Map Extractor \(VMEX\)**是一个[起源引擎](https://developer.valvesoftware.com/wiki/Source)地图的反编译器。它可以将将[BSP](https://developer.valvesoftware.com/wiki/BSP)格式文件转换回[VMF](https://developer.valvesoftware.com/wiki/VMF)格式的地图，并可以加载到Hammer。自从0.98g版本以来，它支持Valve直到《求生之路》的所有游戏。

{% hint style="info" %}
**注解：**使用VMEX对地图进行反编译不一定能够得到100%准确的构建模型。有些东西（关键值，材质等）可能会与原始地图不完全匹配。
{% endhint %}

## 船（一个游戏）

要反编译[The Ship](https://developer.valvesoftware.com/wiki/The_Ship)的地图，请在这里下载修改过的版本：[VMEX \(v0.98e\)](http://www.bagthorpe.org/bob/cofrdrbob/files/vmex-098e-ts.zip)。

### 求生之路

vmex的修改版本是由[TerabyteDragon](https://developer.valvesoftware.com/wiki/User:TerabyteDragon)在原作者的许可下创建的，用于反编译[Left 4 Dead](https://developer.valvesoftware.com/wiki/Left_4_Dead)的地图。此修改解决了静态道具的一个问题（特别是BSP文件中的条目大小问题）。这个版本可以从下面的链接获取。注意:这个版本的vmex不保证能兼容其他游戏。

### 求生之路2

你可以在下面下载一个由[Omnicoder](https://developer.valvesoftware.com/wiki/User:Omnicoder)编写的可将[Left 4dead 2](https://developer.valvesoftware.com/wiki/Left_4_Dead_2)的bsp文件转换为可由VMEX反编译的预处理器的软件。

### Windows Vista Java 修复

在手动设置Java的环境变量路径之前，当前的VMEx版本\(098g\)是不能与Windows Vista一起工作的。（应用程序将拒绝打开，如果您用命令提示符运行它，您还会得到错误消息“Java is not recognized as an internal or external command”。）

要设置环境变量路径，请遵循以下步骤：

1. 找到JAVA的可执行文件 \(`Java.exe`\) 并记录其路径。常见路径应该为`C:\Program Files\Java\jre6\bin` （32位windows系统）或者`C:\Program Files (x86)\Java\jre6\bin` （64位windows系统）你需要记住这个路径。（如果您无法找到Java可执行文件，这可能意味着Java\(运行时环境\)甚至没有成功地安装在您的计算机上。如果没有，请到[java官方网站](http://www.java.com/)下载并安装。）
2. 点击左下角的“开始”图标，然后选择“控制面板”，然后点击“系统”，进入后点击左上角“高级系统设置”。
3. 在弹出的选项卡中点击环境变量按钮。
4. 在系统变量中找到名为PATHS的变量。
5. 双击打开，在现有变量值的末尾，添加一个分号\(;\)，然后添加你之前确认过的Java.exe （`C:\Program Files\Java\jre6\bin` 或`C:\Program Files (x86)\Java\jre6\bin`）的路径，随后保存即可生效。

{% hint style="info" %}
源文档链接： [https://developer.valvesoftware.com/wiki/VMEX](https://developer.valvesoftware.com/wiki/VMEX)
{% endhint %}

