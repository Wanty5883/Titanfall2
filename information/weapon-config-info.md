---
description: List of information for the weapon config files
---

# Weapon config info

## Introduction & Warning

Massive amount of value and information. Check down bellow in `Game Values` category for more. But please read this in the first place.

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder containt the "config files" for the weapons. This folder contain a lot of files, check [File location](https://wanty5883.gitbook.io/titanfall2/information/weapon-config-info#file-location) for the full list of the different weapons in the game.

{% hint style="danger" %}
**Edit those files at your own risk**, if you get banned because you edit some important value don’t blame me.
{% endhint %}

## Location

The weapon config files are stored in this location

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\weapons
```

Other weapon config files are stored in other VPK but as for now I won't cover that part.

## RUI\_CrosshairData

Bracket where go the following values

### active\_crosshair\_count

This value set the amount of crosshair you would like to use at once. To use multiple crosshair at once, you need to duplication the all `Crosshair_1` bracket.

### ui/crosshair

This values are the crosshair itself. They can be swaped to any other ui/crosshair value you can find in other config files. You can send me message if you find other one.

Some crosshair are dynamics, like the charge rifle, frag grenade and couples of other crosshair that have animation. In some case changing to an other dynamic crosshair will work fine, in other cases it won't. As an example my favorite one is using the charge rifle crosshair for the Northstar railgun. For an opposite example, the frag grenade crosshair to the CAR won't work well.

![](../.gitbook/assets/crosshair1.PNG)

![](../.gitbook/assets/crosshair2.PNG)

![](../.gitbook/assets/crosshair3.PNG)

### base\_spread

This value set the based size of the crosshair, this won't change the vector size but the distance between the center of the screen and the different parts of the crosshair. You can use positive or negative values.

## Effects

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder containt the "config files" for the weapons. Edit those files at your own risk, if you get banned because you edit some important value don’t blame me.

This guide will cover value bellow the comment `// Effects` in those files. This guide will be large and covert lot of different value, so for an easier navigation refer to the **table of content**. Here is the part of the file we are looking for

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

As you may noticed, for some weapon when you amp them \(amped weapon\) some effect change. Here what you should look For

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

### a. impact\_effect\_table

This value define the impact animation when the bullet hit on players or walls. It can be added to weapon who don't already have this value. As I tested before, is not possible to combine multiple impact.  
You can have different value between normal and amped mode on each weapon config file. Impact\_effect\_table accept other type of values, like tracers.

### b. tracer\_effect

Tracer effect are for **hitscan weapon only**, this function does not effect projectile based weapon. However, there is some exeption about that. Find that code block to get where is the tracers code part.

```text
"tracer_effect"   							  "P_wpn_tracer"
"tracer_effect_first_person"                    "P_wpn_tracer"
```

`tracer_effect` will effect the **overall game**, basically it will change the tracer particle of other player using the edited weapon \(this is client side of course\). `tracer_effect_first_person` will effect **you**. Depending of what you want to do, you can set different value between them. As I tested around, it could be very confusing or even have a bad impact on your game performance too many `tracer_effect` in too many different weapons. I personally rarely change it, I just change `tracer_effect_first_person` most of the time.

### b. Tracer values

| Value | Notes | e.g. |
| :--- | :--- | :--- |
| **Classic** |  |  |
| P\_wpn\_tracer | Default AR | Carbine, G2A5 |
| P\_wpn\_tracer\_BC | Default AR amped | Amped Carbine |
| P\_wpn\_tracer\_pistol | Default pistol | Wingman |
| P\_weapon\_tracers\_predator | Default Legion | Legion default fire mode |
| P\_weapon\_tracers\_predator\_alt | White trail, longer duration | Legion fire while ADS |
| weapon\_tracers\_shotgun | Leadwall |  |
| weapon\_tracers\_xo16 | Default chaingun |  |
| P\_wpn\_tracer\_sniper | Longbow DMR |  |
| P\_wpn\_tracer\_sniper\_BC | Amped Longbow DMR |  |
| **Electric** |  |  |
| P\_wpn\_tracer\_pulse | Default electric |  |
| P\_wpn\_tracer\_xo16\_elec | Chaingun electric |  |
| **Beam** |  |  |
| P\_wpn\_hand\_laser\_beam | Laser shot |  |
| P\_wpn\_defender\_beam\_burn | Amped Charge rifle |  |
| P\_wpn\_monarch\_beam\_v1 | Syphon default mode |  |
| P\_wpn\_monarch\_beam\_v2 | Syphon varient |  |
| wpn\_arc\_cannon\_beam | Arc Cannon |  |
| wpn\_arc\_cannon\_beam\_mod | Arc Cannon |  |
| **Unknown** |  |  |
| weapon\_tracers\_vortex | Vortex shield |  |
| weapon\_tracers\_vortex\_mod | Vortex shield |  |
| P\_wpn\_tracer\_sniper | Not used by railgun | Railgun |
| weapon\_tracers\_40mm | Have to test | Thermite launcher |
| P\_wpn\_hand\_laser\_beam\_BC | Have to test | Monarch & laser shot |

### c. projectile\_trail\_effect

Projectile trail effect are for **projectile weapon only**, this function does not effect hitscan based weapon. Find that code block to get where is the tracers code part.

```text
"projectile_trail_effect_0" 					"P_projectile_lstar"
```

You can have different value between normal and amped mode on each weapon config file.





## 

