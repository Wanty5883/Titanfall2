# 北极星-重力特效

## 前期准备

在前面这么多指南的积累下，我们认为你学会了如何设置/开始修改你的游戏。如果你是特殊情况（直接跳到这个页面），你需要去了解“基础信息”。[参考链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction)

Any欢迎您提出任何建议，您可以在NS的Discord服务器中提交您的请求/意见。即使是您自己制作的武器/设置，你也可以通过[联系方式](https://noskill.gitbook.io/titanfall2/v/chinese/contact)联系我们。 

### 录像

{% embed url="https://www.youtube.com/watch?v=A2ke8bzzi30" %}

## 电浆磁轨炮

### 编辑

为了得到视频中电浆轨道炮的效果，你需要去编辑一个文本文件。除了你自己用的文本编辑器，没有其他特定的软件。

进入以下目录：

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

用你的文本编辑器打开 `mp_titanweapon_sniper.txt` 这个文件

在文件中查找并替换以下数值。**注意**：不要将整个代码块复制粘贴到原始文件中，请手动输入双引号中的数值，否则可能会导致游戏不能正常解析文件。

这些数值将电浆磁轨炮的炮弹在射出后变为蓝色，并使得进行蓄力射击时拥有重力漩涡特效。

```text
"projectile_trail_effect_0"				"wpn_grenade_frag_blue"
"projectile_trail_effect_1"				"wpn_grenade_frag_blue"
"projectile_trail_effect_2"				"P_wpn_grenade_gravity"
```

这些数值将枪焰变为电光。 _注:_ _枪焰适用于当你开枪的时候，而不是你蓄力射击时的涡流特效。_

```text
"fx_muzzle_flash_view"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_world"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_attach"				"muzzle_flash"
```

下列数值改变了电浆磁轨炮蓄力射击时的效果和声音。我把蓄力射击时的效果和声音换成了成重力漩涡的特效。

```text
"charge_sound_1p"					"weapon_gravitystar_preexplo"
"charge_full_sound_1p"					"Weapon_Titan_Sniper_SustainLoop"
"charge_effect_1p"					"P_wpn_grenade_gravity"
"charge_effect_3p"					"P_wpn_grenade_gravity"
```

### 准星

这里是我所使用的电浆磁轨炮的准星数据：

```text
active_crosshair_count				"2"
rui_crosshair_index					"0"

RUI_CrosshairData
{
	DefaultArgs
	{
		adjustedSpread				weapon_spread
		adsFrac 					player_zoomFrac
		isSprinting					player_is_sprinting
		isReloading					weapon_is_reloading
		readyFrac                   progress_ready_to_fire_frac
		teamColor					crosshair_team_color
		isAmped						weapon_is_amped
		chargeFrac                  player_chargeFrac
		crosshairMovementX          crosshair_movement_x
		crosshairMovementY          crosshair_movement_y
	}

	Crosshair_1
	{
		"ui"						"ui/crosshair_charge_rifle"
		"base_spread"				"10.0"
		Args
		{
			isFiring				weapon_is_firing
		}
	}
	Crosshair_1
	{
		"ui"						"ui/crosshair_circle2_small"
		"base_spread"				"0.0"
		Args
		{
			isFiring				weapon_is_firing
		}
	}
}
```

## 飞行核心

### 编辑

为了修改飞行核心，你需要去编辑一个文本文件。除了你的文本编辑器，没有特定的软件。（系统自带的也行）

对于需要编辑的第一个文件，请进入以下目录：

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\vscripts\weapons

用你的文本编辑器打开 `mp_titanweapon_flightcore_rockets.txt` 这个文件。

在文件中查找并替换下面的数值。**Note:** 不要将整个代码块复制粘贴到原始文件中，请手动输入双引号中的数值，否则可能会导致游戏不能正常解析文件。

这将使得飞行核心发射导弹时带有电光特效。

```text
"fx_muzzle_flash_view"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_world"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_attach"				"muzzle_flash_2"

"fx_muzzle_flash2_view"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash2_world"				"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash2_attach"				"muzzle_flash"
```

这些数值将把电浆磁轨炮原来的炮弹换成能源炮的炮弹，并使得炮弹带有雷电炮的特效：

```text
"impact_effect_table" 					"exp_arc_ball"
"projectile_trail_effect_0" 				"P_plasma_proj_LG_DLight"
```

下面的修改把核心声音的变成了"软"一些的飞弹声音（这一点是纯粹的个人口味）只影响你自己使用飞行核心的时候。

```text
"fire_sound_1_player_1p"			"ShoulderRocket_Homing_Fire_1P"
"fire_sound_1_player_3p"			"weapon_titan_flightcore_rocket_fire_3p"
"fire_sound_2"					"Weapon_bulletCasings.Bounce"
```

### 准星

```text
active_crosshair_count				"1"
rui_crosshair_index					"0"

RUI_CrosshairData
{
	DefaultArgs
	{
		adjustedSpread				weapon_spread
		adsFrac 					player_zoomFrac
		isSprinting					player_is_sprinting
		isReloading					weapon_is_reloading
		teamColor					crosshair_team_color
		isAmped						weapon_is_amped
		crosshairMovementX          crosshair_movement_x
		crosshairMovementY          crosshair_movement_y
	}

	Crosshair_1
	{
		"ui"						"ui/crosshair_tracker_rockets"
		"base_spread"				"0.0"
		Args
		{
			isFiring				weapon_is_firing
		}
	}
}
```

## 集束飞弹

为了得到视频中集束飞弹的效果，你需要去编辑一个文本文件。除了你自己用的文本编辑器，没有其他特定的软件。

进入以下目录：

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

用你的文本编辑器打开 `mp_titanweapon_dumbfire_rockets.txt` 这个文件。

在文件中查找并替换下面的数值。**Note:** 不要将整个代码块复制粘贴到原始文件中，请手动输入双引号中的数值，否则可能会导致游戏不能正常解析文件。

下面的修改使得集束飞弹的图标变成边境防御中的同款，并且也把集束飞弹的动画效果变成了边境防御中神盾升级后的双倍集束飞弹的动画效果。

```text
"hud_icon"		"rui/menu/fd_menu/upgrade_northstar_twin_cluster_hud"
"viewmodel"		"models/weapons/titan_raptor_rocket_pod/atpov_titan_raptor_rocket_pod_core.mdl"
```

这个修改使得集束飞弹的火箭弹变成了重力旋涡的效果，这就是本次北极星修改的主题。

```text
"projectile_trail_effect_0"			"P_wpn_grenade_gravity"
```

## 绊索陷阱

为了得到视频中绊索陷阱的效果，你需要去编辑一个文本文件。除了你的文本编辑器，没有特定的软件。（系统自带的也行）

对于需要编辑的第一个文件，请进入以下目录：

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

用你的文本编辑器打开 `mp_titanability_tether_trap.txt` 这个文件。

在文件中查找并替换下面的数值。**Note:** 不要将整个代码块复制粘贴到原始文件中，请手动输入双引号中的数值，否则可能会导致游戏不能正常解析文件。

这将把绊索陷阱的图标HUD改为边境防御中的图标。

```text
"hud_icon"			"rui/menu/fd_menu/upgrade_northstar_explosive_trap_hud"
```

这些修改后的值使绊索陷阱具有了电光特效。

```text
"impact_effect_table"				"P_wpn_arcTrap"
"projectile_trail_effect_0"			"P_wpn_arcball_trail_amp"
```

