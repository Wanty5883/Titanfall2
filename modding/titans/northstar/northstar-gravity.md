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

在文件中查找并替换以下数值。**注意**：不要将整个代码块复制粘贴到原始文件中，用字符串替换字符串，否则可能会导致游戏不能正常解析文件。

Thoose value change the railgun projectile to a blue one for regular shot and to gravity vortex for the full charged shots.

```text
"projectile_trail_effect_0"				"wpn_grenade_frag_blue"
"projectile_trail_effect_1"				"wpn_grenade_frag_blue"
"projectile_trail_effect_2"				"P_wpn_grenade_gravity"
```

Those values change the muzzle flash to an electric one. _note:_ muzzle flash apply when you shoot, this is not the vortex effect when you charge the railgun.

```text
"fx_muzzle_flash_view"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_world"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_attach"				"muzzle_flash"
```

This list of value change the charge effect and sound of the railgun. I change the charge effect **and**sound to the gravity vortex.

```text
"charge_sound_1p"					"weapon_gravitystar_preexplo"
"charge_full_sound_1p"					"Weapon_Titan_Sniper_SustainLoop"
"charge_effect_1p"					"P_wpn_grenade_gravity"
"charge_effect_3p"					"P_wpn_grenade_gravity"
```

### 准星

Here is the crosshair I'm using on the railgun

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

To get this flight core, you will need to edit one text files. No specific software exept your text editor.

For the first file you need to edit, go to this location

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\vscripts\weapons

Open the file `mp_titanweapon_flightcore_rockets.txt` with your text editor.

Find and replace the following values in your file. **Note:** Do not copy paste this entire code block into your original file, replace string by string or you might resolve with a none working file.

This will change the muzzle flash to an electric one.

```text
"fx_muzzle_flash_view"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_world"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash_attach"				"muzzle_flash_2"

"fx_muzzle_flash2_view"					"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash2_world"				"wpn_muzzleflash_arc_cannon_fp"
"fx_muzzle_flash2_attach"				"muzzle_flash"
```

Change the projectile to the EPG one and changeed the impact to the arc launcher one.

```text
"impact_effect_table" 					"exp_arc_ball"
"projectile_trail_effect_0" 				"P_plasma_proj_LG_DLight"
```

Changed the core sound to a soft "energy" one \(that point is purely personnal taste\) only for first person.

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

To get this cluster missle, you will need to edit one text files. No specific software exept your text editor.

Go to this location

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

Open the file `mp_titanweapon_dumbfire_rockets.txt` with your text editor.

Find and replace the following values in your file. **Note:** Do not copy paste this entire code block into your original file, replace string by string or you might resolve with a none working file.

This will change the cluster icon to the one from Frontier Defense. The cluster missile animation will change to the twin cluter tier mod from Frontier Defense.

```text
"hud_icon"		"rui/menu/fd_menu/upgrade_northstar_twin_cluster_hud"
"viewmodel"		"models/weapons/titan_raptor_rocket_pod/atpov_titan_raptor_rocket_pod_core.mdl"
```

This change the cluster missile projectile to the gravity vortex, which is the theme of this Northstar theme.

```text
"projectile_trail_effect_0"			"P_wpn_grenade_gravity"
```

## 绊索陷阱

To get this tether trap effect, you will need to edit one text files. No specific software exept your text editor.

Go to this location

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

Open the file `mp_titanability_tether_trap.txt` with your text editor.

Find and replace the following values in your file. **Note:** Do not copy paste this entire code block into your original file, replace string by string or you might resolve with a none working file.

This change the tether trap icon HUD to the one used in Frontier Defense.

```text
"hud_icon"			"rui/menu/fd_menu/upgrade_northstar_explosive_trap_hud"
```

Thoose values make the tether trap this electric effect.

```text
"impact_effect_table"				"P_wpn_arcTrap"
"projectile_trail_effect_0"			"P_wpn_arcball_trail_amp"
```

