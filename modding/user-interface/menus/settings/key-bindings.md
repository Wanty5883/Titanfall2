---
description: 在“按键绑定”菜单添加其他自定义按键绑定
---

# 按键设置

![&#x7F16;&#x8F91;&#x5B8C;&#x6210;&#x5E26;Titanfall 2 speedrunning&#x90E8;&#x5206;&#x7684;&#x6309;&#x952E;&#x7ED1;&#x5B9A;&#x83DC;&#x5355;](../../../../.gitbook/assets/snapshot0015.jpg)

## 文件位置

按键绑定菜单文件在 `englishclient_frontend.bsp.pak000_dir.vpk`**，**位于 `scripts\kb_act.lst`

## 工作原理

文件的每一行对应于这之中的标题/节点，其代码如下：

```text
"blank"					"=========================="
"blank"					"Section Title"
"blank"					"=========================="
```

或是为按键绑定到动作：

```text
"+attack"				    "#FIRE"
"+zoom"					    "#AIM_MODIFIER"
"+toggle_zoom"			"#TOGGLE_AIM_MODIFIER"
"+reload"				    "#RELOAD"
```

## 自定义按键

要添加自定义按键绑定，首先打开文件并创建一个新的节点菜单（不必这样做，但这样会使它看起来更整洁）。 复制以 `"blank"` 开头的三行代码块，并创建自己的标题。

在你创建的新节点下面，添加新的行，我们将在这里添加自定义按键绑定设置。

每个设置的左边是泰坦陨落/起源变量，右边是按键绑定的标题。

```text
"+jump"        "Jump"
```

## 有趣的指令

低重力效果

```text
"toggle sv_gravity 200 750"    "Low Gravity"
```

创建和加载存档

```text
"save quicksave"    "Create Quicksave"
"load quicksave"    "Load Quicksave"
```

放慢或加快游戏速度

```text
"toggle host_timescale .25 1"      "0.25x Speed"
"toggle host_timescale 5 1"        "5x Speed"
```



