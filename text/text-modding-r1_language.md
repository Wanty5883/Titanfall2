---
description: Guide to change in game text
---

# Text modding r1\_language

## Preparation

In this guide you will have to edit text. Simply use a text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

This guide will be large. Refer to the **table of contents** to find what you are looking for.

Since there is a lot of value, feel free to offer your help to improve this guide check [contact](https://wanty5883.gitbook.io/titanfall2/contact).

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_frontend.bsp.pak000\_dir.vpk
* client\_frontend.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://wanty5883.gitbook.io/titanfall2/information/modding-tools)​

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_frontend.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://wanty5883.gitbook.io/titanfall2/how-to-start-modding/2.-how-to-backup-extract-and-repack)​

## Editing

To edit text, go to this location

> englishclient\_frontend.bsp.pak000\_dir.vpk\resource

To edit most of the text in the game, you need to edit r1 txt file. Depending of your set game language \(in Origin\) you have to edit the right r1 file. **e.g.** If your game language is english, then you edit the file _`r1_english.txt`_.

Open the file _`r1_english.txt`_ and search for code block that are listed down bellow to the right text you want to edit. I won't cover all the content of this file, if you want to change some text that are not listed in this guide, you should note what you seen on your screen and use the function _search_on this file. Any suggestion are welcome ! Check [contact](https://github.com/Wanty5883/Titanfall2/wiki/Contact) for that

### Chat

**Chat prefixes**

```text
"HUD_CHAT_TEAM_PREFIX"						"[TEAM]"
"HUD_CHAT_DEAD_PREFIX"						"[DEAD]"
```

### Titan

**Titan eject message**

The value _`COCKPIT_EJECT_PROMPT`_ & _`COCKPIT_EJECT_CONFIRMED`_ are the messages appearing on the Titan's main screen. The other ones are the message in the red bar bellow the main screen.

To edit titan ejecting message find the following code block

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

**Titan HUD**

Thoose value set the text that show up in middle of your screen. Not the one close to the core meter.

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

**Titan core Meter**

Thoose value set the text around the core meter.

It's important that you leave the values like _`%s1`_, _\`\`1%$rui/hud/titan\_core%`0+%s1`3%%\`_, _\`3%%\`_untouched.

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

### Kill feed

Kill feed is the text zone where you see all the text in the down right of your screen.

**Player connection**

It's important that you leave the value _`%s1`_ untouched.

```text
"MP_PLAYER_CONNECTED"                          "%s1 has entered the game"
"MP_PLAYER_DISCONNECTED"                       "%s1 has left the game"
"MP_SOMEONE_DISCONNECTED"                      "A player has left the game"
```

**Death types**

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

Down bellow, code block that set the text in the little LSTAR screen.

```text
"LSTAR_AMPED"                                  "AMPED"
"LSTAR_COOLING"                                "COOLING"
"LSTAR_READY"                                  "READY"
"LSTAR_DANGER"                                 "DNGR"
"LSTAR_CAUTION"                                "caution"
"LSTAR_ERRBRK"                                 "ERRBRK"
"LSTAR_DEPLETE"                                "depleted"
```

### Gamemode

As I tested, thoose value are common to any gamemode if you have a respawn time set.

```text
"GAMEMODE_RESPAWNING_IN_N"					"Respawning in: `1%s1"
"GAMEMODE_DEPLOYING_IN_N"				 	"Deploying in: `1%s1"
```

**Capture the flag**

Thoose value set the text for the different state of the flags through the wall.

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

Thoose value set the text for the different action on the flag made by players.

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

Thoose value set the text for the different action you did on the flag.

```text
"GAMEMODE_YOU_PICKED_UP_THE_FLAG_RUI"				"Picked up the Flag"
"GAMEMODE_YOU_HAVE_THE_ENEMY_FLAG"					"You have the enemy flag"
"GAMEMODE_YOU_DROPPED_THE_ENEMY_FLAG"				"You dropped the enemy flag"
"GAMEMODE_YOU_CAPTURED_THE_ENEMY_FLAG"				"You captured the enemy flag!"
"GAMEMODE_RODEO_PILOT_HAS_THE_ENEMY_FLAG"			"Friendly Rodeo Pilot has the enemy flag"
"GAMEMODE_YOU_RETURNED_THE_FRIENDLY_FLAG"			"You Returned the Flag!"
```

**Amped Hardpoint**

Thoose value set the text while inside a point.

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

**Marked for death**

Thoose values set the text for marked kilss. It's important that you leave the values like _`%s1`_, _`3%%`_untouched.

For more mark for death text value, with the function search look for _`MARKED_FOR_DEATH`_.

```text
"GAMEMODE_MARKED_FOR_DEATH_KILLED"			"%s1 killed %s2"
"GAMEMODE_MARKED_FOR_DEATH_SUICIDE"			"%s1 committed suicide"
"GAMEMODE_MARKED_FRIENDLY_KILLED_MARKED"	"%s1 killed %s2"
"GAMEMODE_MARKED_ENEMY_KILLED_MARKED"		"%s1 killed %s2"
"GAMEMODE_MARKED_FRIENDLY_MARKED_DIED"		"%s1 died"
"GAMEMODE_MARKED_ENEMY_MARKED_DIED"			"%s1 died"
```

### First strike

Set the text about first strike.

```text
"EVENTNOTIFY_FIRST_STRIKE_FRIENDLY"					"First Strike! %s1 killed %s2"
"EVENTNOTIFY_FIRST_STRIKE_ENEMY"					"First Strike! %s1 killed %s2"
```

### Out of map

```text
"OUT_OF_BOUNDS_WARNING"    "RETURN TO THE BATTLE!"
```

### Server error

```text
"CLIENT_DELTA_BUFFER_OVERFLOW"    "Server error - client desynchronization"
```

## Repacking <a id="repacking"></a>

​[How to repack VPK files proprely ?](https://github.com/Wanty5883/Titanfall2/wiki/General-Info#how-to-repack-vpk-files-proprely-)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_frontend.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_frontend.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

