---
description: List of information for the weapon config files
---

# Weapon config info

## Introduction & Warning

This page is quite... big due to the big amount of information around weapon config files and I plan to add even more. So for the sake of your mental health refer to the content summary on the right side of your screen. I done title and subtile to make it easier !

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

### b. Impact values

| Impact name | Value | Note |
| :--- | :--- | :--- |
| **`Pilot Ability`** |  |  |
| Pulse Blade | wpn\_grenade\_sonar\_impact | Impact effect |

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
| wpn\_arc\_cannon\_beam | Arc Cannon |  |
| wpn\_arc\_cannon\_beam\_mod | Arc Cannon |  |
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

| Projectile name | Value | Note |
| :--- | :--- | :--- |
| **`Pilot Ordnance`** |  |  |
| Electric Smoke | P\_wpn\_smk\_electric\_pilot |  |
| Electric Smoke | P\_wpn\_smk\_electric\_pilot\_air |  |
| Firestar | P\_grenade\_thermite\_trail |  |
| Frag Grenade | wpn\_grenade\_frag |  |
| Gravity Star | wpn\_grenade\_frag\_blue | Blue projectile |
| Gravity Star | P\_wpn\_grenade\_gravity | Vortex FX |
| Gravity Star | P\_gravity\_mine\_FP | Screen FX |
| Tether Trap | P\_tether\_explosive\_light | Not used by default |
| **`Pilot Ability`** |  |  |
| Pulse Blade | wpn\_grenade\_sonar | Orange projectile |
| Pulse Blade | wpn\_grenade\_sonar\_impact | Impact effect |
| **`Northstar`** |  |  |
| Railgun | P\_titan\_sniper1 | Uncharged |
| Railgun | P\_titan\_sniper2 | Half charged |
| Railgun | P\_titan\_sniper3 | Full charged |
| Railgun | P\_wpn\_tracer\_sniper | Disable by default |
| Hover | P\_FlightCore\_trail |  |
| **`Tone`** |  |  |
| 40MM | weapon\_40mm\_projectile |  |
| Salvo Core | P\_SalvoCore\_trail |  |
| Mortar Rockets | P\_Rocket\_Mortar | FD content |
| Sonar Pulse | wpn\_grenade\_sonar\_titan | Orange trail |
| Sonar Pulse | wpn\_grenade\_sonar\_titan\_AMP | FD content |
| **`Ronin`** |  |  |
| Leadwall | P\_leadwall\_proj |  |
| Leadwall | P\_dragonsbreath\_trail |  |
| Electric Ronin | elite\_smoke\_rise | FD content |
| **`Scorch`** |  |  |
| Thermite Launcher | P\_wpn\_meteor\_trail |  |
| Flame Core | P\_xo\_meteorWave\_trail |  |
| Incendiary Trap | P\_meteor\_trap\_trail |  |
| **`Ion`** |  |  |
| Laser Trip Wire | P\_wpn\_laserTrip\_trail |  |
| **`Legion`** |  |  |
| Predator Cannon | P\_proj\_predator\_alt\_pwr | Red projectile |
| **`Monarch`** |  |  |
| Chaingun | P\_projectile\_TPA |  |
| **`Misc`** |  |  |
|  | P\_projectile\_turretplasma\_mega |  |
| Drones | P\_plasma\_proj\_SM | FD content |
| Electric Drones | dissolve\_CH\_arcs | FD content |
|  | Rocket\_Smoke\_Small\_Titan |  |
|  | Rocket\_Smoke\_SMALL\_Titan\_2 |  |
|  | Rocket\_Smoke\_SMALL\_Titan\_mod |  |
|  | Rocket\_Smoke\_Small\_Titan\_s2s | SP content |
|  | wpn\_grenade\_TT | Related to gunship |
|  | wpn\_grenade\_TT\_mag | Related to gunship |
|  | wpn\_grenade\_TT\_activate | Related to Scorch |
|  | test\_projectile |  |
|  | P\_sspectre\_proj |  |
| Spectre Spawner | P\_drone\_launch\_trail |  |
| Gunship Launcher | tower\_light\_red |  |

## FX

### Pilot Ability

| FX name | Value | Note |
| :--- | :--- | :--- |
| Phase Shift | P\_phase\_shift\_main | Appear & disappear |
| Phase Shift | P\_phase\_shift\_main\_XO | Titan value |
| Phase Shift | P\_phase\_shift\_screen | Screen FX |
| Phase Shift | P\_phase\_shift\_screen\_start |  |
| Pulse Blade | wpn\_grenade\_sonar\_impact | Impact effect |
| Pulse Blade | P\_ar\_sonar\_CP\_amp |  |
| Pulse Blade | P\_ar\_sonar\_CP |  |
| Pulse Blade | P\_ar\_holopulse\_CP |  |
| Pulse Blade | P\_holo\_screespace |  |
| Stim | P\_heal |  |
| Stim | P\_pilot\_stim\_hld |  |

### Pilot Ordnance

