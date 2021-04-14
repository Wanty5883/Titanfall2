---
description: 游戏文本修改指南
---

# 游戏文本修改-r1\_language

## 前期准备

在本指南中，你需要去修改文本内容。只需使用一个文本编辑器即可，例如：Atom, NotePad++, VIM。（只要是功能正常的文本编辑器都可以，系统自带的也行）

{% hint style="warning" %}
这个指南的内容很多，请参阅右边的目录以快速跳转至您要查找的内容。.
{% endhint %}

因为文件中存在很多数据，如果您希望改进指南的内容，随时可以[联系我们](https://noskill.gitbook.io/titanfall2/v/chinese/contact)。

进入你的游戏目录并找到此VPK文件夹:

> Origin Games\Titanfall2\vpk\

复制粘贴下面列出的文件到其他空的文件夹之中:

* englishclient\_frontend.bsp.pak000\_dir.vpk
* client\_frontend.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool，这个软件允许你查看并重新打包《泰坦陨落2》VPK文件。 [下载链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)​

## 解包 <a id="unpacking"></a>

现在，这些文件已经备份完毕并且所有东西都已经准备就绪了。在软件中进入游戏目录，并打开下面的这个文件:

> Origin Games\Titanfall2\vpk\englishclient\_frontend.bsp.pak000\_dir.vpk

​[如何正确的提取VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)​

## 编辑

若想修改游戏文本，请先进入下面的这个文件夹之中

> englishclient\_frontend.bsp.pak000\_dir.vpk\resource

想要编辑游戏中的大部分文本，你需要去编辑r1文本文件。 根据您设置的游戏语言（在Origin中），选择正确的r1文本文件进行编辑。**例如：**如果你的游戏语言是英语，那么你要编辑文件是_`r1_english.txt`_。（中文是_`r1_tchinese.txt`_）

打开_`r1_english.txt`_文件并根据你所需要修改的游戏文本来搜索下面列出的代码块。 指南中并未涵盖此文件的所有内容。如果你想修改在本指南中未列出的某些文本，请留意文本文件中的内容，并善用文本编辑器中的搜索功能。欢迎你随时提出建议！这里是[联系方式](https://noskill.gitbook.io/titanfall2/v/chinese/contact)

### 聊天

**聊天前缀**

```text
"HUD_CHAT_TEAM_PREFIX"						"[TEAM]"
"HUD_CHAT_DEAD_PREFIX"						"[DEAD]"
```

### 泰坦

**泰坦弹射信息**

_`COCKPIT_EJECT_PROMPT`_和 _`OCKPIT_EJECT_CONFIRMED`_这两个数据的数值是出现在泰坦主界面上的。其他的则是主界面下方红色条中的信息。

若要修改泰坦弹射信息，请查找以下代码块：

```text
"COCKPIT_EJECT_PROMPT"                          "SELF_DESTRUCT:"
"COCKPIT_EJECT_CONFIRMED"                       "EJECTING"

"COCKPIT_EJECT_COMMON_0"                        "PILOT EJECTING"
"COCKPIT_EJECT_COMMON_1"                        "EJECT NOW EJECT"
"COCKPIT_EJECT_COMMON_2"                        "CORE BREAK IN PROGRESS"
"COCKPIT_EJECT_COMMON_3"                        "DESTRUCT SEQUENCE ENGAGED"
"COCKPIT_EJECT_COMMON_4"                        "EJECT-SYSTEM ENGAGED"
"COCKPIT_EJECT_COMMON_5"                        "PROTOCOL [03]"
// COCKPIT_EJECT_COMMON_COUNT = 6

"COCKPIT_EJECT_RARE_0"                          "It was fun."
"COCKPIT_EJECT_RARE_1"                          "Ain't over till it's over."
"COCKPIT_EJECT_RARE_2"                          "Until next time, then."
"COCKPIT_EJECT_RARE_3"                          "Second star to the right."
"COCKPIT_EJECT_RARE_4"                          "Go get 'em, tiger."
"COCKPIT_EJECT_RARE_5"                          "Make it so."
"COCKPIT_EJECT_RARE_6"                          "See you on the other side."
"COCKPIT_EJECT_RARE_7"                          "Wait for the wheel."
"COCKPIT_EJECT_RARE_8"                          "Do not throw your shot."
"COCKPIT_EJECT_RARE_9"                          "Drop and burn 'em up."
```

**泰坦HUD**

这些数值设置的是显示在屏幕中间的游戏文本。（而不是泰坦核心值旁边的）

```text
"HUD_EJECT"                                     "[Eject]"
"HUD_EJECT_NO_BRACKETS"                         "Eject"
"HUD_TITAN_READY"                               "TITAN READY"
"HUD_TITAN_READY_HINT"                          "%ability 1% Titanfall"
"HUD_TITAN_CORE_READY"                          "Titan Core Charged"
"HUD_TITAN_CORE_CHARGING"                       "Recharging Core"
"HUD_TITAN_BUILDING"                            "Building Titan"
"HUD_TITAN_DISEMBARK"                           "Hold %use% to disembark"
```

**泰坦核心值**

这些数值用于设置泰坦核心值周围的游戏文本。

请不要更改这些数据：_`%s1`_, _\`\`1%$rui/hud/titan\_core%`0+%s1`3%%\`_, _\`3%%\`_

```text
"CORE_READY"                                "CORE READY"
"CORE_ACTIVE"                               "CORE ACTIVE"
"CORE_EARNED_DELTA"                         "CORE +%s1`3%%"
"CORE_EARNED_AMOUNT"                        "CORE %s1`3%%"
"CORE_EARNED_DELTA_COMPACT"                 "`1%$rui/hud/titan_core%`0+%s1`3%%"
"CORE_EARNED_AMOUNT_COMPACT"                "`1%$rui/hud/titan_core%`0%s1`3%%"

"TITAN_READY"                                "TITAN READY"
"TITAN_EARNED_DELTA"                         "TITAN +%s1`3%%"
"TITAN_EARNED_AMOUNT"                        "TITAN %s1`3%%"
"TITAN_EARNED_DELTA_COMPACT"                 "`1%$rui/hud/titanfall_marker_arrow_progress%`0+%s1`3%%"
"TITAN_EARNED_AMOUNT_COMPACT"                "`1%$rui/hud/titanfall_marker_arrow_progress%`0%s1`3%%"
```

### 击杀效果

击杀效果是你在屏幕右下角看到的所有文本。

**玩家连接**

请不要更改这个数据：_`%s1`_ 

```text
"MP_PLAYER_CONNECTED"                          "%s1 has entered the game"
"MP_PLAYER_DISCONNECTED"                       "%s1 has left the game"
"MP_SOMEONE_DISCONNECTED"                      "A player has left the game"
```

**死亡类型**

```text
"DEATH_BUBBLE_SHIELD"						"Dome Shield"
"DEATH_BURN"						 		"Burn"
"DEATH_CRUSHED"				      		"Crushed"
"DEATH_INDOOR_INFERNO"		   			"Burning Inferno"
"DEATH_ELECTROCUTION"						"Electrocution"
"DEATH_SUICIDE_SPECTRE"					  "Tick Explosion"
[...]
```

### LSTAR

下面的代码块是用来设置LSTAR小屏幕中的文本。

```text
"LSTAR_AMPED"                                  "AMPED"
"LSTAR_COOLING"                                "COOLING"
"LSTAR_READY"                                  "READY"
"LSTAR_DANGER"                                 "DNGR"
"LSTAR_CAUTION"                                "caution"
"LSTAR_ERRBRK"                                 "ERRBRK"
"LSTAR_DEPLETE"                                "depleted"
```

### 游戏模式

正如我所测试过的。如果你有重生时间，这些数值在任何游戏模式中都是通用的。

```text
"GAMEMODE_RESPAWNING_IN_N"					"Respawning in: `1%s1"
"GAMEMODE_DEPLOYING_IN_N"				 	"Deploying in: `1%s1"
```

**夺旗模式**

这些数值用于设置旗帜不同状态下的透视显示。

```text
"GAMEMODE_FLAG_DEFEND"								"DEFEND"
"GAMEMODE_FLAG_CAPTURE"							   "CAPTURE"
"GAMEMODE_FLAG_ESCORT"								"ESCORT"
"GAMEMODE_FLAG_ATTACK"								"KILL"
"GAMEMODE_FLAG_RETURN"								"RETURN"
"GAMEMODE_FLAG_GUARD"								 "GUARD"
"GAMEMODE_FLAG_SECURE"								"SECURE"
"GAMEMODE_FLAG_HOLD"							  	"HOLD"
"GAMEMODE_FLAG_STEAL"							 	"STEAL"
"GAMEMODE_FLAG_INTERCEPT"						 	"INTERCEPT"
"GAMEMODE_FLAG_AWAY"							      "AWAY"
"GAMEMODE_FLAG_YOU"								   "You have the Flag"
```

这些数值用于设置其他玩家对旗帜不同行为的文本。

```text
"GAMEMODE_PLAYER_HAS_FRIENDLY_FLAG"					"%s1 has our flag!"
"GAMEMODE_PLAYER_HAS_ENEMY_FLAG"					"%s1 has the enemy flag!"

"GAMEMODE_PLAYER_CAPTURED_FRIENDLY_FLAG"			"%s1 captured our flag!"
"GAMEMODE_PLAYER_CAPTURED_ENEMY_FLAG"				"%s1 captured the enemy flag!"
"GAMEMODE_PLAYER_CAPTURED_FLAG_RUI"					"You captured the flag!"

"GAMEMODE_PLAYER_RETURNED_FRIENDLY_FLAG"			"%s1 returned Our flag"
"GAMEMODE_PLAYER_RETURNED_ENEMY_FLAG"				"%s1 flag returned"
"GAMEMODE_PLAYER_RETURNED_FLAG_RUI"					"You returned the flag"

"GAMEMODE_RETURNED_FRIENDLY_FLAG"					"Our flag returned to base"
"GAMEMODE_RETURNED_ENEMY_FLAG"						"Enemy flag returned to base"

"GAMEMODE_PLAYER_DROPPED_FRIENDLY_FLAG"				"%s1 dropped your flag"
"GAMEMODE_PLAYER_DROPPED_ENEMY_FLAG"				"%s1 dropped the enemy flag"
"GAMEMODE_PLAYER_DROPPED_FLAG_RUI"					"Dropped the Flag"
```

这些数值用于设置你对旗帜不同行为的文本。

```text
"GAMEMODE_YOU_PICKED_UP_THE_FLAG_RUI"				"Picked up the Flag"
"GAMEMODE_YOU_HAVE_THE_ENEMY_FLAG"					"You have the enemy flag"
"GAMEMODE_YOU_DROPPED_THE_ENEMY_FLAG"				"You dropped the enemy flag"
"GAMEMODE_YOU_CAPTURED_THE_ENEMY_FLAG"				"You captured the enemy flag!"
"GAMEMODE_RODEO_PILOT_HAS_THE_ENEMY_FLAG"			"Friendly Rodeo Pilot has the enemy flag"
"GAMEMODE_YOU_RETURNED_THE_FRIENDLY_FLAG"			"You Returned the Flag!"
```

**Amped Hardpoint**

这些数值用于设置在据点时的文本。

```text
"HUD_SECURED"										"SECURED"
"HUD_CONTESTED"									  "CONTESTED"
"HUD_CONTESTED_ARROWS_UP"						    "CONTESTED %s1"
"HUD_CONTESTED_ARROWS_DOWN"						  "%s1 CONTESTED"
"HUD_NEUTRALIZING_ARROWS_UP"						 "NEUTRALIZING %s1"
"HUD_CAPTURING_ARROWS_UP"							"CAPTURING %s1"
"HUD_CAPTURING_ARROWS_DOWN"						  "%s1 CAPTURING"
"HUD_LOSING_ARROWS_DOWN"							 "%s1 LOSING"
```

**死亡标志**

这些数值用于设置死亡标志的文本。请不要更改这些数据例如： _`%s1`_, _`3%%`_

若想修改其他关于死亡标记的数值，请在文本编辑器中搜索： _`MARKED_FOR_DEATH`_.

```text
"GAMEMODE_MARKED_FOR_DEATH_KILLED"			"%s1 killed %s2"
"GAMEMODE_MARKED_FOR_DEATH_SUICIDE"			"%s1 committed suicide"
"GAMEMODE_MARKED_FRIENDLY_KILLED_MARKED"	"%s1 killed %s2"
"GAMEMODE_MARKED_ENEMY_KILLED_MARKED"		"%s1 killed %s2"
"GAMEMODE_MARKED_FRIENDLY_MARKED_DIED"		"%s1 died"
"GAMEMODE_MARKED_ENEMY_MARKED_DIED"			"%s1 died"
```

### 首杀

用于设置关于首杀的文本。

```text
"EVENTNOTIFY_FIRST_STRIKE_FRIENDLY"					"First Strike! %s1 killed %s2"
"EVENTNOTIFY_FIRST_STRIKE_ENEMY"					"First Strike! %s1 killed %s2"
```

### 脱离地图范围

```text
"OUT_OF_BOUNDS_WARNING"    "RETURN TO THE BATTLE!"
```

### 服务器错误

```text
"CLIENT_DELTA_BUFFER_OVERFLOW"    "Server error - client desynchronization"
```

## 重新打包 <a id="repacking"></a>

​[如何正确的重新打包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)​

在按步骤完成了上方链接的内容之后：

重命名pak000\_000.vpk为**client\_frontend.bsp.pak000\_000.vpk**

重命名pak000\_dir.vpk为**englishclient\_frontend.bsp.pak000\_dir.vpk**

将两个重命名完成的文件放回下面所示的文件夹之中并覆盖文件，然后启动《泰坦陨落2》。你就能看见修改后游戏文本了！

> Origin Games\Titanfall2\vpk\

