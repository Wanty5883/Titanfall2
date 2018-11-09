---
description: Guide to edit network menus details and color
---

# Network - Menus

## Preparation

In this guide you will have to edit res files. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

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

To edit the Network menu interface text color, go to this location

> resource\ui\menus\panels

Open the file _`community_info.res`_

To make edit easier, down bellow a list of code block to the right value you want to edit. To edit color, edit the string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity. **In some code block**, mostly what we will call "value" \(value, is the result in menus\) you won't find this string _`fgcolor_override "x x x x"`_. Just add it inside the bracket with the RGB + opacity code you want.

Is possible to hide some labels by editing this string _`visible 1`_ to 0. The labels where you edit it will be hidden **but** other labels won't fit empty place. You will need to edit both thoose values _`wide`_ & _`tall`_ for that.

![](https://github.com/Wanty5883/Titanfall2/raw/master/picture/community_info.PNG)

### Creator name

Find the following code block

**Creator label**

```text
	CreatorLabel
	{
		ControlName				Label
		pin_to_sibling			CommunityName
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		ypos					32
		tall 					30
		wide					200
		labelText				"#COMMUNITY_CREATOR_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"255 0 255 255"

		zpos					1
	}
```

**Creator value \(name\)**

```text
	CreatorName
	{
		ControlName				Label
		pin_to_sibling			CreatorLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_RIGHT
		wide					600
		tall					30
		visible					1
		font 					Default_28
		fgcolor_override		"87 151 219 128"
	}
```

You can edit this string _`fgcolor_override "87 151 219 128"`_. The 3 first value are RGB and the 4th one is the opacity.

### Net Worth

Find the following code block

**Net worth label**

```text
	XPLabel
	{
		ControlName				Label
		pin_to_sibling			CreatorLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		auto_tall_tocontents	1
		wide					200
		labelText				"#COMMUNITY_XP_LABEL"
		textAlignment			"north-west"
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"255 0 255 255"

		zpos					1
	}
```

**Net worth value**

```text
	XP
	{
		ControlName				Label
		xpos					30
		pin_to_sibling			XPLabel
		pin_corner_to_sibling	LEFT
		pin_to_sibling_corner	RIGHT
		textAlignment			"north-west"
		wide					220
		auto_tall_tocontents	1
		visible					1
		font 					Default_28
		fgcolor_override		"254 151 0 255"
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Members

Find the following code block

**Members label**

```text
	ActiveMembersLabel
	{
		ControlName				Label
		pin_to_sibling			XPLabel
		pin_corner_to_sibling	TOP_RIGHT
		pin_to_sibling_corner	BOTTOM_RIGHT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_ACTIVE_MEMBERS"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Members value**

```text
	ActiveMembers
	{
		ControlName				Label
		pin_to_sibling			XPIcon
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					300
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Membership

Find the following code block

**Membership label**

```text
	CommunityMembershipLabel
	{
		ControlName				Label
		pin_to_sibling			ActiveMembersLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_MEMBERSHIP_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Membership value**

```text
	MembershipPolicy
	{
		ControlName				Label
		pin_to_sibling			ActiveMembers
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Happy hour

Find the following code block

**Happy hour label**

```text
	HappyHourLabel
	{
		ControlName				Label
		ypos					30
		pin_to_sibling			CommunityMembershipLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_HAPPYHOUR_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Happy hour value**

```text
	HappyHourStart
	{
		ControlName				Label
		ypos					30
		pin_to_sibling			MembershipPolicy
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Wins

Find the following code block

**Wins label**

```text
	WinsLabel
	{
		ControlName				Label
		pin_to_sibling			HappyHourLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_WINS_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Wins value**

```text
	Wins
	{
		ControlName				Label
		pin_to_sibling			HappyHourStart
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Kills

Find the following code block

**Kills label**

```text
	KillsLabel
	{
		ControlName				Label
		pin_to_sibling			WinsLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_KILLS_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"255 0 255 255"

		zpos					1
	}
```

**Kills value**

```text
	Kills
	{
		ControlName				Label
		pin_to_sibling			Wins
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Attitude

Find the following code block

**Attitude label**

```text
	CommunityTypeLabel
	{
		ControlName				Label
		pin_to_sibling			XP
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_RIGHT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_TYPE"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Attitude value**

```text
	CommunityType
	{
		ControlName				Label
		pin_to_sibling			CommunityTypeLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_RIGHT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Category

Find the following code block

**Category label**

```text
	CategoryLabel
	{
		ControlName				Label
		pin_to_sibling			CommunityTypeLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_CATEGORIES"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Category value**

```text
	Category
	{
		ControlName				Label
		pin_to_sibling			CommunityType
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Mics Policy

Find the following code block

**Mics policy label**

```text
	MicsLabel
	{
		ControlName				Label
		pin_to_sibling			CategoryLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_MICPREF_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Mics policy value**

```text
	MicPolicy
	{
		ControlName				Label
		pin_to_sibling			Category
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Visibility

Find the following code block

**Visibility label**

```text
	CommunityVisibilityLabel
	{
		ControlName				Label
		pin_to_sibling			MicsLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_VISIBILITY_LABEL"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Visibility value**

```text
	Visibility
	{
		ControlName				Label
		pin_to_sibling			MicPolicy
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Languages

Find the following code block

**Languagues label**

```text
	LanguagesLabel
	{
		ControlName				Label
		pin_to_sibling			CommunityVisibilityLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_LANGUAGES"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Languages value**

```text
	Languages
	{
		ControlName				Label
		pin_to_sibling			Visibility
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		tall					30
		visible					1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Regions

Find the following code block

**Regions label**

```text
	RegionsLabel
	{
		ControlName				Label
		pin_to_sibling			LanguagesLabel
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		tall 					30
		wide					200
		labelText				"#COMMUNITY_REGIONS"
		textAlignment			west
		font					Default_28
		textinsetx				11
		textinsety				1
		allcaps					0
		visible					1
		fgcolor_override		"192 192 192 255"

		zpos					1
	}
```

**Regions value**

```text
	Regions
	{
		ControlName				Label
		pin_to_sibling			Languages
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	BOTTOM_LEFT
		wide					400
		textAlignment           "north-west"
		auto_tall_tocontents    1
		visible					1
		wrap                    1
		font 					Default_28
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Message of the day

Find the following code block

**Message of the day label**

```text
	CommunityMOTDLabel
	{
		ControlName				Label
		xpos 					-24
		ypos                    -8
		pin_to_sibling			MOTDBackground
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_LEFT
		auto_tall_tocontents	1
		wide					400
		textAlignment			"north-west"
		labelText				"#COMMUNITY_MOTD_LABEL"
		font					Default_33
		allcaps					0
		visible					1
		fgcolor_override		"255 255 255 255"

		zpos					1
	}
```

**Message of the day value**

```text
	MOTD
	{
		ControlName				Label
		xpos 					10
		ypos					-15
		pin_to_sibling			MOTDIcon
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_RIGHT
		wide					460
		tall					308
		textAlignment			"north-west"
		wrap					1
		visible					1
		font 					Default_28
		fgcolor_override		"255 0 255 255"
	}
```

You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

### Title

Find the following code block

**Title label**

```text
	InfoTitle
	{
		ControlName				Label
		pin_to_sibling			InfoTitleBackground
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_LEFT
		xpos					0
		ypos					0
		textAlignment			"west"
		textinsetx				11
		wide					1100
		tall					30
		visible					0
		textinsety				-1
		allcaps 				1
		labelText 				"#COMMUNITY_DETAILS"
		font 					Default_28
	}
```

**Title value**

```text
	CommunityName
	{
		ControlName				Label
		pin_to_sibling			InfoBackground
		pin_corner_to_sibling	TOP_LEFT
		pin_to_sibling_corner	TOP_LEFT
		xpos					-32
		textAlignment			"west"
		wide					1100
		tall					40
		visible					0
		font 					Default_38
	}
```

For now, this isn't the right ones. They are only supposition, any information about this label would be welcome ! You can edit this string _`fgcolor_override "x x x x"`_. The 3 first value are RGB and the 4th one is the opacity.

## Hidden label

At the end of this file, we can see 2 hidden labels which contain death \(opposite of kills\) and losses \(opposite of wins\).

For now, set the value \*`visible 1`\*show it, but both thoose stats show 0, I guess there is no server track on this stats. They are also by default at the same place then label "Wins" & "Kills", need the right _`wide`_ & _`tall`_ value in labels. Any information would be welcome !

## Repacking <a id="repacking"></a>

​[How to repack VPK files proprely ?](https://github.com/Wanty5883/Titanfall2/wiki/General-Info#how-to-repack-vpk-files-proprely-)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_frontend.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_frontend.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