| FX name | Value | Note |
| :--- | :--- | :--- |
| Arc Trap | P\_wpn\_arcTrap | FD content |
| Arc Trap | P\_arcTrap\_light | FD content |
| Arc Trap | P\_wpn\_arcTrap\_start | FD content |
| Arc Trap | P\_wpn\_arcTrap\_beam | FD content |
| Hardcover | P\_pilot\_cover\_shield |  |
| Hardcover | P\_pilot\_amped\_shield |  |
| Satchel | wpn\_laser\_blink |  |
| Satchel | wpn\_satchel\_clacker\_glow\_LG\_1 | Large |
| Satchel | wpn\_satchel\_clacker\_glow\_SM\_1 | Small |
| Smoke Grenade | P\_wpn\_smk\_electric\_pilot |  |
| Smoke Grenade | P\_wpn\_smk\_electric\_pilot\_air |  |

### Pilot Weapon

| FX name | Value | Note |
| :--- | :--- | :--- |
| Arc Tool | P\_charge\_tool\_charge\_FP |  |
| Arc Tool | P\_elec\_arc\_loop\_LG\_1 |  |
| Arc Tool | acl\_light\_red |  |
| Arc Tool | acl\_light\_green |  |
| Arc Tool | wpn\_arc\_cannon\_beam\_mod |  |
| Arc Tool | P\_ArcSwitch\_open |  |
| Arc Tool | P\_ArcSwitch\_open\_far |  |
| Arc Tool | P\_ArcSwitch\_close |  |
| Arc Tool | P\_ArcSwitch\_close\_far |  |
| Cold War | P\_plasma\_proj\_MD |  |
| Cold War | P\_plasma\_proj\_MD\_amp | Amped projectile |
| DMR | wpn\_mflash\_snp\_hmn\_smoke\_side\_FP |  |
| DMR | wpn\_mflash\_snp\_hmn\_smoke\_side |  |
| DMR | garand\_trail\_smoke | Not used by default |
| DMR | Rocket\_Smoke\_SMR\_Glow |  |
| Double Take | P\_doubletake\_proj |  |
| Double Take | P\_doubletake\_proj\_burn | Amped projectile |
| Double Take | P\_dragonsbreath\_trail | Not used by default |
| Double Take | doubletake\_bullet | Impact effect |
| Double Take | P\_wpn\_mflash\_dbltake\_FP |  |
| Double Take | P\_wpn\_mflash\_dbltake |  |
| Double Take | P\_wpn\_mflash\_dbltake\_FP\_burn | Amped muzzleflash FP |
| Double Take | P\_wpn\_mflash\_dbltake\_burn | Amped muzzleflash |
| Kraber | wpn\_mflash\_snp\_hmn\_smoke\_side\_FP |  |
| Kraber | wpn\_mflash\_snp\_hmn\_smoke\_side |  |
| LSTAR | wpn\_mflash\_snp\_hmn\_smokepuff\_side\_FP | Cooldown effect |
| LSTAR | wpn\_mflash\_snp\_hmn\_smokepuff\_side | Cooldown effect |
| LSTAR | xo\_spark\_med | Burnout effect |

### Titan

| FX name | Value | Note |
| :--- | :--- | :--- |
| Arc Ball | P\_impact\_exp\_emp\_med\_air |  |
| Arc Ball | wpn\_arc\_cannon\_charge\_fp |  |
| Arc Ball | wpn\_arc\_cannon\_charge |  |
| Arc Cannon | wpn\_arc\_cannon\_electricity\_fp |  |
| Arc Cannon | wpn\_arc\_cannon\_electricity |  |
| Arc Cannon | impact\_arc\_cannon\_titan |  |
| Arc Cannon | wpn\_arc\_cannon\_beam |  |
| Arc Cannon | wpn\_arc\_cannon\_beam\_mod |  |
| Arc Cannon | exp\_arc\_cannon |  |
| Arc Cannon | wpn\_muzzleflash\_arc\_cannon\_fp |  |
| Arc Cannon | wpn\_muzzleflash\_arc\_cannon |  |
| Arc Cannon | impact\_arc\_cannon\_titan |  |
| Arc Cannon | P\_emp\_body\_human |  |
| Atlas | P\_titan\_doom\_stage\_1 | ParticleSystem |
| Atlas | P\_titan\_doom\_stage\_2 | ParticleSystem |
| Atlas | P\_titan\_doom\_stage\_3 | ParticleSystem |
| Atlas | P\_xo\_damage\_fire\_1 | ParticleSystem |
| Atlas | P\_xo\_damage\_fire\_2 | ParticleSystem |
| Atlas | P\_xo\_damage\_fire\_2\_alt | ParticleSystem |
| Atlas | xo\_damage\_exp\_1 | ParticleSystem |
| Atlas | xo\_damage\_exp\_2 | ParticleSystem |
| Atlas | xo\_damage\_lvl\_1\_elec | ParticleSystem |
| Atlas | xo\_dmg\_gibs | ParticleSystem |
| Atlas | xo\_exp\_death | ParticleSystem |
| Atlas | xo\_health\_dam\_exhaust\_fire\_1 | TagHealthFX |
| Atlas | xo\_health\_exhaust\_white\_1 | TagHealthFX |
| Atlas | xo\_health\_fire\_vent | TagHealthFX |
| Atlas | xo\_health\_smoke\_white | TagHealthFX |
| Atlas | xo\_spark\_med | ParticleSystem |
| Atlas | P\_titan\_doom\_body | TagHealthFX |
| Atlas | P\_titan\_doom\_body\_beams | TagHealthFX |
| Atlas | P\_xo\_damage\_fire\_1 | TagHealthFX |
| Atlas | P\_xo\_damage\_fire\_2 | TagHealthFX |
| Atlas | P\_xo\_damage\_fire\_1\_XL | TagHealthFX |
| Atlas | P\_xo\_damage\_fire\_2\_XL | TagHealthFX |
| Battery Generator | P\_generator\_exp |  |
| Dome Shield | P\_shield\_hld\_01\_CP | Particle system |
| Hotdrop Warp | P\_warpjump\_FP |  |
| Hotdrop Trail | hotdrop\_hld\_warp |  |
| Titancore Utility | P\_titan\_core\_atlas\_blast |  |
| Titancore Utility | P\_titan\_core\_atlas\_charge |  |

