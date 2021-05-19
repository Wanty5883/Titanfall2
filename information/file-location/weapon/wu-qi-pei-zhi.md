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
| R-201卡宾枪 |  mp\_weapon\_rspn101.txt |
| R-101卡宾枪 | mp\_weapon\_rspn101\_og.txt |
| 汗洛BF-R | mp\_weapon\_hemlock.txt |
| V-47平行步枪 | mp\_weapon\_vinson.txt |
| G2A5 | mp\_weapon\_g2.txt |

### **冲锋枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| CAR | mp\_weapon\_car.txt |
| 转换者冲锋枪 | mp\_weapon\_alternator\_smg.txt |
| 电能冲锋枪 | mp\_weapon\_hemlok\_smg.txt |
| R-97 | mp\_weapon\_r97.txt |

### **轻机枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 喷火枪 | mp\_weapon\_lmg.txt |
| L-STAR | mp\_weapon\_lstar.txt |
| X-55专注冲锋枪 | mp\_weapon\_esaw.txt |

### **狙击步枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 克莱博-AP狙击步枪 | mp\_weapon\_sniper.txt |
| D-2双发狙击步枪 | mp\_weapon\_doubletake.txt |
| 长弓DMR | mp\_weapon\_dmr.txt |

### **散弹枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| EVA-8自动 | mp\_weapon\_shotgun.txt |
| 獒犬散弹枪 | mp\_weapon\_mastiff.txt |

### **榴弹枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 响尾蛇飞弹 | mp\_weapon\_smr.txt |
| 能源炮-1 | mp\_weapon\_epg.txt |
| R-6P垒球榴弹枪 | mp\_weapon\_softball.txt |
| EM-4冷战榴弹枪 | mp\_weapon\_pulse\_lmg.txt |

### **手枪**

| 武器名称 | File name |
| :--- | :--- |
| 汉蒙P2016 | mp\_weapon\_semipistol.txt |
| RE-45自动 | mp\_weapon\_autopistol.txt |
| B3小帮手 | mp\_weapon\_wingman.txt |
| 小帮手精英 | mp\_weapon\_wingman\_n.txt |
| SA-3莫桑比克 | mp\_weapon\_shotgun\_pistol.txt |
| 智慧手枪 | mp\_weapon\_smart\_pistol.txt |

### **反泰坦**

| 武器名称 | File name |
| :--- | :--- |
| 电能步枪 | mp\_weapon\_defender.txt |
| 磁能榴弹发射器 | mp\_weapon\_mgl.txt |
| LG-97雷电炮 | mp\_weapon\_arc\_launcher.txt |
| 射手飞弹 | mp\_weapon\_rocket\_launcher.txt |

### **投掷物**

| 投掷物名称 | File name |
| :--- | :--- |
| 破片手榴弹 | mp\_weapon\_frag\_grenade.txt |
| 电弧手榴弹 | mp\_weapon\_grenade\_emp.txt |
| 飞火星 | mp\_weapon\_thermite\_grenade.txt |
| 重力星 | mp\_weapon\_grenade\_gravity.txt |
| 电子烟雾手榴弹 | mp\_weapon\_grenade\_electric\_smoke.txt |
| 炸药包 | mp\_weapon\_satchel.txt |

### 铁驭技能

| 技能名称 | File name |
| :--- | :--- |
| 隐形 | mp\_ability\_cloak.txt |
| 脉冲刀 | mp\_weapon\_grenade\_sonar.txt |
| 钩爪 | mp\_ability\_grapple.txt |
| • Values | scripts\players\mp\pilot\_base.set |
| 兴奋剂 | mp\_ability\_heal.txt |
| A盾 | mp\_weapon\_deployable\_cover.txt |
| 相位转移 | mp\_ability\_shifter.txt |
| 幻影 | mp\_ability\_holopilot.txt |

## **泰坦**

| 武器名称 | File name |
| :--- | :--- |
| Ability Electric Smoke | mp\_titanability\_smoke.txt |
| Global Electric Smoke | mp\_titanability\_electric\_smoke.txt |
| 核能弹射 | mp\_titanability\_nuke\_eject.txt |
| 四段火箭 | mp\_titanweapon\_rocketeer\_rocketstream.txt |

### **离子**

| 武器名称 | File name |
| :--- | :--- |
| 分裂枪 | mp\_titanweapon\_particle\_accelerator.txt |
| 镭射炮 | mp\_titanweapon\_laser\_lite.txt |
| 拌线 | mp\_titanability\_laser\_trip.txt |
| 涡流防护罩 | mp\_titanweapon\_vortex\_shield\_ion.txt |
| • Base Class | mp\_titanweapon\_vortex\_shield.txt |
| 镭射核心 | mp\_titancore\_laser\_cannon.txt |

### **烈焰**

| 武器名称 | File name |
| :--- | :--- |
| T-203铝热剂发射器 | mp\_titanweapon\_meteor.txt |
| 火墙 | mp\_titanweapon\_flame\_wall.txt |
| 燃烧陷阱 | mp\_titanability\_slow\_trap.txt |
| 热能护罩 | mp\_titanweapon\_heat\_shield.txt |
| 火焰核心 | mp\_titancore\_flame\_wave.txt |

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

