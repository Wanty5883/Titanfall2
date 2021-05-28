# Vtex - 疑难解答

下面这些都是你在使用[Vtex](./)时可能会遇到的错误和问题：

在这里，你可以上传并更新你所遇到的问题，但是请注意，上传时请和下列问题的格式保持一致：

## 本地Steam服务没有运行

Vtex 会报以下的错误：

```text
SteamStartup() failed: SteamStartup(0xf,0x0012F0E4) failed with error 108: The local Steam Service is not running
```

当Vtex运行时，Steam也必须运行。请启动Steam来解决这个问题。

## outputdir 相关问题

Vtex 会报以下的错误：

```text
Problem figuring out outputdir for <path>
```

第一步，请检查需要被转换的纹理是否真的存放在`\sourcesdk_content\gamedir\materialsrc` folder，其中gamedir 为游戏所在文件夹 \(`cstrike`/`dod`/`hl2`/`hl2mp`\).

如果纹理确实在对应的文件夹中，则错误可能是由于环境变量的复杂度造成的。为了解决这个问题，请使用 [VConfig](../../game-directory.md) ,并确保所选的mod至少运行过一次，这样应该能够解决上述问题。当然，有些情况下，问题依旧会存在。

对于这种情况，一个解决办法是删除 VProject 的环境变量。 在Windows XP（后续版本的win无验证，请根据不同系统版本的环境变量配置方式进行更改）也可以通过以下方法实现：

1. 右键单击“我的电脑”，单击“属性”。
2. 选择高级系统设置选项卡。
3. 单击窗口底部的环境变量。
4. 在系统变量部分，向下滚动直到出现VProject行。
5. 单击删除按钮。
6. 双击确定按钮，并退出。

然而，这个解决方案将会生成一个 gameinfo.txt 错误，对于这个情况可能的解决办法是：直接删掉这个非功能性解决方案？（未验证，具体有没有用也不知道）

### **替代解决方案**

如果出现了Vtex.exe无法理解输入语句中的空格的情况。一种解决方案是在C:\驱动器上直接创建一个与vtex快捷方式所指向的源文件夹同名的文件夹。例如，创建一个`C:\tf`文件夹来替代`C:\Program Files\Steam\steamapps \team fortress 2\tf`文件夹。之后，请更新vtex.exe快捷方式的启动路径以指向这个新文件夹。在这个文件夹中，请放入原文件夹中的`gameinfo.txt`，并创建空的`materialsrc`和`materials`文件夹。最后，请将要转换的文件放到新的`materialsrc`文件夹中。然后将文件拖拽到vtex.exe上，正常情况下，输出文件将会在`materials`文件夹中生成。

