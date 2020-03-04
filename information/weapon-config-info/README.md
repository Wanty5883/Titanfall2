---
description: List of information for the weapon config files
---

# Weapon config info

## Introduction & Warning

Massive amount of value and information. Check down bellow in `Game Values` category for more. But please read this in the first place.

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder contains the "config files" for the weapons. This folder contain a lot of files, check **`Weapon config - File name`** for the full list of the different weapons in the game.

{% page-ref page="weapon-config-file-name.md" %}

{% hint style="danger" %}
**Edit those files at your own risk.** If you get banned because you edit some important value it is your own fault. Do not experiment with values that are not client sided or mainly aesthetic.
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

![](../../.gitbook/assets/crosshair1.PNG)

![](../../.gitbook/assets/crosshair2.PNG)

![](../../.gitbook/assets/crosshair3.PNG)

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

You can have different value between normal and amped mode on each weapon config file. Find impact values in game values FX

You can have different value between normal and amped mode on each weapon config file. Find impact values in game values FX

{% page-ref page="../../game-values/fx/" %}

{% page-ref page="../../game-values/fx/" %}

### b. tracer\_effect

Tracer effect are for **hitscan weapon only**, this function does not effect projectile based weapon. However, there is some exeption about that. Find that code block to get where is the tracers code part.

```text
"tracer_effect"   							  "P_wpn_tracer"
"tracer_effect_first_person"                    "P_wpn_tracer"
```

`tracer_effect` will effect the **overall game**, basically it will change the tracer particle of other player using the edited weapon \(this is client side of course\). `tracer_effect_first_person` will effect **you**. Depending of what you want to do, you can set different value between them. As I tested around, it could be very confusing or even have a bad impact on your game performance too many `tracer_effect` in too many different weapons. I personally rarely change it, I just change `tracer_effect_first_person` most of the time.

{% page-ref page="../../game-values/fx/" %}

{% page-ref page="../../game-values/fx/" %}

### c. projectile\_trail\_effect

Projectile trail effect are for **projectile weapon only**, this function does not effect hitscan based weapon. Find that code block to get where is the tracers code part.

```text
"projectile_trail_effect_0" 					"P_projectile_lstar"
```

You can have different value between normal and amped mode on each weapon config file. Find projectile value in game values FX

You can have different value between normal and amped mode on each weapon config file. Find projectile value in game values FX

{% page-ref page="../../game-values/fx/" %}

{% page-ref page="../../game-values/fx/" %}

## Arguments

{% tabs %}
{% tab title="RUI\_CrosshairData Args" %}
| Argument | Value | Note |
| :--- | :--- | :--- |
| adjustedSpread | weapon\_spread |  |
| adsFrac | player\_zoomFrac |  |
| ammoFrac | "progress\_weapon\_clip\_ammo\_frac" |  |
| ammoFrac | "progress\_grapple\_power" |  |
| chargeFrac | player\_chargeFrac |  |
| chargeLevel | player\_chargeLevel |  |
| chargeMaxTime | eWeaponVar.custom\_float\_0 |  |
| chargeStartTime | weapon\_script\_time\_0 |  |
| clipAmmo | weapon\_ammo |  |
| clipSize | weapon\_clipSize |  |
| crosshairMovementX | crosshair\_movement\_x |  |
| crosshairMovementY | crosshair\_movement\_y |  |
| dryfireTime | "weapon\_latest\_dryfire\_time" |  |
| isActive | weapon\_is\_active |  |
| isAmped | weapon\_is\_amped |  |
| isFiring | weapon\_is\_firing |  |
| isGrappleInRange | "grapple\_in\_range" |  |
| isLocked | smartammo\_locked |  |
| isReloading | weapon\_is\_reloading |  |
| isSprinting | player\_is\_sprinting |  |
| readyFrac | progress\_ready\_to\_fire\_frac |  |
| regenRate | "eWeaponVar.regen\_ammo\_refill\_rate" |  |
| smartFov | "eWeaponVar.smart\_ammo\_search\_angle" |  |
| teamColor | crosshair\_team\_color |  |
{% endtab %}

{% tab title="Mods Args" %}
| Argument | Value | Note |
| :--- | :--- | :--- |
| ammo | weapon\_ammo |  |
| ammoFrac | weapon\_ammofrac |  |
| chargeFrac | progress\_weapon\_charge\_frac |  |
| clipAmmo | weapon\_ammo |  |
| clipCount | weapon\_stockpileClipCount |  |
| clipSize | weapon\_clipSize |  |
| inCooldown | weapon\_is\_inCooldown |  |
| isActive | weapon\_is\_active |  |
| isAmped | weapon\_is\_amped |  |
| isCooling | weapon\_is\_inCooldown |  |
| isFiring | weapon\_is\_firing |  |
| isInCooldown | weapon\_is\_inCooldown |  |
| isReloading | weapon\_is\_reloading |  |
| lastDryFireTime | weapon\_latest\_dryfire\_time |  |
| lifetimeShots | weapon\_lifetime\_shots |  |
| pchargeFrac | player\_chargeFrac |  |
| proOwnedByPlayer | proscreen\_owner\_is\_player |  |
| proValue | proscreen\_int0 |  |
| readyFrac | progress\_ready\_to\_fire\_frac |  |
| readyToFireFrac | progress\_ready\_to\_fire\_frac |  |
| vis | player\_zoomfrac |  |
| zoomFrac | player\_zoomfrac |  |
{% endtab %}
{% endtabs %}

## 