### Ion

| FX name | Value | Note |
| :--- | :--- | :--- |
| Laser Core | P\_wpn\_lasercannon\_aim | Aim |
| Laser Core | P\_lasercannon\_core | Core |
| Laser Core | P\_handlaser\_charge | Muzzleflash |
| Vortex Shield | P\_impact\_xo\_shield\_cp |  |
| Vortex Shield | P\_impact\_exp\_med\_xo\_shield\_CP |  |

### Tone

| FX name | Value | Note |
| :--- | :--- | :--- |
| 40MM | wpn\_mflash\_40mm\_smoke\_side |  |
| 40MM | wpn\_mflash\_40mm\_smoke\_side\_FP |  |
| 40MM | P\_scope\_glint |  |
| Sonar | P\_ar\_sonar\_CP\_amp |  |
| Sonar | P\_ar\_sonar\_CP |  |
| Sonar | P\_ar\_holopulse\_CP |  |
| Sonar | P\_holo\_screespace |  |

### Monarch

| FX name | Value | Note |
| :--- | :--- | :--- |
| Upgrade Core | P\_wpn\_lasercannon\_aim |  |

### Ronin

| FX name | Value | Note |
| :--- | :--- | :--- |
| Arc Wave | P\_arcwave\_exp |  |
| Arc Wave | P\_arcwave\_exp\_charged |  |
| Arc Wave | P\_emp\_body\_human |  |
| Arc Wave | P\_emp\_body\_titan |  |
| Sword Block | P\_impact\_xo\_sword |  |

### Scorch

| FX name | Value | Note |
| :--- | :--- | :--- |
| Flame Core | P\_impact\_exp\_xsmll\_metal |  |
| Flame Core | P\_impact\_exp\_med\_metal |  |
| Flame Core | flamewave\_blast\_left |  |
| Flame Core | flamewave\_blast\_middle |  |
| Flame Core | flamewave\_blast\_right |  |
| Flamewall | P\_wpn\_meteor\_wall |  |
| Flamewall | P\_wpn\_meteor\_wall\_s2s |  |
| Flamewall | impact\_exp\_burst\_FRAG\_2 |  |
| Thermal Shield | P\_wpn\_HeatShield |  |
| Thermal Shield | P\_wpn\_HeatShield\_FP |  |
| Thermal Shield | P\_wpn\_HeatShield\_impact | Absorb effect |
| Thermal Shield | P\_wpn\_HeatSheild\_burn\_titan | Impact |
| Thermal Shield | P\_wpn\_HeatSheild\_burn\_human | Impact |
| Thermal Shield | P\_impact\_exp\_emp\_med\_air | Particle |

### Legion

| FX name | Value | Note |
| :--- | :--- | :--- |
| Predator Cannon | P\_predator\_barrel\_blur\_FP |  |
| Predator Cannon | P\_predator\_barrel\_blur |  |

### Drones, Turret & Gunship

