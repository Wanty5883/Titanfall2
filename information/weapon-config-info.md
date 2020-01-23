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
| **`Pilot Weapon`** |  |  |
| Cold War | P\_plasma\_proj\_MD |  |
| Cold War | P\_plasma\_proj\_MD\_amp | Amped |
| DMR | garand\_trail\_smoke | Not used by default |
| Double Take | P\_doubletake\_proj |  |
| EPG | P\_plasma\_proj\_LG\_DLight |  |
| EPG | P\_plasma\_proj\_LG\_amp | Amped |
| Kraber | weapon\_kraber\_projectile |  |
| Kraber | weapon\_kraber\_projectile\_burn | Amped |
| LSTAR | P\_projectile\_lstar |  |
| LSTAR | P\_projectile\_lstar\_burn | Amped |
| Mastiff | P\_mastiff\_proj |  |
| Mastiff | P\_mastiff\_proj\_amp | Amped |
| Rocket Launcher | Rocket\_Smoke\_Large |  |
| Rocket Launcher | Rocket\_Smoke\_Large\_burn | Amped |
| SMR | Rocket\_Smoke\_SMR |  |
| SMR | Rocket\_Smoke\_SMR\_burn | Amped |
| Softball | wpn\_grenade\_frag\_softball |  |
| Softball | wpn\_grenade\_frag\_softball\_burn | Amped |
| Spitfire | wpn\_grenade\_frag\_mag |  |
| Spitfire | wpn\_grenade\_frag\_mag\_burn | Amped |
| Thunderbolt | P\_wpn\_arcball\_trail |  |
| Thunderbolt | P\_wpn\_arcball\_trail\_amp | Amped |
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
| Arc Trap | P\_arcTrap\_light | FD content |
|  | test\_projectile |  |
|  | P\_sspectre\_proj |  |
| Spectre Spawner | P\_drone\_launch\_trail |  |
| Gunship Launcher | tower\_light\_red |  |

## FX

### Pilot Ability

| FX name | Value | Note |
| :--- | :--- | :--- |
| Pulse Blade | wpn\_grenade\_sonar\_impact |  |

### Pilot Ordnance

| FX name | Value | Note |
| :--- | :--- | :--- |
| Arc Trap | P\_wpn\_arcTrap | FD content |
| Arc Trap | P\_arcTrap\_light | FD content |
| Arc Trap | P\_wpn\_arcTrap\_start | FD content |
| Arc Trap | P\_wpn\_arcTrap\_beam | FD content |
| Hardcover | P\_pilot\_cover\_shield |  |
| Hardcover | P\_pilot\_amped\_shield |  |
| Smoke Grenade | P\_wpn\_smk\_electric\_pilot |  |
| Smoke Grenade | P\_wpn\_smk\_electric\_pilot\_air |  |

### Titan

| FX name | Value | Note |
| :--- | :--- | :--- |
| Battery Generator | P\_generator\_exp |  |
| Dome Shield | P\_shield\_hld\_01\_CP | Particle system |
| Hotdrop Warp | P\_warpjump\_FP |  |
| Hotdrop Trail | hotdrop\_hld\_warp |  |

### Drones, Turret & Gunship

| FX name | Value | Note |
| :--- | :--- | :--- |
| Gunship Launcher | wpn\_grenade\_TT\_activate | Mine ignition |
| Gunship Launcher | tower\_light\_red | Mine trail |
| Gunship Launcher | Rocket\_Smoke\_Large | Mine light |

### Misc

| FX name | Value | Note |
| :--- | :--- | :--- |
| Deployable cloakfield | harvester\_base\_noise | FD content ? |
| Deployable cloakfield | harvester\_base\_glowflat | FD content ? |
| Deployable cloakfield | ar\_operator\_target\_idle | FD content ? |



## Sound

### Pilot Ability

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Holopilot | holopilot\_deploy\_1p |  |
| Holopilot | holopilot\_deploy\_3p |  |
| Pulse Blade | Pilot\_PulseBlade\_Activated\_1P |  |
| Pulse Blade | Pilot\_PulseBlade\_Activated\_3P |  |
| Pulse Blade | Pilot\_PulseBlade\_Sonar\_Pulse\_1P |  |
| Pulse Blade | Pilot\_PulseBlade\_Sonar\_Pulse\_3P |  |
| Pulse Blade | HUD\_MP\_EnemySonarTag\_Activated\_1P |  |
| Pulse Blade | HUD\_MP\_EnemySonarTag\_Flashed\_1P |  |
| Stim | pilot\_stimpack\_activate\_1P |  |
| Stim | pilot\_stimpack\_activate\_3P |  |

### Pilot Ordnance

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Arc Trap | Wpn\_ArcTrap\_Activate | FD content |
| Arc Trap | Wpn\_ArcTrap\_Beep | FD content |
| Hardcover | Hardcover\_Shield\_Start\_3P |  |
| Harcdcover | Hardcover\_Shield\_End\_3P |  |
| Proximity Mine | Weapon\_ProximityMine\_Land |  |
| Proximity Mine | Weapon\_ProximityMine\_ArmedBeep |  |
| Smoke Grenade | explo\_electric\_smoke\_impact |  |

