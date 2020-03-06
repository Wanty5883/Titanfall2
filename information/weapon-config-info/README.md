---
description: List of information for the weapon config files
---

# Weapon config info

## Introduction & Warning

Massive amount of value and information. Check the `Game Values` category down below for more. But please read this before.

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder contains the "config files" for the weapons. This folder contains a lot of files, check **`Weapon config - File name`** for the full list of the different weapons in the game.

{% page-ref page="weapon-config-file-name.md" %}

{% hint style="danger" %}
**Edit those files at your own risk.** If you get banned because you edit some important value it is your own fault. Do not experiment with values that are not client sided or mainly aesthetic.
{% endhint %}

## Location

The weapon config files are stored in this location

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\weapons
```

Other weapon config files are stored in other VPKs but as of right now I won't cover that part.

## RUI\_CrosshairData

Bracket where the following values go

### active\_crosshair\_count

This value sets the amount of crosshairs you would like to use at once. To use multiple crosshairs at once, you need to duplicate the `Crosshair_1` bracket.

### ui/crosshair

These values are the crosshair itself. They can be swapped to any other ui/crosshair value you can find in other config files. You can send me a message if you find other ones.

Some crosshairs are dynamic, like the charge rifle, frag grenade and a couple of other crosshairs that have animations. In some cases changing to another dynamic crosshair will work fine, in other cases it won't. As a working example: my favorite crosshair combo is using the charge rifle crosshair for the Northstar railgun. For a non working example: the frag grenade crosshair on the CAR won't work well.

![](../../.gitbook/assets/crosshair1.PNG)

![](../../.gitbook/assets/crosshair2.PNG)

![](../../.gitbook/assets/crosshair3.PNG)

### base\_spread

This value sets the base size of the crosshair, this won't change the vector size but the distance between the center of the screen and the different parts of the crosshair. You can use positive or negative values.

## Effects

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder contains the "config files" for the weapons. Edit those files at your own risk, if you get banned because you edit some important value don’t blame me.

This guide will cover value below the comment `// Effects` in those files. This guide will be large and covers a lot of different values, so for an easier navigation refer to the **table of content**. This is the part of the file we are looking for:

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

As you may noticed, for some weapons, when you amp them \(amped weapon\) some effects change. This is what you should look for:

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

This value defines the impact animation when the bullet hits players or walls. It can be added to weapons who don't  have this value already. As tested before, it is not possible to combine multiple impact animations.  
You can have different values between normal and amped mode on each weapon config file. Impact\_effect\_table accepts other type of values, like tracers.

You can have different values between normal and amped mode on each weapon config file. Find impact values in game values FX

{% page-ref page="../../game-values/fx/" %}

### b. tracer\_effect

Tracer effects are for **hitscan weapons only**, this function does not effect projectile based weapons. However, there are some exeptions. Find this code block to the tracers code part:

```text
"tracer_effect"   							  "P_wpn_tracer"
"tracer_effect_first_person"                    "P_wpn_tracer"
```

`tracer_effect` will effect the **overall game**, basically it will change the tracer particle of other players using the edited weapon \(this is client side of course\). `tracer_effect_first_person` will effect **you**. Depending of what you want to do, you can set different values between them. As tested, it could be very confusing or even have a bad impact on your game performance if there are too many `tracer_effect` on too many different weapons. I personally rarely change it, I just change `tracer_effect_first_person` most of the time.

{% page-ref page="../../game-values/fx/" %}

### c. projectile\_trail\_effect

Projectile trail effects are for **projectile weapons only**, this function does not effect hitscan based weapons. Find this code block to get to the trail code part:

```text
"projectile_trail_effect_0" 					"P_projectile_lstar"
```

You can have different values between normal and amped mode on each weapon config file. Find projectile values in game values FX

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

