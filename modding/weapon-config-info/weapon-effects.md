---
description: Modify the visual aspect of your weapon
---

# Weapon effects

## Preparation <a id="preparation"></a>

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)

### Effects

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder contains the "config files" for the weapons. Edit these files at your own risk. If you get banned because you edited important values, don’t blame me.

This guide will cover values below the comment `// Effects` in those files. It will be large and there are many different values, so for easier navigation refer to the **table of contents**. This is the part of the file we are looking for:

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