| FX name | Value | Note |
| :--- | :--- | :--- |
| Bomber | P\_veh\_crow\_exp\_sml | TagHealthFX |
| Bomber | xo\_health\_smoke\_white | TagHealthFX |
| Bomber | veh\_chunk\_trail | TagHealthFX |
| Drone Plasma | P\_wpn\_sspectre\_charge |  |
| Drone Plasma | P\_wpn\_muzzleflash\_epg |  |
| Drone Rocket | P\_wpn\_drone\_charge |  |
| Dropship | xo\_atlas\_jet\_large | Thrusters |
| Dropship | veh\_gunship\_damage\_FULL |  |
| Dropship | P\_veh\_exp\_crow |  |
| Dropship | runway\_light\_blue |  |
| Dropship | acl\_light\_green |  |
| Dropship | acl\_light\_red |  |
| Dropship | acl\_light\_white |  |
| Mega Turret | wpn\_muzzleflash\_mega\_trrt |  |
| Mega Turret | wpn\_shelleject\_40mm |  |
| Gunship Launcher | wpn\_grenade\_TT\_activate | Mine ignition |
| Gunship Launcher | tower\_light\_red | Mine trail |
| Gunship Launcher | Rocket\_Smoke\_Large | Mine light |
| Turret | runway\_light\_red | Red glow |
| Turret | runway\_light\_blue | Blue glow |
| Turret | xo\_health\_exhaust\_white\_1 | TagHealthFX |
| Turret | xo\_damage\_exp\_2 | TagHealthFX |
| Turret | P\_sup\_spec\_dam\_vent\_1 | TagHealthFX |
| Turret | xo\_damage\_exp\_2 | TagHealthFX |
| Turret | sup\_spec\_vent\_fire\_1 | TagHealthFX |
| Turret | xo\_spark\_med | TagHealthFX |
| Stalkers | P\_sparks\_dir\_MD\_LOOP |  |
| Stalkers | P\_spectre\_dmg\_elec |  |
| Stalkers | P\_spectre\_dmg\_fire |  |
| Stalkers | P\_spectre\_dmg\_smk |  |
| Stalkers | P\_stalker\_eye\_foe |  |
| Stalkers | P\_stalker\_eye\_friend |  |
| Super Specter | P\_wpn\_sspectre\_charge |  |
| Super Specter | P\_wpn\_muzzleflash\_sspectre |  |
| Super Specter | P\_sup\_spectre\_death |  |
| Super Specter | P\_sup\_spectre\_death\_nuke |  |
| Super Specter | P\_xo\_damage\_fire\_2 |  |
| Super Specter | P\_sup\_spec\_dam\_vent\_1 |  |
| Super Specter | P\_sup\_spec\_dam\_vent\_2 |  |
| Super Specter | P\_sup\_spectre\_dam\_1 |  |
| Super Specter | P\_sup\_spectre\_dam\_2 |  |
| Super Specter | drone\_dam\_smoke\_2 |  |
| Super Specter | superSpectre\_groundSlam\_impact | Impact effect |
| Super Specter | superSpectre\_megajump\_land | Impact effect |

### Misc

| FX name | Value | Note |
| :--- | :--- | :--- |
| Beacon | veh\_birm\_warp\_in\_FULL | Not used |
| Beacon | veh\_carrier\_warp\_FULL |  |
| Beacon | veh\_carrier\_warp\_full |  |
| Beacon | veh\_red\_warp\_in\_full\_SB | Redeye |
| Beacon | veh\_birm\_warp\_in\_FULL | Bermingham |
| Beacon | veh\_contrails\_01 |  |
| Beacon | veh\_jetwash\_exit\_eng\_blast |  |
| Beacon | P\_wpn\_charge\_tool\_beam\_HOLO | Charge ghost effect |
| Deployable Cloakfield | harvester\_base\_noise | FD content ? |
| Deployable Cloakfield | harvester\_base\_glowflat | FD content ? |
| Deployable Cloakfield | ar\_operator\_target\_idle | FD content ? |
| Orbital Strike | wpn\_orbital\_beam |  |
| Orbital Strike | ar\_rocket\_strike\_small\_friend |  |
| Orbital Strike | ar\_rocket\_strike\_small\_foe |  |
| Orbital Strike | ar\_rocket\_strike\_large\_friend |  |
| Orbital Strike | ar\_rocket\_strike\_large\_foe |  |
| Pickups | P\_ar\_titan\_droppoint | Pickup glow FX \(battery ?\) |
| Pickups | P\_item\_bluelion | Collectible flox FX \(helmet\) |
| Proto Hold Beam | elite\_smoke\_rise |  |
| Proto Hold Beam | dissolve\_CH\_arcs |  |



## Sound

### Pilot Ability

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Cloak | coop\_sentrygun\_deploymentdeniedbeep |  |
| Cloak | bc\_pCloak | Chatter event |
| Cloak | HUD\_kit\_meter\_replenished\_1P |  |
| Holopilot | holopilot\_deploy\_1p |  |
| Holopilot | holopilot\_deploy\_3p |  |
| Phase Shift | Pilot\_PhaseShift\_PreActivate\_1P |  |
| Phase Shift | Pilot\_PhaseShift\_PreActivate\_3P |  |
| Phase Shift | Pilot\_PhaseShift\_Loop\_1P |  |
| Phase Shift | Pilot\_PhaseShift\_Loop\_3P |  |
| Phase Shift | Pilot\_PhaseShift\_WarningToEnd\_1P |  |
| Phase Shift | Pilot\_PhaseShift\_WarningToEnd\_3P |  |
| Pulse Blade | Pilot\_PulseBlade\_Activated\_1P |  |
| Pulse Blade | Pilot\_PulseBlade\_Activated\_3P |  |
| Pulse Blade | Pilot\_PulseBlade\_Sonar\_Pulse\_1P |  |
| Pulse Blade | Pilot\_PulseBlade\_Sonar\_Pulse\_3P |  |
| Pulse Blade | HUD\_MP\_EnemySonarTag\_Activated\_1P |  |
| Pulse Blade | HUD\_MP\_EnemySonarTag\_Flashed\_1P |  |
| Stim | pilot\_stimpack\_activate\_1P |  |
| Stim | pilot\_stimpack\_activate\_3P |  |
| Stim | pilot\_stimpack\_deactivate\_1P |  |
| Stim | pilot\_stimpack\_deactivate\_3P |  |
| Stim | pilot\_stimpack\_loop\_1P |  |
| Stim | pilot\_stimpack\_loop\_3P |  |
| Stim | bc\_pStim | Chatter event |

