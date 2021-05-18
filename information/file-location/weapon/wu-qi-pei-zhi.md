# 武器配置

## 文件位置

这些文件的默认位置是：

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\weapons
```

## 规范

一些泰坦武器和技能的值分布在多个文件中。对于这些数据，随后的文件将在名称字段中用一个“•”表示，并简要说明附加文件与武器/能力的关系。如果它是一种通过添加附件来修改武器的能力，名称字段将显示附加文件中的{attachment name}，使用大括号表示它是附件。附件本身没有这些大括号。

## 铁驭

### 突击步枪

| 武器名称 | 文件名称 |
| :--- | :--- |
| R-201 ****Carbine |  mp\_weapon\_rspn101.txt |
| R-101 Carbine | mp\_weapon\_rspn101\_og.txt |
| Hemlock BF-R | mp\_weapon\_hemlock.txt |
| V-47 Flatline | mp\_weapon\_vinson.txt |
| G2A5 | mp\_weapon\_g2.txt |

### **冲锋枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| CAR | mp\_weapon\_car.txt |
| Alternator | mp\_weapon\_alternator\_smg.txt |
| Volt | mp\_weapon\_hemlok\_smg.txt |
| R-97 | mp\_weapon\_r97.txt |

### **轻机枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| Spitfire | mp\_weapon\_lmg.txt |
| L-STAR | mp\_weapon\_lstar.txt |
| Devotion | mp\_weapon\_esaw.txt |

### **狙击步枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| Kraber | mp\_weapon\_sniper.txt |
| Double Take | mp\_weapon\_doubletake.txt |
| Longbow DMR | mp\_weapon\_dmr.txt |

### **散弹枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| EVA-8 Auto | mp\_weapon\_shotgun.txt |
| Mastiff | mp\_weapon\_mastiff.txt |

### **榴弹枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| Sidewinder SMR | mp\_weapon\_smr.txt |
| EPG | mp\_weapon\_epg.txt |
| Softball | mp\_weapon\_softball.txt |
| EM-4 Cold War | mp\_weapon\_pulse\_lmg.txt |

### **手枪**

| 武器名称 | File name |
| :--- | :--- |
| P2016 | mp\_weapon\_semipistol.txt |
| RE-45 Auto | mp\_weapon\_autopistol.txt |
| B3 Wingman | mp\_weapon\_wingman.txt |
| Wingman Elite | mp\_weapon\_wingman\_n.txt |
| Mozambique | mp\_weapon\_shotgun\_pistol.txt |
| Smart Pistol | mp\_weapon\_smart\_pistol.txt |

### **反泰坦**

| 武器名称 | File name |
| :--- | :--- |
| Charge Rifle | mp\_weapon\_defender.txt |
| MGL | mp\_weapon\_mgl.txt |
| LG-97 Thunderbolt | mp\_weapon\_arc\_launcher.txt |
| Archer | mp\_weapon\_rocket\_launcher.txt |

### **投掷物**

| 投掷物名称 | File name |
| :--- | :--- |
| Frag Grenade | mp\_weapon\_frag\_grenade.txt |
| Arc Grenade | mp\_weapon\_grenade\_emp.txt |
| Firestar | mp\_weapon\_thermite\_grenade.txt |
| Gravity Star | mp\_weapon\_grenade\_gravity.txt |
| Electric Smoke | mp\_weapon\_grenade\_electric\_smoke.txt |
| Satchel | mp\_weapon\_satchel.txt |

### 铁驭技能

| 技能名称 | File name |
| :--- | :--- |
| Cloak | mp\_ability\_cloak.txt |
| Pulse Blade | mp\_weapon\_grenade\_sonar.txt |
| Grapple | mp\_ability\_grapple.txt |
| • Values | scripts\players\mp\pilot\_base.set |
| Stim | mp\_ability\_heal.txt |
| A-Wall | mp\_weapon\_deployable\_cover.txt |
| Phase Shift | mp\_ability\_shifter.txt |
| Holopilot | mp\_ability\_holopilot.txt |

## **泰坦**

| 武器名称 | File name |
| :--- | :--- |
| Ability Electric Smoke | mp\_titanability\_smoke.txt |
| Global Electric Smoke | mp\_titanability\_electric\_smoke.txt |
| Nuke Ejection | mp\_titanability\_nuke\_eject.txt |
| Quad Rocket | mp\_titanweapon\_rocketeer\_rocketstream.txt |

### **离子**

| 武器名称 | File name |
| :--- | :--- |
| Splitter Rifle | mp\_titanweapon\_particle\_accelerator.txt |
| Laser Shot | mp\_titanweapon\_laser\_lite.txt |
| Tripwire | mp\_titanability\_laser\_trip.txt |
| Vortex Shield | mp\_titanweapon\_vortex\_shield\_ion.txt |
| • Base Class | mp\_titanweapon\_vortex\_shield.txt |
| Laser Core | mp\_titancore\_laser\_cannon.txt |

### **烈焰**

| 武器名称 | File name |
| :--- | :--- |
| Thermite Launcher | mp\_titanweapon\_meteor.txt |
| Flame Wall | mp\_titanweapon\_flame\_wall.txt |
| Incendiary Trap | mp\_titanability\_slow\_trap.txt |
| Thermal Shield | mp\_titanweapon\_heat\_shield.txt |
| Flame Core | mp\_titancore\_flame\_wave.txt |

### **北极星**

| 武器名称 | File name |
| :--- | :--- |
| Plasma Railgun | mp\_titanweapon\_sniper.txt |
| Cluster Missile | mp\_titanweapon\_dumbfire\_rockets.txt |
| VTOL Hover | mp\_titanability\_hover.txt |
| Tether Trap | mp\_titanability\_tether\_trap.txt |
| Flight Core | mp\_titancore\_flight\_core.txt |
| • Core Weapon | mp\_titanweapon\_flightcore\_rockets.txt |

### **浪人**

| 武器名称 | File name |
| :--- | :--- |
| Leadwall | mp\_titanweapon\_leadwall.txt |
| Arc Wave | mp\_titanweapon\_arc\_wave.txt |
| Phase Dash | mp\_titanability\_phase\_dash.txt |
| Sword Block | mp\_titanability\_basic\_block.txt |
| Sword Core | mp\_titancore\_shift\_core.txt |
| • {super\_charged} | mp\_titan\_sword.txt |

### **强力**

| 武器名称 | File name |
| :--- | :--- |
| 40MM | mp\_titanweapon\_sticky\_40mm.txt |
| Tracking Rockets | mp\_titanweapon\_tracker\_rockets.txt |
| • Base Class | mp\_titanweapon\_salvo\_rockets.txt |
| Sonar Pulse | mp\_titanability\_sonar\_pulse.txt |
| Particle Wall | mp\_titanability\_particle\_wall.txt |
| Salvo Core | mp\_titancore\_salvo\_core.txt |

### **军团**

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x6B66;&#x5668;&#x540D;&#x79F0;</th>
      <th style="text-align:left">File name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Predator Cannon</td>
      <td style="text-align:left">mp_titanweapon_predator_cannon.txt</td>
    </tr>
    <tr>
      <td style="text-align:left">Power Shot</td>
      <td style="text-align:left">mp_titanability_power_shot.txt</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x2022; {CloseRangePowerShot}</p>
        <p>&#x2022; {LongRangePowerShot}</p>
      </td>
      <td style="text-align:left">mp_titanweapon_predator_cannon.txt</td>
    </tr>
    <tr>
      <td style="text-align:left">Mode Switch</td>
      <td style="text-align:left">mp_titanability_ammo_swap.txt</td>
    </tr>
    <tr>
      <td style="text-align:left">Gun Shield</td>
      <td style="text-align:left">mp_titanability_gun_shield.txt</td>
    </tr>
    <tr>
      <td style="text-align:left">Smart Core</td>
      <td style="text-align:left">mp_titancore_siege_mode.txt</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2022; {Smart_Core}</td>
      <td style="text-align:left">mp_titanweapon_predator_cannon.txt</td>
    </tr>
  </tbody>
</table>

### **帝王**

| 武器名称 | 文件名称 |
| :--- | :--- |
| XO-16 | mp\_titanweapon\_xo16\_vanguard.txt |
| Rocket Salvo | mp\_titanweapon\_salvo\_rockets.txt |
| Multi Target Missiles | mp\_titanweapon\_shoulder\_rockets.txt |
| Rearm | mp\_titanability\_rearm.txt |
| Energy Siphon | mp\_titanweapon\_stun\_laser.txt |
| Upgrade Core | mp\_titancore\_upgrade.txt |

## 杂项

| 武器名称 | 文件名称 |
| :--- | :--- |
| Orbital Strike | mp\_titanweapon\_orbital\_stike.txt |

