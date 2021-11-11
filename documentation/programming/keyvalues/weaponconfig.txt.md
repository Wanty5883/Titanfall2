---
description: >-
  KeyValues files dedicated to weapon configuration. Otherwise referred as
  weapon config for simplicity.
---

# WeaponConfig.txt

## Introduction

The so called weapon config files are in a text file format, so they can easily be read and edited. The format of the content is known as [Source **KeyValues**](./).

Beside being a general source of information, this page will be used as a reference point of documentation for the different aspects and uses of the weapon config files. Either by modding guides or other documentation pages.

### File location

Weapon config files can be found in this folder relative to your VPK.

```
<VPK archive>\scripts\weapons
```

The VPK of your choice will depend of the context of your modding. If it is for multiplayer or for single player. For multiplayer purpose it will be the "Common" VPK and for other than multiplayer you will need to modify each VPK archives for their respective levels.

## Index - Variables (keys)&#x20;

Down below is embedded a table used as an index. All (known) variables are split in different tabs (Models, Effects, Sounds, etc.) with categories per tab.\
Each tab will have its own header so it can easily be browsed in the contents table. The different categories will also have their own sub headers.

{% embed url="https://docs.google.com/spreadsheets/d/1wzCDQn8xuszQHWP2Uf5Ip9lu32YLurqF5X3fBYB62K8" %}

## Models & Animation

## Effects (FX)

Effects, which will be mentioned as FX, is one of the end applications of the Particle System in Source Engine. For a basic approach, FX are a conjunction of textures (2D graphic elements) and different kind of parameter to create the illusion of 3D visual effects, such as explosions, clouds, trails, etc.

{% hint style="info" %}
At this time, there isn't an in depth reference page for the Particle System and their pcf files. The page will be included here and hyperlinked on keywords. If you would like to help, please contact us.
{% endhint %}