### Pilot Ordnance

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Arc Trap | Wpn\_ArcTrap\_Activate | FD content |
| Arc Trap | Wpn\_ArcTrap\_Beep | FD content |
| Hardcover | Hardcover\_Shield\_Start\_3P |  |
| Harcdcover | Hardcover\_Shield\_End\_3P |  |
| Proximity Mine | Weapon\_ProximityMine\_Land |  |
| Proximity Mine | Weapon\_ProximityMine\_ArmedBeep |  |
| Satchel | weapon\_r1\_satchel.throw |  |
| Smoke Grenade | explo\_electric\_smoke\_impact |  |

### Pilot Weapon

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Arc Tool | Weapon\_BatteryGun\_FireLoop\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_FireLoop\_3P |  |
| Arc Tool | Weapon\_BatteryGun\_FireStart\_3P |  |
| Arc Tool | Weapon\_BatteryGun\_FireStop\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_Fire\_EnergyDrained\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_Fire\_EndWarning\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_CoolDownSizzle\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_CoolDownSizzle\_3P |  |
| Arc Tool | ArcTool\_SmallPanel\_DeActivate |  |
| Arc Tool | ArcTool\_SmallPanel\_Beep |  |
| Alternator | Weapon\_Alternator\_SecondShot\_1P |  |
| Alternator | Weapon\_Alternator\_SecondShot\_3P |  |
| Alternator | Weapon\_Alternator\_SecondShot\_NPC |  |
| Charge Rifle | Weapon\_ChargeRifle\_WindUp\_1P | Charge sound |
| Charge Rifle | Weapon\_ChargeRifle\_WindUp\_3P | Charge sound |
| Charge Rifle | Weapon\_ChargeRifle\_WindDown\_1P | Unload sound |
| Charge Rifle | Weapon\_ChargeRifle\_WindDown\_3P | Unload sound |
| Cold War | Weapon\_ColdWar\_ChargeUp\_1P |  |
| Cold War | Weapon\_ColdWar\_ChargeUp\_3P |  |
| DMR | large\_shell\_drop |  |
| Double Take | wpn\_pickup\_Rifle\_1P |  |
| Double Take | Weapon\_DoubleTake\_Fire\_1P |  |
| Double Take | Weapon\_DoubleTake\_Fire\_3P |  |
| Double Take | Weapon\_DoubleTake\_Fire\_NPC |  |
| Double Take | large\_shell\_drop |  |
| Double Take | large\_shell\_drop |  |
| Double Take | DoubleTake\_LowAmmo\_Shot1 |  |
| Double Take | DoubleTake\_LowAmmo\_Shot2 |  |
| Double Take | DoubleTake\_LowAmmo\_Shot3 |  |
| Double Take | Weapon\_Rangemaster\_Kraber\_ADS\_In |  |
| Double Take | Weapon\_Rangemaster\_Kraber\_ADS\_Out |  |
| LSTAR | Weapon\_LSTAR\_Fire\_1P |  |
| LSTAR | Weapon\_LSTAR\_Fire\_3P |  |
| LSTAR | Weapon\_LSTAR\_Fire\_NPC |  |
| LSTAR | lstar\_lowammowarning | Warning sound |
| LSTAR | LSTAR\_LensBurnout | Burnout sound |
| LSTAR | LSTAR\_LensBurnout\_3P | Burnout sound |
| Melee | Player\_Melee\_Backhand\_1P |  |
| Melee | player\_melee\_kick\_3p |  |
| Smart Pistol | Weapon\_SmartPistol\_Fire\_1P |  |
| Smart Pistol | Weapon\_SmartPistol\_Fire\_3P |  |
| Smart Pistol | Weapon\_SmartPistol\_SuppressedFire\_1P |  |
| Smart Pistol | Weapon\_SmartPistol\_SuppressedFire\_3P |  |
| Thunderbolt | Weapon\_Arc\_Ball\_Loop |  |
| Thunderbolt | Weapon\_ArcLauncher\_Fire\_1P |  |
| Thunderbolt | Weapon\_ArcLauncher\_Fire\_3P |  |

