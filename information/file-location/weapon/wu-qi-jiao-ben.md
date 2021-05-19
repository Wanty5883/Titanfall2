# 武器脚本

## 文件位置

这些文件的默认位置是：

```text
englishclient_mp_common.bsp.pak000_dir.vpk\scripts\vscripts\weapons
```

## 规范

一些武器/技能的值或关键功能分布在多个文件之中。对于这些文件，后续文件将在“文件名称”字段中用“•”表示，并带有说明、方法名称和变量名称。由于某些变量和方法名称的长度，名称字段可能包含一个字符串，您可以搜索该字符串以快速查找值/方法，并用“引号”表示。

## 铁驭

### 突击步枪

| 武器名称 | 文件名称 |
| :--- | :--- |
| R-201卡宾枪 | N/A |
| R-101卡宾枪 | N/A |
| 汗洛BF-R | N/A |
| V-47平行步枪 | N/A |
| G2A5 | N/A |

### **冲锋枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| CAR | N/A |
| 转换者冲锋枪 | mp\_weapon\_alternator\_smg.nut |
| 电能冲锋枪 | N/A |
| R-97 | N/A |

### **轻机枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 喷火枪 | mp\_weapon\_lmg.nut |
| L-STAR | mp\_weapon\_lstar.nut |
| X-55专注冲锋枪 | N/A |

### **狙击步枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 克莱博-AP狙击步枪 | mp\_weapon\_sniper.nut |
| D-2双发狙击步枪 | mp\_weapon\_doubletake.nut |
| 长弓DMR | mp\_weapon\_dmr.nut |

### **散弹枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| EVA-8自动 | mp\_weapon\_shotgun.nut |
| 獒犬散弹枪 | mp\_weapon\_mastiff.nut |

### **榴弹枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 响尾蛇飞弹 | mp\_weapon\_smr.nut |
| 能源炮-1 | N/A |
| R-6P垒球榴弹枪 | mp\_weapon\_softball.nut |
| EM-4冷战榴弹枪 | N/A |

### **手枪**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 汉蒙P2016 | N/A |
| RE-45自动 | N/A |
| B3小帮手 | N/A |
| 小帮手精英 | N/A |
| SA-3莫桑比克 | mp\_weapon\_shotgun\_pistol.nut |
| 智慧手枪 | mp\_weapon\_smart\_pistol.nut |

### **反泰坦**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 电能步枪 | mp\_weapon\_defender.nut |
| 磁能榴弹发射器 | mp\_weapon\_mgl.nut |
| • Base Projectile | \_grenade.nut |
| LG-97雷电炮 | mp\_weapon\_arc\_launcher.nut |
| • FireArcBall | mp\_titanweapon\_arc\_ball.nut |
| • Values: "ball" | \scripts\vscripts\\_settings.nut |
| 射手飞弹 | mp\_weapon\_rocket\_launcher.nut |

### **投掷物**

| 投掷物名称 | 文件名称 |
| :--- | :--- |
| **Base Grenade** | \_grenade.nut |
| 破片手榴弹 | N/A |
| 电弧手榴弹 | mp\_weapon\_grenade\_emp.nut |
| 飞火星 | mp\_weapon\_thermite\_grenade.nut |
| 重力星 | mp\_weapon\_grenade\_gravity.nut |
| 电子烟雾手榴弹 | mp\_weapon\_grenade\_electric\_smoke.nut |
| 炸药包 | mp\_weapon\_satchel.nut |

### 铁驭技能

| 技能名称 | 文件名称 |
| :--- | :--- |
| 隐形 | mp\_ability\_cloak.nut |
| 脉冲刀 | mp\_weapon\_grenade\_sonar.nut |
| 钩爪 | mp\_ability\_grapple.nut |
| 兴奋剂 | mp\_ability\_heal.nut |
| A盾 | mp\_weapon\_deployable\_cover.nut |
| 相位转移 | mp\_ability\_shifter.nut |
| 幻影 | mp\_ability\_holopilot.nut |

## **泰坦**

### **离子**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 分裂枪 | mp\_titanweapon\_particle\_accelerator.nut |
| 镭射炮 | mp\_titanweapon\_laser\_lite.nut |
| 拌线 | mp\_titanability\_laser\_trip.nut |
| 涡流防护罩 | mp\_titanweapon\_vortex\_shield.nut |
| • Base Scripts | \_vortex.nut |
| 镭射核心 | mp\_titancore\_lasercannon.nut |

### **烈焰**

| 武器名称 | 文件名称 |
| :--- | :--- |
| T-203铝热剂发射器 | mp\_titanweapon\_meteor.nut |
| 火墙 | mp\_titanweapon\_flame\_wall.nut |
| • Segment: CreateThermiteTrail | mp\_titanweapon\_meteor.nut |
| 燃烧陷阱 | mp\_titanability\_slow\_trap.nut |
| 热能护罩 | mp\_titanweapon\_heat\_shield.nut |
| • Base Scripts | \_vortex.nut |
| 火焰核心 | mp\_titancore\_flame\_wave.nut |
| • Scr. Earth: CreateThermiteWallSegment | mp\_titanweapon\_flame\_wall.nut |

