---
description: List of information for the weapon config files
---

# Weapon config info



## Introduction & Warning

This page is quite... big due to the big amount of information around weapon config files and I plan to add even more. So for the sake of your mental health refer to the content summary on the right side of your screen. I done title and subtile to make it easier !

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

This folder containt the "config files" for the weapons. This folder contain a lot of files, check [File location](https://wanty5883.gitbook.io/titanfall2/information/weapon-config-info#file-location) for the full list of the different weapons in the game.

{% hint style="danger" %}
**Edit thoose files at your own risk**, if you get banned because you edit some important value don’t blame me.
{% endhint %}

## Location

The weapon config files are stored in this location

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\weapons
```

Other weapon config files are stored in other VPK but as for now I won't cover that part, tough...

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

This folder containt the "config files" for the weapons. Edit thoose files at your own risk, if you get banned because you edit some important value don’t blame me.

This guide will cover value bellow the comment `// Effects` in thoose files. This guide will be large and covert lot of different value, so for an easier navigation refer to the **table of content**. Here is the part of the file we are looking for

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
| P\_wpn\_defender\_beam | Charge rifle |  |
| P\_wpn\_defender\_beam\_burn | Amped Charge rifle |  |
| P\_wpn\_monarch\_beam\_v1 | Syphon default mode |  |
| P\_wpn\_monarch\_beam\_v2 | Syphon varient |  |
| **Unknown** | I have to test them |  |
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

### c. **Projectile value**

| Value | Notes | e.g. |
| :--- | :--- | :--- |
| **Classic** |  |  |
| P\_titan\_sniper1 | Railgun uncharged |  |
| P\_titan\_sniper2 | Railgun halfcharged |  |
| P\_titan\_sniper3 | Railgun full charged |  |
| P\_wpn\_tracer\_sniper | Railgun \(disable by default\) |  |
| P\_FlightCore\_trail | Flight course |  |
| weapon\_40mm\_projectile | 40MM |  |
| P\_SalvoCore\_trail | Salvo core / cluster |  |
| P\_Rocket\_Mortar | Mortar \(frontier defense\) |  |
| P\_leadwall\_proj | Leadwall |  |
| P\_mastiff\_proj | Mastiff |  |
| P\_mastiff\_proj\_amp | Mastiff Amped |  |
| wpn\_grenade\_frag\_mag | Spitfire |  |
| wpn\_grenade\_frag\_mag\_burn | Spitfire Amped |  |
| garand\_trail\_smoke | DMR \(not used by default\) |  |
| P\_doubletake\_proj | Double Take |  |
| weapon\_kraber\_projectile | Kraber |  |
| weapon\_kraber\_projectile\_burn | Kraber Amped |  |
| P\_proj\_predator\_alt\_pwr | Red projectile |  |
| wpn\_grenade\_frag\_blue | Blue projectile |  |
| wpn\_grenade\_sonar | Orange sonar |  |
| wpn\_grenade\_sonar\_titan | Orange titan sonar |  |
| **Electric** |  |  |
| P\_wpn\_arcball\_trail | Arc launcher |  |
| P\_wpn\_arcball\_trail\_amp | Arc launcher Amped |  |
| **Energy** |  |  |
| P\_projectile\_lstar | LSTAR |  |
| P\_projectile\_lstar\_burn | LSTAR Amped |  |
| P\_projectile\_TPA | Particle accelerator |  |
| P\_plasma\_proj\_LG\_DLight | EPG |  |
| P\_plasma\_proj\_LG\_amp | EPG Amped |  |
| P\_plasma\_proj\_MD | Cold War |  |
| P\_plasma\_proj\_MD\_amp | Cold War Amped |  |
| P\_projectile\_turretplasma\_mega | Red projectile |  |
| P\_plasma\_proj\_SM | Drone in FD |  |
| **Fire** |  |  |
| P\_wpn\_meteor\_trail | Thermite launcher |  |
| P\_xo\_meteorWave\_trail | Flame core trail |  |
| P\_grenade\_thermite\_trail | Firestar |  |
| **Smoke** |  |  |
| Rocket\_Smoke\_Small\_Titan | Rocket launcher |  |
| Rocket\_Smoke\_SMALL\_Titan\_2 | Electric smoke |  |
| Rocket\_Smoke\_SMALL\_Titan\_mod | Rocket launcher |  |
| Rocket\_Smoke\_Small\_Titan\_s2s | From single player |  |
| P\_meteor\_trap\_trail | Scorch trap smoke |  |
| Rocket\_Smoke\_SMR | SMR |  |
| Rocket\_Smoke\_SMR\_burn | SMR Amped |  |
| Rocket\_Smoke\_Large | Rocket Launcher |  |
| Rocket\_Smoke\_Large\_burn | Rocket Launcher Amped |  |
| wpn\_grenade\_frag\_softball | Softball |  |
| wpn\_grenade\_frag\_softball\_burn | Softball Amped |  |
| **Unknown** |  |  |
| P\_wpn\_laserTrip\_trail | Laser trip wire |  |
| wpn\_grenade\_sonar\_titan\_AMP | Orange titan sonar |  |
| wpn\_grenade\_TT | Related to gunship |  |
| wpn\_grenade\_TT\_mag | Related to gunship |  |
| wpn\_grenade\_TT\_activate | Related to Schorch |  |
| P\_dragonsbreath\_trail | Leadwall and probably doublet |  |
| P\_arcTrap\_light | Arc trap from FD |  |
| test\_projectile | In mp\_weapon\_arena1\(LSTAR\) |  |
| P\_sspectre\_proj | In mp\_weapon\_arena2 |  |
| wpn\_grenade\_frag | Frag grenade |  |
| P\_drone\_launch\_trail | Spectre spawner |  |

## File location

### AR - Assault Rifle

| Weapon name | File name |
| :--- | :--- |
| Carbine R-201C |  mp\_weapon\_rspn101.txt |
| Carbine R-101C | mp\_weapon\_rspn101\_og.txt |
| Hemlock BF-R | mp\_weapon\_hemlock.txt |
| V-47 Flatline | mp\_weapon\_vinson.txt |
| G2A5 | mp\_weapon\_g2.txt |

### **SMG**

| Weapon name | File name |
| :--- | :--- |
| Alternator | mp\_weapon\_alternator\_smg.txt |
| CAR | mp\_weapon\_car.txt |
| R-97 | mp\_weapon\_r97.txt |
| Volt | mp\_weapon\_hemlock\_smg.txt |

### **Shotgun**

| Weapon name | File name |
| :--- | :--- |
| EVA 8 Auto | mp\_weapon\_shotgun.txt |
| Mastiff | mp\_weapon\_mastiff.txt |

### **Sniper**

| Weapon name | File name |
| :--- | :--- |
| Kraber | mp\_weapon\_sniper.txt |
| Double Take | mp\_weapon\_doubletake.txt |
| Longbow DMR | mp\_weapon\_dmr.txt |

### **LMG**

| Weapon name | File name |
| :--- | :--- |
| Devotion | mp\_weapon\_esaw.txt |
| Spitfire | mp\_weapon\_lmg.txt |
| L-STAR | mp\_weapon\_lstar.txt |

### **Grenadiers**

| Weapon name | File name |
| :--- | :--- |
| EPG | mp\_weapon\_epg.txt |
| EM-4 Cold War | mp\_weapon\_pulse\_lmg.txt |
| Sidewinder SMR | mp\_weapon\_smr.txt |
| Softball | mp\_weapon\_softball.txt |

### **Pistol**

| Weapon name | File name |
| :--- | :--- |
| RE-45 Auto | mp\_weapon\_autopistol.txt |
| Wingman | mp\_weapon\_wingman.txt |
| Wingman Elite | mp\_weapon\_wingman\_n.txt |
| P2016 | mp\_weapon\_semipistol.txt |
| Mozambique | mp\_weapon\_shotgun\_pistol.txt |
| Smart Pistol | mp\_weapon\_smart\_pistol.txt |

### **Anti-Titan**

| Weapon name | File name |
| :--- | :--- |
| LG-97 Thunderbolt | mp\_weapon\_arc\_launcher.txt |
| Archer | mp\_weapon\_rocket\_launcher.txt |
| MGL | mp\_weapon\_mgl.txt |
| Charge Rifle | mp\_weapon\_defender.txt |

### **Pilot Ordnance**

| Weapon name | File name |
| :--- | :--- |
| Firestar | mp\_weapon\_thermite\_grenade.txt |
| Gravitystar | mp\_weapon\_grenade\_gravity.txt |
| Satchel | mp\_weapon\_satchel.txt |
| Arc nade | mp\_weapon\_grenade\_emp.txt |

### **Titan Weapon**

| Weapon name | File name |
| :--- | :--- |
| Northstar | mp\_titanweapon\_sniper.txt |
| Ion | mp\_titanweapon\_particle\_accelerator.txt |
| Tone | mp\_titanweapon\_sticky\_40mm.txt |
| Ronin | mp\_titanweapon\_leadwall.txt |
| Scorch | mp\_titanweapon\_meteor |
| Legion | mp\_titanweapon\_predator\_canon.txt |

### **Titan Core**

| Weapon name | File name |
| :--- | :--- |
| Northstar | mp\_titanweapon\_flightcore\_rockets.txt |
| Ion | mp\_titancore\_lasercannon.txt |
| Tone | mp\_titancore\_salvo\_core.txt |

### **Titan Ordnance**

| Weapon name | File name |
| :--- | :--- |
| Northstar | mp\_titanweapon\_dumbfire\_rockets.txt |
| Ion | mp\_titanweapon\_laser\_lite.txt |
| Ronin | mp\_titanweapon\_arc\_wave.txt |
| Scorch | mp\_titanweapon\_flame\_wall.txt |
| Tone | mp\_titanweapon\_salvo\_rockets.txt |