### Titans

| Sound name | Value |  |
| :--- | :--- | :--- |
| Arc Cannon | Explo\_ProximityEMP\_Impact\_3P |  |
| Arc Cannon | Weapon\_ArcLauncher\_Fire\_1P |  |
| Arc Cannon | Weapon\_ArcLauncher\_Fire\_3P |  |
| Arc Cannon | arc\_cannon\_charge |  |
| Arc Cannon | arc\_cannon\_charged\_loop |  |
| Arc Cannon | Arc\_Rifle\_charged\_Loop\_1P |  |
| Arc Cannon | Arc\_Rifle\_charged\_Loop\_3P |  |
| Arc Cannon | Titan\_Blue\_Electricity\_Cloud |  |
| Arc Cannon | weapon\_arc\_ball\_tendril |  |
| Titancore Utility | Titan\_CoreAbility\_Sustain\_Long |  |
| Titancore Utility | Titan\_CoreAbility\_Sustain |  |
| Triple Threat | Wpn\_TripleThreat\_Grenade\_MineAttach |  |
| Warpfall | Titan\_1P\_Warpfall\_Hotdrop |  |
| Warpfall | Titan\_1P\_Warpfall\_Start |  |
| Warpfall | Titan\_3P\_Warpfall\_Start |  |
| Warpfall | Titan\_3P\_Warpfall\_CallIn |  |
| Warpfall | Titan\_3P\_Warpfall\_WarpToLanding |  |
| Warpfall | Titan\_1P\_Warpfall\_WarpToLanding\_fast |  |
| Warpfall | Titan\_3P\_Warpfall\_WarpToLanding\_fast |  |
| Warpfall | titan\_hot\_drop\_turbo\_begin |  |
| Warpfall | titan\_hot\_drop\_turbo\_begin\_3P |  |
|  | Weapon\_Vortex\_Gun.ExplosiveWarningBeep |  |

### Ion

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Laser Core | Titan\_Core\_Laser\_FireBeam\_1P\_extended |  |
| Laser Core | Titan\_Core\_Laser\_Fire\_EndWarning\_1P |  |
| Laser Core | Titan\_Core\_Laser\_FireBeam\_1P |  |
| Laser Core | Titan\_Core\_Laser\_FireBeam\_3P |  |
| Laser Core | Titan\_Core\_Laser\_FireStart\_1P |  |
| Laser Core | Titan\_Core\_Laser\_FireStart\_3P |  |
| Laser Core | Titan\_Core\_Laser\_FireStop\_1P |  |
| Laser Core | Titan\_Core\_Laser\_FireStop\_3P |  |
| Laser Core | Titan\_Core\_Laser\_ChargeUp\_1P |  |
| Laser Core | Titan\_Core\_Laser\_ChargeUp\_3P |  |
| Laser Shot | Weapon\_ShoulderLaser\_Fire\_3P |  |
| Laser Shot | Weapon\_ShoulderLaser\_Fire\_3P |  |
| Laser Shot | Weapon\_ShoulderLaser\_StutterBuild\_1P | Charge sound |
| Laser Shot | Weapon\_ShoulderLaser\_StutterBuild\_3P | Charge sound |
| Laser Trip Wire | Wpn\_LaserTripMine\_Deploy\_1P |  |
| Laser Trip Wire | Wpn\_LaserTripMine\_Deploy\_3P |  |
| Vortex Shield | Weapon\_Vortex\_Gun.ExplosiveWarningBeep |  |
| Vortex Shield | vortex\_impact\_sound\_1p |  |
| Vortex Shield | vortex\_impact\_sound\_3p |  |
| Vortex Shield | Weapon.Explosion\_Med |  |

### Tone

| Sound name | Value | Note |
| :--- | :--- | :--- |
| 40mm | Weapon\_bulletCasings.Bounce |  |
| 40mm | Weapon\_40mm\_Fire\_1P |  |
| 40mm | Weapon\_40mm\_Fire\_3P |  |
| 40MM | weapon\_40mm\_burstloader\_leveltick\_1 |  |
| 40MM | weapon\_40mm\_burstloader\_leveltick\_2 |  |
| 40MM | weapon\_40mm\_burstloader\_leveltick\_3 |  |
| 40MM | Weapon\_Sidwinder\_Projectile | Mortar |
| 40MM | HUD\_40mm\_TrackerBeep\_Locked |  |
| 40MM | HUD\_40mm\_TrackerBeep\_Hit |  |
| Sonar Pulse | Titan\_Tone\_SonarLock\_Fired\_ShoulderPod\_1P |  |
| Sonar Pulse | Titan\_Tone\_SonarLock\_Fired\_ShoulderPod\_3P |  |
| Particule Wall | ShieldWall\_Deploy |  |
| Salvo Core | ShoulderRocket\_Salvo\_Fire\_1P |  |
| Salvo Core | ShoulderRocket\_Salvo\_Fire\_3P |  |
| Salvo Core | weapon\_coreability\_salvo\_fire\_chargeup\_1p |  |
| Salvo Core | weapon\_coreability\_salvo\_chargeup\_3p |  |