A different sub header will be made for the different category of variables used in the purpose of FX. The complete list of variables can be viewed from the [index table](weaponconfig.txt.md#variables-key-index) in the **Effect (FX)** tab.

By the very nature of config files, the usage of FX can be restrictive, as they are easier to edit (the config files) but at the cost of possibilities. With that said, for anything that cannot be done from the config file, vscript files open more possibilities.

While looking at pre-existing files, the FX variables will often be around the comment:

```
// Effects
```

In KeyValues format, a comment is defined by a double forward slash, everything after will not be interpreted by the engine (Source Engine). This method is very useful to leave annotations, default values, etc. Thus making your file easier to read and / or easier to modify over time.

Note that the variables do not need to be after the `// Effect` comment.\
You can learn more about the KeyValues format here

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

{% hint style="warning" %}
&#x20;Weapons can have different FX when they are amped. To modify this aspect, your FX variables will need to be included inside the `Mods` braces. Most of the time this part is already implemented, at the bottom of the weapon config file.
{% endhint %}

The following code block is what you should look for in the weapon config file. While it won't be exactly the same, it should look similar. **It should include `is_burn_mod` in the braces**

```
{
	"is_burn_mod"		              "1"

	//FX
	"tracer_effect"   				   	"P_wpn_tracer_BC"
	"tracer_effect_first_person"  "P_wpn_tracer_BC"
	"fx_muzzle_flash_view"			  "wpn_muzzleflash_smg_elec_FP"
	"fx_muzzle_flash_world"		  	"wpn_muzzleflash_smg_elec"
}
```

FX values are indexed, which you can refer to while reading the sub-headers.

{% content-ref url="../../../game-values/effect-fx.md" %}
[effect-fx.md](../../../game-values/effect-fx.md)
{% endcontent-ref %}

#### \<FX Value>

**The expected value \<FX Value> is the name of an effect from the Particle System as a string.** Those names are set from pcf files (particle files)

The FX can be found in the reference index in the page down bellow.

{% content-ref url="../../../game-values/effect-fx.md" %}
[effect-fx.md](../../../game-values/effect-fx.md)
{% endcontent-ref %}

#### \<Attachment>

Even if the effect of this variable are not known with certainties. Here is a the list of the known values that can be used.

```
FX_GLOW
center
exhaust
fx_center
fx_top
muzzle_flash
muzzle_flash_scoped
muzzle_flash_suppressor_sq
muzzle_flash_l
shell
shell_l
shell_scoped
MissileAirBurst
```

#### \<Boolean int> / \<Boolean str>

The **Boolean **data type is a [data type](https://en.wikipedia.org/wiki/Data\_type) that has one of two possible values (usually denoted true and false) which is intended to represent the two [truth values](https://en.wikipedia.org/wiki/Truth\_value) of [logic](https://en.wikipedia.org/wiki/Logic) and [Boolean algebra](https://en.wikipedia.org/wiki/Boolean\_algebra).&#x20;

A boolean as an integer (int) will differ from a boolean as a string (str), they are used depending on the syntax of the language. Its use varies in different areas of the engine but for the most part, in weapon config files boolean values are used in a form of intergers. Howhever there are some exeptions, those will be differenciated by either `<Boolean int>` or `<Boolean str>`.

{% tabs %}
{% tab title="Boolean int" %}
```
0
1
```
{% endtab %}

{% tab title="Boolean str" %}
```
false
true
```
{% endtab %}
{% endtabs %}

###

### Bullet - Hitscan

The FX for hitscan bullets are known as tracer effects. They will behave as intended for hitscan based weapons but will not work properly on projectile based weapons.

{% embed url="https://gfycat.com/anchoredfabulousaustraliankelpie" %}
An example of tracer FX
{% endembed %}

The tracers FX will change the aesthetics of your bullets, either for the bullet itself or the trail it leaves behind (the bullet itself being the leading graphical element as it moves in one direction)\
Combination are of course possible, but not from the weapon config file. _(refer to the mentions under the main _[_FX header_](weaponconfig.txt.md#effects-fx)_)_\
__Different "kinds" of bullets can be achieved (energy, electric, fire, high velocity, etc.)

* **tracer\_effect **will set an FX to the given weapon from other entities (players & NPC's)
* **tracer\_effect\_first\_person** will set an FX only from your uses of the weapon

While modding with large quantities of FX, it is recommended to primarily focus on first person variables, thus having a lower impact on performance and being less confusing.

{% tabs %}
{% tab title="Format" %}
```
"tracer_effect_first_person"    <FX Value>
"tracer_effect"   							<FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"tracer_effect_first_person"    "P_wpn_tracer"
"tracer_effect"   							"P_wpn_tracer"
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Tracer variables are known to not work very well with FX that are used for projectiles originally. However this is not a golden rule. Trying different kind of FX values can lead to very interesting results. Feel free to play around with them.
{% endhint %}

### Bullet - Projectile

The FX for projectile bullets are known as projectile trail effects. They will behave as intended for projectile based weapons but will not work properly on hitscan based weapons.

{% embed url="https://gfycat.com/poshoilyadder-titanfall-2" %}
An example of projectile FX
{% endembed %}

The projectile trail FX will change the aesthetics of your projectiles, either for the projectile itself or the trail it leaves behind (the projectile itself being the leading graphical element as it moves in one direction).\
Combination are of course possible, but not from the weapon config file. _(refer to the mentions under the main _[_FX header_](weaponconfig.txt.md#effects-fx)_)_\
__Different "kinds" of bullets can be achieved (energy, electric, fire, high velocity, etc.)

* **projectile\_trail\_effect\_0 **will set an FX to the given weapon from other entities (players & NPC's)
* **projectile\_trail\_attachment** the effect of this variable are unknown for now.

{% hint style="info" %}
Note that some weapons can have the use of. Very few of them can use it, if you don't find them already in the weapon config file, it will likely have no effect

* **projectile\_trail\_effect\_1**
* **projectile\_trail\_effect\_2**
{% endhint %}

{% tabs %}
{% tab title="Format" %}
```
"projectile_trail_effect_0"      <FX Value>
"projectile_trail_effect_1"      <FX Value>
"projectile_trail_effect_2"      <FX Value>
"projectile_trail_attachment"    <Attachment>
```
{% endtab %}

{% tab title="Example" %}
```
"projectile_trail_effect_0"      "weapon_kraber_projectile"
"projectile_trail_effect_1"      "P_titan_sniper1"
"projectile_trail_effect_2"      "P_titan_sniper2"
"projectile_trail_attachment"    "FX_GLOW"
```
{% endtab %}
{% endtabs %}

### Bullet - Laser

The FX for lasers are known as sustained laser effects. With the weapon config file, this category is used only for Ion's laser core. It is unlikely to get those variables to work on other weapons, to achieve similar / equivalent effects on other weapons this will have to be done from weapon script files.

{% embed url="https://gfycat.com/nastyveneratedfieldmouse" %}

{% hint style="danger" %}
^ REFERENCE GIF REQUIRED HERE ^\
_using this one waiting for a better one to be made_
{% endhint %}

The sustained laser FX will change the aesthetics of your laser, either for the laser itself or the impact itself.\
Combination are of course possible, but not from the weapon config file. _(refer to the mentions under the main _[_FX header_](weaponconfig.txt.md#effects-fx)_)_

* **sustained\_laser\_effect\_1p **will set an FX only from your uses of the weapon
* **sustained\_laser\_effect\_3p **will set an FX to the given weapon from other entities (players & NPC's)
* **sustained\_laser\_attachment **the effect of this variable are unknown for now.
* **sustained\_laser\_effect\_loops **the effect of this variable are unknown for now.
* **sustained\_laser\_impact\_effect **will set an FX for the laser impact.

{% tabs %}
{% tab title="Format" %}
```
"sustained_laser_attachment"        <ATTACHMENT>
"sustained_laser_effect_1p"         <FX Value>
"sustained_laser_effect_3p"         <FX Value>
"sustained_laser_effect_loops"      <Boolean str>  
"sustained_laser_impact_effect"     <FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"sustained_laser_attachment"        "muzzle_flash"
"sustained_laser_effect_1p"					"P_wpn_lasercannon_FP"
"sustained_laser_effect_3p"					"P_wpn_lasercannon"
"sustained_laser_effect_loops"      "false"  
"sustained_laser_impact_effect"     "P_lasercannon_endglow"
```
{% endtab %}
{% endtabs %}

### Bullet - Impact

Those variables defines the impact animation when the bullet, laser, projectile, etc. hit a surface or an entity (player, titans, NPC's, etc.)

{% embed url="https://gfycat.com/insistentsmallhusky" %}

The variables can be added to weapons that do not have it originally. It should be noted that impact FX cannot be combined (using more than one) from the weapon config file. However this is possible with weapon script files. Reference pages will be linked from the main [FX header](weaponconfig.txt.md#effects-fx).

You also can have different values between normal and amped modes on each weapon config files.

{% tabs %}
{% tab title="Format" %}
```
"impact_effect_table" 							<FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"impact_effect_table" 							"exp_defender"
```
{% endtab %}
{% endtabs %}



### Charge

{% tabs %}
{% tab title="Format" %}
```
"charge_effect_1p"                    <FX Value>
"charge_effect_3p"                    <FX Value>
"charge_effect_attachment"            <Attachment>
"charge_effect_show_during_drain"     <Boolean int>
"charge_effect2_1p"                   <FX Value>
"charge_effect2_3p"                   <FX Value>
"charge_effect2_attachment"           <Attachment>
```
{% endtab %}

{% tab title="Example" %}
```
"charge_effect_1p"                    "P_wpn_defender_charge_FP"
"charge_effect_3p"                    "P_wpn_defender_charge"
"charge_effect_attachment"            "muzzle_flash"
"charge_effect_show_during_drain"     "0"
"charge_effect2_1p"                   "P_wpn_lasercannon_FP"
"charge_effect2_3p"                   "defender_charge_CH_dlight"
"charge_effect2_attachment"           "muzzle_flash"
```
{% endtab %}
{% endtabs %}

### Ignition

{% tabs %}
{% tab title="Plain Text" %}
```
"ignition_effect"                     <Attachment>
"pre_ignition_impact_effect_table"    <FX Value>
"pre_ignition_trail_effect"           <FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"ignition_effect"                     "MissileAirBurst"
"pre_ignition_impact_effect_table"    "exp_smr"
"pre_ignition_trail_effect"           "Rocket_Smoke_SMR"
```
{% endtab %}
{% endtabs %}

### Muzzle Flash

{% embed url="https://gfycat.com/piercingbountifullemming" %}

{% tabs %}
{% tab title="Format" %}
```
"fx_muzzle_flash_attach"            <Attachment>
"fx_muzzle_flash_attach_scoped"     <Attachment>
"fx_muzzle_flash_view"              <FX Value>
"fx_muzzle_flash_world"             <FX Value>
"fx_muzzle_flash2_attach"           <Attachment>
"fx_muzzle_flash2_view"             <FX Value>
"fx_muzzle_flash2_world"            <FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"fx_muzzle_flash_attach"            "muzzle_flash_suppressor_sq"
"fx_muzzle_flash_attach_scoped"     "muzzle_flash_scoped"
"fx_muzzle_flash_view"              "wpn_muzzleflash_smg_elec_FP"
"fx_muzzle_flash_world"             "wpn_muzzleflash_smg_elec"
"fx_muzzle_flash2_attach"           "muzzle_flash_l"
"fx_muzzle_flash2_view"             "wpn_mflash_xo_rocket_shoulder_FP"
"fx_muzzle_flash2_world"            "P_muzzleflash_predator"
```
{% endtab %}
{% endtabs %}

### Shell

{% tabs %}
{% tab title="Format" %}
```
"fx_shell_eject_attach"            <Attachment>
"fx_shell_eject_attach_scoped"     <Attachment>
"fx_shell_eject_view"              <FX Value>
"fx_shell_eject_world"             <FX Value>
"fx_shell_eject2_attach"           <Attachment>
"fx_shell_eject2_view"             <FX Value>
"fx_shell_eject2_world"            <FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"fx_shell_eject_attach"            "shell"
"fx_shell_eject_attach_scoped"     "shell_scoped"
"fx_shell_eject_view"              "wpn_shelleject_rifle_large_FP"
"fx_shell_eject_world"             "wpn_shelleject_rifle_large"
"fx_shell_eject2_attach"           "shell_l"
"fx_shell_eject2_view"             "wpn_shelleject_rifle_assault_FP"
"fx_shell_eject2_world"            "wpn_shelleject_rifle_assault"
```
{% endtab %}
{% endtabs %}

### Vortex Shield

{% tabs %}
{% tab title="Format" %}
```
"vortex_absorb_effect"                <FX Value>
"vortex_absorb_effect_third_person"   <FX Value>
"vortex_impact_effect"                <FX Value>
```
{% endtab %}

{% tab title="Example" %}
```
"vortex_absorb_effect"                "wpn_vortex_projectile_SuperSpec_FP"
"vortex_absorb_effect_third_person"   "wpn_vortex_projectile_SuperSpec"
"vortex_impact_effect"                "P_impact_xo_shield_cp"
```
{% endtab %}
{% endtabs %}

###

## UI & Menu

UI elements (basically graphical elements) are indexed in this page

{% content-ref url="../../../game-values/ui-and-hud/" %}
[ui-and-hud](../../../game-values/ui-and-hud/)
{% endcontent-ref %}

#### \<Icon>

Variables used to change the icon. **The expected value is a path to **[**material **](../../textures/valve-material-type-vmt.md)**as a string.**

If your desired weapon already has an icon RUI location allocated on your screen then it becomes fairly easy to modify. This will be the case most of the time.

{% hint style="info" %}
Custom icons, using icons that aren't shipped with the game files is possible. A modding guide on this topic might be added in the future. If so, it will also be linked in this section of the page.
{% endhint %}

However if you would like to add an icon that does not have an RUI location allocated (basically a new location on your screen) you will have to code it.

{% hint style="info" %}
This topic is not yet covered in the wiki. This might be added in the future. If you would like to contribute, please contact us.
{% endhint %}

In the table down bellow you will find an index with previews (partially) of the different icons. This list is not complete, there is a lot of unused icons left in the game files.

{% embed url="https://docs.google.com/spreadsheets/d/1QM3bJSek__ttMRjxTx1IjkV4OVq3mdeaAdDVOUVAtqg" %}
Icons index
{% endembed %}

### Crosshairs

{% hint style="danger" %}
TODO
{% endhint %}

### HUD

{% tabs %}
{% tab title="Format" %}
```
"enable_hud_alert"                        <Boolean int>
"grenade_arc_impact_indicator_effect"     TODO
"grenade_arc_indicator_bounce_count"      <Int>
"grenade_arc_indicator_effect"            TODO
"grenade_arc_indicator_effect_first"      TODO
"grenade_arc_indicator_show_from_hip"     <Boolean int>
"grenade_indicator_icon_enemy"            TODO
"grenade_indicator_icon_friendly"         TODO
"grenade_show_indicator_to_owner"         <Boolean int>
"hud_grapple_indicator"                   <Boolean int>
"hud_icon"                                <Icon>
"smart_ammo_hud_lock_style"               TODO
"smart_ammo_hud_type"                     TODO
```
{% endtab %}

{% tab title="Example" %}
```
"enable_hud_alert"                        "0"
"grenade_arc_impact_indicator_effect"     "grenade_arc_impact_proto_orange"
"grenade_arc_indicator_bounce_count"      "2"
"grenade_arc_indicator_effect"            "P_grenade_arc_proto"
"grenade_arc_indicator_effect_first"      "P_grenade_arc_proto_first"
"grenade_arc_indicator_show_from_hip"     "0"
"grenade_indicator_icon_enemy"            "P_wpn_grenade_frag_blue_icon"
"grenade_indicator_icon_friendly"         "P_wpn_grenade_frag_blue_icon"
"grenade_show_indicator_to_owner"         "0"
"hud_grapple_indicator"                   "1"
"hud_icon"                                "rui/pilot_loadout/ordnance/gravity_grenade"
"smart_ammo_hud_lock_style"               "pilot_launcher"
"smart_ammo_hud_type"                     "predator_cannon"
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
TODO
{% endhint %}

### Menu

{% tabs %}
{% tab title="Format" %}
```
"menu_anim_class"    <Anim Class>
"menu_category"      <Category>
"menu_icon"          <Icon>
"stat_accuracy"      <Int>
"stat_damage"        <Int>
"stat_range"         <Int>
"stat_rof"           <Int>
```
{% endtab %}

{% tab title="Example" %}
```
"menu_anim_class"    "custom"
"menu_category"      "special"
"menu_icon"          "r2_ui/menus/loadout_icons/primary_weapon/primary_r102"
"stat_accuracy"      "100"
"stat_damage"        "68"
"stat_range"         "80"
"stat_rof"           "12"
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
TODO
{% endhint %}

### Text

{% hint style="danger" %}
TODO
{% endhint %}

## References & Sources

{% hint style="info" %}
* [https://developer.valvesoftware.com/wiki/Particle\_System\_Overview](https://developer.valvesoftware.com/wiki/Particle\_System\_Overview)
* [https://developer.valvesoftware.com/wiki/Particles\_In\_Code](https://developer.valvesoftware.com/wiki/Particles\_In\_Code)
* [https://steamcommunity.com/sharedfiles/filedetails/?id=530493383](https://steamcommunity.com/sharedfiles/filedetails/?id=530493383)
* [https://en.wikipedia.org/wiki/Boolean\_data\_type](https://en.wikipedia.org/wiki/Boolean\_data\_type)
* [https://developer.valvesoftware.com/wiki/Boolean](https://developer.valvesoftware.com/wiki/Boolean)
{% endhint %}

