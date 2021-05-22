---
description: Entspy是一个可以查看和编辑BSP文件实体属性的工具。
---

# Entspy

**Entspy**是一个可以查看和编辑[BSP](https://developer.valvesoftware.com/wiki/BSP)文件[实体](https://developer.valvesoftware.com/wiki/Entity)属性的工具。该工具对于调整较小实体的属性很有用，而且无需再次编译地图。  
该程序的最后一个版本是v0.8，发布于2nd October 2005。

![Entspy &#x754C;&#x9762;](../../../../../.gitbook/assets/entspy1.gif)

## 在地图上添加重生点

给地图添加额外的重生点可能是你想要使用Entspy编辑地图实体的一个常见原因。下面是操作说明与指导：

1.运行一个本地服务器。这个可以通过向控制台输入`sv_lan 1`和`map mapname` 来实现，此命令将会加载对应地图。

2. 开启作弊。在控制台中输入`sv_cheats 1`。

3. 在控制台中输入 `map_showspawnpoints` 。地图上所有有效的重生点都会以绿色盒子的形式显示。

4. 输入`cl_showpos 1`。你当前地图的坐标（X, Y, Z） 将会显示在屏幕的右上角（在"pos:"之后的数值）。

5. 当你想要创建新重生点时，请站在不要过于靠近当前重生点的任意一个地方。另外，请记录你在每一个点的位置（坐标精确到整数位即可）。

6. 退出游戏并在Entspy中加载地图。

7. 在实体列表中，找出你想创建的重生点类型。例如，在 CS:S 中，实体`info_player_counterterrorist`代表CT方的重生点，实体`info_player_terrorist`代表T方的重生点。

8.通过选择上述重生点类型并按下在实体列表下的“Copy”按钮来给重生点实体做一个备份。

9. 编辑备份重生点的“原点（origin）”属性，以匹配你再第五步记录的位置坐标。注意，你可能需要从z坐标（最后一个数字）中减去大约50个单位，才能保证刷出点的高度是正确的。

10. 对于剩下的点位重复第七步的步骤。

11. 通过 "File/Save BSP" 菜单存储地图。

12. 现在请像将改变后的地图加载到游戏中，并再次在控制台中输入`map_showspawnpoints`命令。现在你就可以看到以绿盒子形式出现的新重生点了。如果某些重生点以红盒子形式显示，则它们是无效的。如果一个重生点与一个实体（如地面）相交，或者与另一个实体（如另一个重生点）太近，那么它就会是无效的。一般重生点间距约为至少80个单位。 

![&#x5728;&#x5730;&#x56FE;cs\_office&#x4E2D;CT &#x65B9;&#x7684;&#x91CD;&#x751F;&#x70B9;&#x3002; &#x7EFF;&#x76D2;&#x5B50;&#x662F;&#x73B0;&#x6709;&#x7684;&#x91CD;&#x751F;&#x70B9;&#x3002;&#x76EE;&#x524D;&#x73A9;&#x5BB6;&#x7684;&#x4F4D;&#x7F6E;&#x5728;&#x5C4F;&#x5E55;&#x53F3;&#x4E0A;&#x65B9;&#x88AB;&#x663E;&#x793A;&#x3002;](../../../../../.gitbook/assets/cs_office0000.jpg)

![&#x4E3A;&#x4E86;&#x5728;cs\_office&#x4E2D;&#x6DFB;&#x52A0;&#x4E00;&#x4E2A;&#x65B0;&#x7684;&#x91CD;&#x751F;&#x70B9;&#xFF0C;&#x4F60;&#x9700;&#x8981;&#x590D;&#x5236;&#x4E00;&#x4E2A;&#x5DF2;&#x6709;&#x7684;info\_player\_counter&#x5B9E;&#x4F53;&#xFF0C;&#x5E76;&#x7F16;&#x8F91;&#x201C;&#x539F;&#x70B9;&#xFF08;origin&#xFF09;&#x201D;&#x5C5E;&#x6027;&#x4EE5;&#x5339;&#x914D;&#x73A9;&#x5BB6;&#x7684;&#x5750;&#x6807;&#x4F4D;&#x7F6E;&#x3002;](../../../../../.gitbook/assets/entspy_edit.png)

## 视频教学

{% embed url="https://www.youtube.com/watch?v=irO8V8U9YYY" %}

{% hint style="info" %}
引用资料：

* [https://developer.valvesoftware.com/wiki/Entspy](https://developer.valvesoftware.com/wiki/Entspy)
* [http://www.bagthorpe.org/bob/cofrdrbob/entspy.html](http://www.bagthorpe.org/bob/cofrdrbob/entspy.html)
{% endhint %}