### Pilot Weapon

| Sound name | Value | Note |
| :--- | :--- | :--- |
| **`Pilot Weapon`** |  |  |
| Arc Tool | Weapon\_BatteryGun\_FireLoop\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_FireLoop\_3P |  |
| Arc Tool | Weapon\_BatteryGun\_FireStart\_3P |  |
| Arc Tool | Weapon\_BatteryGun\_FireStop\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_Fire\_EnergyDrained\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_Fire\_EndWarning\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_CoolDownSizzle\_1P |  |
| Arc Tool | Weapon\_BatteryGun\_CoolDownSizzle\_3P |  |
| Alternator | Weapon\_Alternator\_SecondShot\_1P |  |
| Alternator | Weapon\_Alternator\_SecondShot\_3P |  |
| Alternator | Weapon\_Alternator\_SecondShot\_NPC |  |
| Charge Rifle | Weapon\_ChargeRifle\_WindUp\_1P | Charge sound |
| Charge Rifle | Weapon\_ChargeRifle\_WindUp\_3P | Charge sound |
| Charge Rifle | Weapon\_ChargeRifle\_WindDown\_1P | Unload sound |
| Charge Rifle | Weapon\_ChargeRifle\_WindDown\_3P | Unload sound |
| Cold War | Weapon\_ColdWar\_ChargeUp\_1P |  |
| Cold War | Weapon\_ColdWar\_ChargeUp\_3P |  |
| LSTAR | Weapon\_LSTAR\_Fire\_1P |  |
| LSTAR | Weapon\_LSTAR\_Fire\_3P |  |
| LSTAR | Weapon\_LSTAR\_Fire\_NPC |  |
| Thunderbolt | Weapon\_Arc\_Ball\_Loop |  |

### Titans

| Sound name | Value |  |
| :--- | :--- | :--- |
| Arc Cannon | arc\_cannon\_charge |  |
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
| Laser Shot | Weapon\_ShoulderLaser\_Fire\_3P |  |
| Laser Shot | Weapon\_ShoulderLaser\_Fire\_3P |  |
| Laser Shot | Weapon\_ShoulderLaser\_StutterBuild\_1P | Charge sound |
| Laser Shot | Weapon\_ShoulderLaser\_StutterBuild\_3P | Charge sound |
| Laser Trip Wire | Wpn\_LaserTripMine\_Deploy\_1P |  |
| Laser Trip Wire | Wpn\_LaserTripMine\_Deploy\_3P |  |

### Tone

| Sound name | Value | Note |
| :--- | :--- | :--- |
| 40mm | Weapon\_bulletCasings.Bounce |  |
| 40mm | Weapon\_40mm\_Fire\_1P |  |
| 40mm | Weapon\_40mm\_Fire\_3P |  |
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

### Ronin

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Leadwall | Weapon\_Leadwall\_Fire\_1P |  |
| Leadwall | Weapon\_Leadwall\_Fire\_3P |  |
| Arc Wave | arcwave\_fire\_1p |  |
| Arc Wave | arcwave\_fire\_3p |  |
| Arc Wave | Weapon\_ShoulderLaser\_StutterBuild\_02 |  |
| Sword Block | Weapon\_ShoulderLaser\_StutterBuild\_1P |  |
| Sword Block | ronin\_sword\_draw\_02\_3p |  |

### Scorch

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Meteor Cannon | Weapon\_bulletCasings.Bounce |  |
| Meteor Cannon | weapon\_thermitelauncher\_fire\_1p |  |
| Meteor Cannon | weapon\_thermitelauncher\_fire\_3p |  |
| Incendiary Trap | incendiary\_trap\_deploy\_1p |  |
| Incendiary Trap | incendiary\_trap\_deploy\_3p |  |
| Thermal Shield | heat\_shield\_1p\_loop |  |
| Thermal Shield | heat\_shield\_3p\_loop |  |

### Legion

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Predator Cannon | Weapon\_Predator\_SecondShot\_1P |  |
| Predator Cannon | Weapon\_Predator\_SecondShot\_3P |  |
| Predator Cannon | weapon\_predator\_winddown\_1p | Unload sound |
| Predator Cannon | weapon\_predator\_winddown\_3p | Unload sound |
| Power Shot | Weapon\_Predator\_Powershot\_ChargeUp\_1P |  |
| Power Shot | Weapon\_Predator\_Powershot\_ChargeUp\_3P |  |

### Drones, Turret & Gunship

| Sound name | Value | Note |
| :--- | :--- | :--- |
| Drones | Drone\_Beam\_Charge |  |
| Gunship Launcher | NPE\_Missile\_Alarm |  |
| Gunship Launcher | Triple\_Threat\_Grenade\_Charge |  |
| Gunship Missile | Weapon\_ARL.Single |  |
| Gunship Missile | ShoulderRocket\_Salvo\_Fire\_3P |  |
| Mega Turret | MegaTurret\_Laser\_ChargeUp\_3P | Not used by default |

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

