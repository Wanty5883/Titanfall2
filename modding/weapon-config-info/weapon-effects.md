---
description: 修改武器的视觉效果
---

# 武器特效

## 前期准备 <a id="preparation"></a>

进入以下目录并找到所需的VPK文件:

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## 解包 <a id="unpacking"></a>

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[如何正确地解包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

### 特效

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

这个文件夹包含所有武器的"配置文件"，修改文件所产生的风险由你自己承担。如果因为你修改核心数值而导致的账号封禁，别把责任归咎于我。

本指南将会介绍这些文件中注释 `// Effects`对应的数值， 它包含很多的内容和各种不同的数值。为了更快找到你所需要的东西，请参阅**目录**。这是我们要在文件中查找的一部分内容：

```text
// Effects
"tracer_effect"   							"P_wpn_tracer"
"tracer_effect_first_person"                  "P_wpn_tracer"
"vortex_absorb_effect"						"wpn_vortex_projectile_rifle_FP"
"vortex_absorb_effect_third_person"	   	"wpn_vortex_projectile_rifle"
"vortex_absorb_sound"						 "Vortex_Shield_AbsorbBulletSmall"
"vortex_absorb_sound_1P_VS_3P"				"Vortex_Shield_AbsorbBulletSmall_1P_VS_3P"
"projectile_adjust_to_gun_barrel"			 "1"

"fx_shell_eject_view"						 "wpn_shelleject_rifle_assault_FP"
"fx_shell_eject_world"						"wpn_shelleject_rifle_assault"
"fx_shell_eject_attach"				   	"shell"

"fx_muzzle_flash_view"						"wpn_muzzleflash_smg_FP"
"fx_muzzle_flash_world"		   			"wpn_muzzleflash_smg"
"fx_muzzle_flash_attach"	  				"muzzle_flash"
```

As you may have noticed, some weapons have their effects changed when Amped. This is what you should look for:

```text
{
	"is_burn_mod"		                "1"

	//FX
	"tracer_effect"   				   "P_wpn_tracer_BC"
	"tracer_effect_first_person"         "P_wpn_tracer_BC"
	"fx_muzzle_flash_view"			   "wpn_muzzleflash_smg_elec_FP"
	"fx_muzzle_flash_world"		  	"wpn_muzzleflash_smg_elec"
}
```

#### impact\_effect\_table

This value defines the impact animation when the bullet hits players or walls. It can be added to weapons that don't have this value already. From previous testing results, it is not possible to combine multiple impact animations.  
Impact\_effect\_table accepts other types of values, like tracers.

You can have different values between the normal and amped modes on each weapon config file. Find impact values in game values FX:

{% page-ref page="../../game-values/fx/" %}

#### tracer\_effect

Tracer effects are for **hitscan weapons only**, this function does not affect projectile based weapons. However, there are some exceptions. Find this code block to locate the tracer code part:

```text
"tracer_effect"   							  "P_wpn_tracer"
"tracer_effect_first_person"                    "P_wpn_tracer"
```

`tracer_effect` will affect the **overall game**, in other words, it will change the tracer particle of other players using the edited weapon \(this is client side of course\). `tracer_effect_first_person` will effect **you**. You can set different values between them. From previous testing, it can be very confusing or even have a negative impact on your game performance if there are too many `tracer_effect` on too many different weapons. I personally rarely change it, I only change `tracer_effect_first_person` most of the time.

{% page-ref page="../../game-values/fx/" %}

#### projectile\_trail\_effect

Projectile trail effects are for **projectile weapons only**, this function does not affect hitscan weapons. Find this code block to locate the trail code part:

```text
"projectile_trail_effect_0" 					"P_projectile_lstar"
```

You can have different values between the normal and amped modes on each weapon config file. Find projectile values in game values FX:

{% page-ref page="../../game-values/fx/" %}



