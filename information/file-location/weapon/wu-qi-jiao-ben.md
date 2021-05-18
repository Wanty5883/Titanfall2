# 武器脚本

## File location

The default location of those files is

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\vscripts\weapons
```

## Formatting

Several weapons and abilities have their values or critical functions spread across multiple files. For these, subsequent files will be represented by a • in the name field, along with a description, method name and/or variable name. Due to the length of certain variable and method names, the name field may instead contain a string you can search for to find the values/methods quickly, indicated by "quotation marks".

## Pilot

### Assault Rifle

| Weapon name | File name |
| :--- | :--- |
| R-201 Carbine | N/A |
| R-101 Carbine | N/A |
| Hemlock BF-R | N/A |
| V-47 Flatline | N/A |
| G2A5 | N/A |

### **Submachine Gun**

| Weapon name | File name |
| :--- | :--- |
| CAR | N/A |
| Alternator | mp\_weapon\_alternator\_smg.nut |
| Volt | N/A |
| R-97 | N/A |

### **Light Machine Gun**

| Weapon name | File name |
| :--- | :--- |
| Spitfire | mp\_weapon\_lmg.nut |
| L-STAR | mp\_weapon\_lstar.nut |
| Devotion | N/A |

### **Sniper**

| Weapon name | File name |
| :--- | :--- |
| Kraber | mp\_weapon\_sniper.nut |
| Double Take | mp\_weapon\_doubletake.nut |
| Longbow DMR | mp\_weapon\_dmr.nut |

### **Shotgun**

| Weapon name | File name |
| :--- | :--- |
| EVA-8 Auto | mp\_weapon\_shotgun.nut |
| Mastiff | mp\_weapon\_mastiff.nut |

### **Grenadier**

| Weapon name | File name |
| :--- | :--- |
| Sidewinder SMR | mp\_weapon\_smr.nut |
| EPG | N/A |
| Softball | mp\_weapon\_softball.nut |
| EM-4 Cold War | N/A |

### **Pistol**

| Weapon name | File name |
| :--- | :--- |
| P2016 | N/A |
| RE-45 Auto | N/A |
| B3 Wingman | N/A |
| Wingman Elite | N/A |
| Mozambique | mp\_weapon\_shotgun\_pistol.nut |
| Smart Pistol | mp\_weapon\_smart\_pistol.nut |

### **Anti-Titan**

| Weapon name | File name |
| :--- | :--- |
| Charge Rifle | mp\_weapon\_defender.nut |
| MGL | mp\_weapon\_mgl.nut |
| • Base Projectile | \_grenade.nut |
| LG-97 Thunderbolt | mp\_weapon\_arc\_launcher.nut |
| • FireArcBall | mp\_titanweapon\_arc\_ball.nut |
| • Values: "ball" | \scripts\vscripts\\_settings.nut |
| Archer | mp\_weapon\_rocket\_launcher.nut |

### **Ordnance**

| Ordnance name | File name |
| :--- | :--- |
| **Base Grenade** | \_grenade.nut |
| Frag Grenade | N/A |
| Arc Grenade | mp\_weapon\_grenade\_emp.nut |
| Firestar | mp\_weapon\_thermite\_grenade.nut |
| Gravity Star | mp\_weapon\_grenade\_gravity.nut |
| Electric Smoke | mp\_weapon\_grenade\_electric\_smoke.nut |
| Satchel | mp\_weapon\_satchel.nut |

### Tactical

| Tactical name | File name |
| :--- | :--- |
| Cloak | mp\_ability\_cloak.nut |
| Pulse Blade | mp\_weapon\_grenade\_sonar.nut |
| Grapple | mp\_ability\_grapple.nut |
| Stim | mp\_ability\_heal.nut |
| A-Wall | mp\_weapon\_deployable\_cover.nut |
| Phase Shift | mp\_ability\_shifter.nut |
| Holopilot | mp\_ability\_holopilot.nut |

## **Titan**

### **Ion**

| Weapon name | File name |
| :--- | :--- |
| Splitter Rifle | mp\_titanweapon\_particle\_accelerator.nut |
| Laser Shot | mp\_titanweapon\_laser\_lite.nut |
| Tripwire | mp\_titanability\_laser\_trip.nut |
| Vortex Shield | mp\_titanweapon\_vortex\_shield.nut |
| • Base Scripts | \_vortex.nut |
| Laser Core | mp\_titancore\_lasercannon.nut |

### **Scorch**

| Weapon name | File name |
| :--- | :--- |
| Thermite Launcher | mp\_titanweapon\_meteor.nut |
| Flame Wall | mp\_titanweapon\_flame\_wall.nut |
| • Segment: CreateThermiteTrail | mp\_titanweapon\_meteor.nut |
| Incendiary Trap | mp\_titanability\_slow\_trap.nut |
| Thermal Shield | mp\_titanweapon\_heat\_shield.nut |
| • Base Scripts | \_vortex.nut |
| Flame Core | mp\_titancore\_flame\_wave.nut |
| • Scr. Earth: CreateThermiteWallSegment | mp\_titanweapon\_flame\_wall.nut |

### **Northstar**

| Weapon name | File name |
| :--- | :--- |
| Plasma Railgun | mp\_titanweapon\_sniper.nut |
| • Projectile File | mp\_projectile\_titanweapon\_sniper.nut |
| Cluster Missile | mp\_titanweapon\_dumbfire\_rockets.nut |
| • Projectile File | mp\_projectile\_cluster\_rocket.nut |
| • Methods: "ClusterR" | \_weapon\_utility.nut |
| VTOL Hover | mp\_titanability\_hover.nut |
| Tether Trap | mp\_titanability\_tether\_trap.nut |
| • Tether Projectile | mp\_weapon\_tether.nut |
| Flight Core | mp\_titancore\_flight\_core.nut |
| • Core Weapon | mp\_titanweapon\_flightcore\_rockets.nut |

### **Ronin**

| Weapon name | File name |
| :--- | :--- |
| Leadwall | mp\_titanweapon\_leadwall.nut |
| Arc Wave | mp\_titanweapon\_arc\_wave.nut |
| Phase Dash | mp\_titanability\_phase\_dash.nut |
| Sword Block | mp\_titanability\_basic\_block.nut |
| Sword Core | mp\_titancore\_shift\_core.nut |

### **Tone**

| Weapon name | File name |
| :--- | :--- |
| 40MM | mp\_titanweapon\_40mm.nut |
| Tracking Rockets | mp\_titanweapon\_tracker\_rockets.nut |
| Sonar Lock | mp\_titanability\_sonar\_pulse.nut |
| Particle Wall | mp\_titanability\_particle\_wall.nut |
| Salvo Core | mp\_titanweapon\_salvo\_core.nut |

### **Legion**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Weapon name</th>
      <th style="text-align:left">File name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Predator Cannon</td>
      <td style="text-align:left">mp_titanweapon_predator_cannon.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">Power Shot</td>
      <td style="text-align:left">mp_titanability_power_shot.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x2022; hasLongRangePowerShot</p>
        <p>&#x2022; hasCloseRangePowerShot</p>
      </td>
      <td style="text-align:left">mp_titanweapon_predator_cannon.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">Mode Switch</td>
      <td style="text-align:left">mp_titanability_ammo_swap.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">Gun Shield</td>
      <td style="text-align:left">mp_titanability_gun_shield.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">Smart Core</td>
      <td style="text-align:left">mp_titancore_siege_mode.nut</td>
    </tr>
  </tbody>
</table>

### **Monarch**

| Weapon name | File name |
| :--- | :--- |
| XO-16 | mp\_titanweapon\_xo16.nut |
| Rocket Salvo | mp\_titanweapon\_salvo\_rockets.nut |
| Multi Target Missiles | mp\_titanweapon\_shoulder\_rockets.nut |
| Rearm | mp\_titanability\_rearm.nut |
| Energy Siphon | mp\_titanweapon\_stun\_laser.nut |
| Upgrade Core | mp\_titancore\_upgrade.nut |

## Common Scripts

Methods used by numerous different weapons.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method name</th>
      <th style="text-align:left">Weapon names</th>
      <th style="text-align:left">File name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Wave Script: WeaponAttackWave</td>
      <td style="text-align:left">
        <p>Arc Wave</p>
        <p>Flame Wall</p>
        <p>Incendiary Trap</p>
        <p>Flame Core</p>
      </td>
      <td style="text-align:left">_weapon_utility.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">Attack Script: ShotgunBlast</td>
      <td style="text-align:left">
        <p>EVA-8 Auto</p>
        <p>Laser Shot
          <br />Energy Siphon</p>
        <p>Close Range Power Shot</p>
        <p>Vortex Shield</p>
      </td>
      <td style="text-align:left">_weapon_utility.nut</td>
    </tr>
  </tbody>
</table>

