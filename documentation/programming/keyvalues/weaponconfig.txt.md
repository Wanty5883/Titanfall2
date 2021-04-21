---
description: >-
  KeyValues files dedicated to weapon configuration. Otherwise referred as
  weapon config for simplicity.
---

# WeaponConfig.txt

## Introduction

The so called weapon config files are in a text file format, so it can easily be read and edited. The format of the content is known as [Source **KeyValues**](./).

Beside being a general source of information, this page will be used as a reference point of documentation for the different aspects and uses of the weapon config files. Either by modding guides or other documentation pages.

## Variables \(key\) index

Down bellow is embedded a table used as an index. All \(known\) variables are splitted in different tabs \(Models, Effects, Sounds, etc.\) with categories per tabs.  
Each tabs will have it's own header so it can easily be browsed in the contents table. The different categories will also have their sub headers.

{% embed url="https://docs.google.com/spreadsheets/d/1wzCDQn8xuszQHWP2Uf5Ip9lu32YLurqF5X3fBYB62K8" %}

## Models & Animation

## Effects \(FX\)

Effects, which will be mentioned as FX. Is one of the end application of the Particle System in Source Engine. For a basic approach, FX are a conjunction of textures \(2D graphic elements\) and different kind of parameters to create the illusion of 3D visual effects. Such as explosions, clouds, trails, etc.

{% hint style="info" %}
At this time, there isn't an in depth reference page for the Particle System and their pcf files. The page will be included here and hyperkinked on keywords. If you would like to help, please contact us.
{% endhint %}

A different sub header will be made for the different category of variables used in the purpose of FX. The complete list of variables can be viewed from the [index table](weaponconfig.txt.md#variables-key-index) in the **Effect \(FX\)** tab.

By the very nature of config files, the usage of FX can be restrictive. As they are easier to edit \(the config files\) but at the cost of possibilities. With that said, for anything that cannot be done from the config file, vscript files open more possibilities.

While looking at pre-existing files, the FX variables will often be around the comment:

```text
// Effects
```

In KeyValues format, a comment is defined by a double forward slash, everything after will not be interpreted by the engine \(Source Engine\). This method is very useful to leave annotations, default values, etc. Thus making your file easier to read and / or easier to modify over time.

Note that the variables does not need to be after effect the comment.  
You can learn more about the KeyValues format here

{% page-ref page="./" %}

### Bullet - Hitscan

The FX for hitscan bullets are known as tracer effects. They will behave as intended for hitscan based wepaons but will not work properly on projectile based weapons.

The tracers FX will change the esthetics of your bullets. Either for the bullet itself or the trail it does leave behind \(the bullet itself being the leading graphical element as it move in one direction\)  
Combination are of course possible, but not from the weapon config file. _\(refer to the mentions under the main FX header\)_  
Different "kind" of bullets can be achived \(energy, electric, fire, high velocity, etc.\)

* **tracer\_effect** will set an FX to the given weapon from other entities \(players & NPC's\)
* **tracer\_effect\_first\_person** will set an FX only from your uses of the weapon

While modding with large quantities of FX, it is recommended to primarily focus on first person variables, thus having a lower impact on performance and being less confusing.

```text
"tracer_effect_first_person"    <FX Value>
"tracer_effect"   							<FX Value>
```

```text
"tracer_effect_first_person"    "P_wpn_tracer"
"tracer_effect"   							"P_wpn_tracer"
```

**The expected value &lt;FX Value&gt; is the name of an effect from the Particle System as a string.** Those names are set from pcf files \(particle files\)

{% embed url="https://gfycat.com/anchoredfabulousaustraliankelpie" caption="An example of tracer FX" %}

## UI & Menu

### Icons

The icons can be changed using those variables \(`menu_icon`, `hud_icon`\). **The expected value is a path to** [**material** ](../../textures/valve-material-type-vmt.md)**as a string.**

If your desired weapon already has an icon RUI location allocated on your screen then it becomes fairly easy to modify. This will be the case most of the time.

{% hint style="info" %}
Custom icons, using icons that aren't shipped with the game files is possible. A modding guide on this topic might be added in the future. If so, it will also be linked in this section of the page.
{% endhint %}

However if you would like to add an icon that does not have an RUI location allocated \(basically a new location on your screen\) you will have to code it.

{% hint style="info" %}
This topic is not yet covered in the wiki. This might be added in the future. If you would like to contribute, please contact us.
{% endhint %}

Down bellow here is how the variables are used in your weapon config file:

* **menu\_icon** will set the icon in the menu, when selecting your loadouts for example.
* **hud\_icon** will set the icon in your hud, while you are in a match

```text
	"menu_icon"		<Icon Path>
	"hud_icon"		<Icon Path>
```

```text
	"menu_icon"		"r2_ui/menus/loadout_icons/primary_weapon/primary_r102"
	"hud_icon"		"r2_ui/menus/loadout_icons/primary_weapon/primary_r102"
```

In the table down bellow you will find an index with previews \(partially\) of the different icons. This list is not complete, there is a lot of unused icons left in the game files.

{% embed url="https://docs.google.com/spreadsheets/d/1QM3bJSek\_\_ttMRjxTx1IjkV4OVq3mdeaAdDVOUVAtqg" caption="Icons index" %}