### Northstar

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Railgun | Weapon\_Titan\_Sniper\_WindUp | Charge sound |
| Railgun | Weapon\_Titan\_Sniper\_WindUp\_Amped | FD content |
| Railgun | Weapon\_Titan\_Sniper\_WindDown | Unload sound |
| Railgun | Weapon\_Titan\_Sniper\_SustainLoop | Loop sound |
| Railgun | Weapon\_Titan\_Sniper\_Level\_1\_1P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_1\_3P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_2\_1P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_2\_3P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_3\_1P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_3\_3P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_4\_1P |  |
| Railgun | Weapon\_Titan\_Sniper\_Level\_4\_3P |  |
| Cluster Missile | ShoulderRocket\_Cluster\_Fire\_1P |  |
| Cluster Missile | ShoulderRocket\_Cluster\_Fire\_3P |  |
| Tether Trap | Wpn\_TetherTrap\_Deploy\_1P |  |
| Tether Trap | Wpn\_TetherTrap\_Deploy\_3P |  |
| Flightcore | weapon\_titan\_flightcore\_rocket\_fire\_1p |  |
| Flightcore | weapon\_titan\_flightcore\_rocket\_fire\_3p |  |

### Monarch

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Chaingun | Weapon\_XO16\_Single\_1P |  |
| Chaingun | Weapon\_XO16\_Single\_3P |  |
| Chaingun | Weapon\_XO16\_SingleAmped\_Monarch\_1P |  |
| Chaingun | Weapon\_XO16\_SingleAmped\_Monarch\_3P |  |
| Chaingun | weapon\_xo16\_singleaccel\_amped\_1p |  |
| Chaingun | weapon\_xo16\_singleaccel\_amped\_3p |  |
| Chaingun | Weapon\_XO16\_SingleAccel\_1P |  |
| Chaingun | Weapon\_XO16\_SingleAccel\_3P |  |
| Rearm | Titan\_Tone\_SonarLock\_Fired\_ShoulderPod\_1P |  |
| Rearm | Titan\_Tone\_SonarLock\_Fired\_ShoulderPod\_3P |  |
| Energy Syphon | Weapon\_EnergySyphon\_Lvl1\_Fire\_1P |  |
| Energy Syphon | Weapon\_EnergySyphon\_Lvl1\_Fire\_3P |  |
| Energy Syphon | Weapon\_EnergySyphon\_Charge\_1P |  |
| Energy Syphon | Weapon\_EnergySyphon\_Charge\_3P |  |
| Chaingun amp | Weapon\_XO16\_SingleAmped\_1P |  |
| Chaingun amp | Weapon\_XO16\_SingleAmped\_3P |  |
| Tracking Rockets | ShoulderRocket\_Homing\_Fire\_1P |  |
| Tracking Rockets | ShoulderRocket\_Homing\_Fire\_3P |  |
| Rockets | ShoulderRocket\_Paint\_Fire\_1P |  |
| Rockets | ShoulderRocket\_Paint\_Fire\_3P |  |
| Upgrade Core | Weapon\_Predator\_MotorLoop\_1P |  |
| Upgrade Core | Weapon\_Predator\_MotorLoop\_3P |  |
| Upgrade Core | Weapon\_Predator\_Windup\_1P |  |
| Upgrade Core | Weapon\_Predator\_Windup\_3P |  |

### Ronin

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Arc Wave | arcwave\_fire\_1p |  |
| Arc Wave | arcwave\_fire\_3p |  |
| Arc Wave | arcwave\_tail\_3p |  |
| Arc Wave | Weapon\_ShoulderLaser\_StutterBuild\_02 |  |
| Leadwall | Weapon\_Leadwall\_Fire\_1P |  |
| Leadwall | Weapon\_Leadwall\_Fire\_3P |  |
| Phase Dash | Pilot\_PhaseShift\_PreActivate\_1P |  |
| Phase Dash | Pilot\_PhaseShift\_PreActivate\_3P |  |
| Phase Dash | titan\_phasedash\_activate\_1p |  |
| Phase Dash | titan\_phasedash\_activate\_3p |  |
| Phase Dash | titan\_phasedash\_loop\_1p |  |
| Phase Dash | titan\_phasedash\_loop\_3p |  |
| Phase Dash | titan\_phasedash\_warningtoend\_1p |  |
| Phase Dash | titan\_phasedash\_warningtoend\_3p |  |
| Phase Dash | titan\_phasedash\_end\_1p |  |
| Phase Dash | titan\_phasedash\_end\_3p |  |
| Sword Block | Weapon\_ShoulderLaser\_StutterBuild\_1P |  |
| Sword Block | ronin\_sword\_draw\_02\_3p |  |
| Sword Block | ronin\_sword\_draw\_3p |  |
| Sword Block | ronin\_sword\_bullet\_impacts |  |

