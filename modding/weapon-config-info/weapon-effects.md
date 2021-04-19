---
description: 修改武器的视觉效果
---

# 武器特效

## 前期准备 <a id="preparation"></a>

进入以下目录并找到所需的VPK文件:

> Origin Games\Titanfall2\vpk\

复制粘贴下面的文件到其他空的文件夹之中:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)​

## 解包 <a id="unpacking"></a>

现在，这些文件已经备份完毕并且所有东西都已准备就绪。在软件中进入游戏目录并打开这个文件：

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[如何正确地解包VPK文件？](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack)

### 特效

> englishclient\_mp\_common.bsp.pak000\_dir.vpk\scripts\weapons

这个文件夹包含所有武器的"配置文件"，修改文件所产生的风险由你自己承担。如果因为你修改核心数值而导致的账号封禁，别把责任归咎于我。

本指南将会介绍这些文件中注释 `// Effects`对应的数值， 它包含很多的内容和各种不同的数值。为了更快找到你所需要的东西，请参阅**目录**。这是我们要在文件中查找的一部分内容：

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

正如你所见到的，部分武器的效果在穿过A盾后会发生变化。 这是你应该查找的部分，例如：

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

#### impact\_effect\_table

这个值用于定义子弹击中玩家或墙壁时的碰撞动画，它可以被添加到那些没有这个数值的武器上。根据以前的测试结果，无法同时组合多个碰撞动画。  
Impact\_effect\_table接受其他类型的数值，例如tracers。

在每个武器配置文件的正常模式和右键瞄准模式之间可以有不同的值。在游戏数值的FX中查找有影响的值：

{% page-ref page="../../game-values/fx/" %}

#### tracer\_effect

子弹弹道追踪效果**仅适用于直线弹道武器**，此功能不会影响到抛物线弹道武器射弹武器。不过，也有一些例外。查找以下代码块来定位跟踪效果的代码部分：

```text
"tracer_effect"   							  "P_wpn_tracer"
"tracer_effect_first_person"                    "P_wpn_tracer"
```

`tracer_effect` 将会影响到**整个游戏**。换句话来说，它会改变其他玩家使用被修改武器时的示踪粒子效果 \(修改效果只有你可见\)。`tracer_effect_first_person`则只会影响到你自己。你可以为这两个数据设置不同的数值。从以前的测试结果来看，如果在太多不同的武器上有太多的`tracer_effect` 可能会导致整个战场非常混乱，甚至会降低游戏性能。就我个人而言，我很少修改它；即便修改了，大多数时候我也只修改 `tracer_effect_first_person` 。

{% page-ref page="../../game-values/fx/" %}

#### projectile\_trail\_effect

抛物线轨迹效果**仅适用于抛物线弹道武器**，此功能不影响直线弹道武器。查找以下代码块来定位轨迹效果的代码部分：

```text
"projectile_trail_effect_0" 					"P_projectile_lstar"
```

在每个武器配置文件的正常模式和右键瞄准模式之间可以有不同的值。在游戏数值的FX中查找有影响的值：

{% page-ref page="../../game-values/fx/" %}