### **北极星**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 电浆磁轨炮 | mp\_titanweapon\_sniper.nut |
| • Projectile File | mp\_projectile\_titanweapon\_sniper.nut |
| 集束飞弹 | mp\_titanweapon\_dumbfire\_rockets.nut |
| • Projectile File | mp\_projectile\_cluster\_rocket.nut |
| • Methods: "ClusterR" | \_weapon\_utility.nut |
| 悬浮 | mp\_titanability\_hover.nut |
| 拌索陷阱 | mp\_titanability\_tether\_trap.nut |
| • Tether Projectile | mp\_weapon\_tether.nut |
| 飞行核心 | mp\_titancore\_flight\_core.nut |
| • Core Weapon | mp\_titanweapon\_flightcore\_rockets.nut |

### **浪人**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 天女散花 | mp\_titanweapon\_leadwall.nut |
| 电弧波 | mp\_titanweapon\_arc\_wave.nut |
| 相位冲刺 | mp\_titanability\_phase\_dash.nut |
| 剑封锁 | mp\_titanability\_basic\_block.nut |
| 剑核心 | mp\_titancore\_shift\_core.nut |

### **强力**

| 武器名称 | 文件名称 |
| :--- | :--- |
| 40MM追踪机炮 | mp\_titanweapon\_40mm.nut |
| 追踪火箭 | mp\_titanweapon\_tracker\_rockets.nut |
| 声呐锁定 | mp\_titanability\_sonar\_pulse.nut |
| 粒子屏障 | mp\_titanability\_particle\_wall.nut |
| 火箭核心 | mp\_titanweapon\_salvo\_core.nut |

### **军团**

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x6B66;&#x5668;&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x6587;&#x4EF6;&#x540D;&#x79F0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x730E;&#x6740;&#x8005;&#x673A;&#x70AE;</td>
      <td style="text-align:left">mp_titanweapon_predator_cannon.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5F3A;&#x5927;&#x706B;&#x529B;</td>
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
      <td style="text-align:left">&#x8FD1;/&#x8FDC;&#x7A0B;&#x6A21;&#x5F0F;&#x5207;&#x6362;</td>
      <td style="text-align:left">mp_titanability_ammo_swap.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x67AA;&#x76FE;</td>
      <td style="text-align:left">mp_titanability_gun_shield.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x667A;&#x6167;&#x6838;&#x5FC3;</td>
      <td style="text-align:left">mp_titancore_siege_mode.nut</td>
    </tr>
  </tbody>
</table>

### **帝王**

| 武器名称 | 文件名称 |
| :--- | :--- |
| XO-16 | mp\_titanweapon\_xo16.nut |
| 火箭弹群 | mp\_titanweapon\_salvo\_rockets.nut |
| 多目标飞弹 | mp\_titanweapon\_shoulder\_rockets.nut |
| 武装 | mp\_titanability\_rearm.nut |
| 能量吸收 | mp\_titanweapon\_stun\_laser.nut |
| 升级核心 | mp\_titancore\_upgrade.nut |

## 常用脚本

许多不同武器所使用的方法。

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x65B9;&#x6CD5;&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x6B66;&#x5668;&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x6587;&#x4EF6;&#x540D;&#x79F0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x6CE2;&#x6D6A;&#x811A;&#x672C;: &#x6B66;&#x5668;&#x653B;&#x51FB;&#x6CE2;</td>
      <td
      style="text-align:left">
        <p>&#x7535;&#x5F27;&#x6CE2;</p>
        <p>&#x706B;&#x5899;</p>
        <p>&#x71C3;&#x70E7;&#x9677;&#x9631;</p>
        <p>&#x706B;&#x7130;&#x6838;&#x5FC3;</p>
        </td>
        <td style="text-align:left">_weapon_utility.nut</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x653B;&#x51FB;&#x811A;&#x672C;: &#x6563;&#x5F39;&#x5C04;&#x51FB;</td>
      <td
      style="text-align:left">
        <p>EVA-8&#x81EA;&#x52A8;</p>
        <p>&#x956D;&#x5C04;&#x70AE;
          <br />&#x80FD;&#x91CF;&#x5438;&#x6536;</p>
        <p>&#x8FD1;&#x8DDD;&#x79BB;&#x5F3A;&#x5927;&#x706B;&#x529B;</p>
        <p>&#x6F29;&#x6DA1;&#x9632;&#x62A4;&#x7F69;</p>
        </td>
        <td style="text-align:left">_weapon_utility.nut</td>
    </tr>
  </tbody>
</table>