### Scorch

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Flame Core | flamewave\_start\_1p |  |
| Flame Core | flamewave\_start\_3p |  |
| Flame Core | Flesh.ThermiteBurn\_3P\_vs\_1P |  |
| Flame Core | Flesh.ThermiteBurn\_1P\_vs\_3P |  |
| Flamewall | flamewall\_flame\_start |  |
| Flamewall | flamewall\_start\_1p |  |
| Flamewall | flamewall\_start\_3p |  |
| Flamewall | Explo\_ThermiteGrenade\_Impact\_3P |  |
| Flamewall | flamewall\_flame\_burn\_front |  |
| Flamewall | flamewall\_flame\_burn\_middle |  |
| Flamewall | flamewall\_flame\_burn\_end |  |
| Meteor Cannon | Weapon\_bulletCasings.Bounce |  |
| Meteor Cannon | weapon\_thermitelauncher\_fire\_1p |  |
| Meteor Cannon | weapon\_thermitelauncher\_fire\_3p |  |
| Incendiary Trap | incendiary\_trap\_deploy\_1p |  |
| Incendiary Trap | incendiary\_trap\_deploy\_3p |  |
| Thermal Shield | heat\_shield\_1p\_loop |  |
| Thermal Shield | heat\_shield\_3p\_loop |  |
| Thermal Shield | heat\_shield\_1p\_end |  |
| Thermal Shield | heat\_shield\_3p\_end |  |
| Thermal Shield | heat\_shield\_burn\_human\_1p |  |
| Thermal Shield | heat\_shield\_burn\_human\_3p |  |
| Thermal Shield | heat\_shield\_burn\_titan\_1p |  |
| Thermal Shield | heat\_shield\_burn\_titan\_3p |  |
| Thermal Shield | heat\_shield\_stop\_bullet |  |
| Thermal Shield | heat\_shield\_stop\_projectile |  |

### Legion

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Predator Cannon | Weapon\_Predator\_SecondShot\_1P |  |
| Predator Cannon | Weapon\_Predator\_SecondShot\_3P |  |
| Predator Cannon | weapon\_predator\_windup\_1p |  |
| Predator Cannon | weapon\_predator\_windup\_3p |  |
| Predator Cannon | weapon\_predator\_winddown\_1p | Unload sound |
| Predator Cannon | weapon\_predator\_winddown\_3p | Unload sound |
| Predator Cannon | Weapon\_Predator\_MotorLoop\_1P |  |
| Predator Cannon | Weapon\_Predator\_MotorLoop\_3P |  |
| Predator Cannon | wpn\_predator\_cannon\_ads\_out\_mech\_fr00\_1p |  |
| Power Shot | Weapon\_Predator\_Powershot\_ChargeUp\_1P |  |
| Power Shot | Weapon\_Predator\_Powershot\_ChargeUp\_3P |  |
| Power Shot | Weapon\_Predator\_Powershot\_ShortRange\_1P |  |
| Power Shot | Weapon\_Predator\_Powershot\_ShortRange\_3P |  |
| Power Shot | Weapon\_Predator\_Powershot\_LongRange\_1P |  |
| Power Shot | Weapon\_Predator\_Powershot\_LongRange\_3P |  |

### Drones, Turret & Gunship

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Drones | Drone\_Beam\_Charge |  |
| Drone Plasma | Drone\_Plasma\_Fire |  |
| Drone Rocket | Drone\_Weapon\_Prefire |  |
| Drone Rocket | Weapon\_ARL.Single |  |
| Drone Rocket | ShoulderRocket\_Salvo\_Fire\_3P |  |
| Mega Turret | MegaTurret\_Laser\_ChargeUp\_3P |  |
| Mega Turret | MegaTurret\_Laser\_Fire\_3P |  |
| Mega Turret | O2\_Scr\_MegaTurret\_Bridge\_Fire |  |
| Mega Turret | megaturret\_fire |  |
| Mega Turret | Weapon\_bulletCasings.Bounce |  |
| Gunship Launcher | NPE\_Missile\_Alarm |  |
| Gunship Launcher | Triple\_Threat\_Grenade\_Charge |  |
| Gunship Missile | Weapon\_ARL.Single |  |
| Gunship Missile | ShoulderRocket\_Salvo\_Fire\_3P |  |
| Mega Turret | MegaTurret\_Laser\_ChargeUp\_3P | Not used by default |
| Super Specter | Weapon\_DaemonRocket\_Launcher |  |
| Super Specter | Weapon\_DaemonRocket\_Launcher.Fire |  |
| Super Specter | Titan\_1P\_Warpfall\_Start |  |
| Super Specter | Titan\_3P\_Warpfall\_WarpToLanding |  |
| Super Specter | ai\_reaper\_nukedestruct\_warmup\_3p |  |
| Super Specter | ai\_reaper\_explo\_3p |  |

### Misc

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Orbital Strike | weapon\_titanmortar\_fire |  |
| Orbital Strike | weapon\_titanmortar\_projectile |  |

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

