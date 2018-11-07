# Ion - Splitter rifle heat effect

## Preparation

In this guide you will have to edit vmt files. I would recommend you to use the software [VTFEdit](https://wanty5883.gitbook.io/titanfall2/information/modding-tools) to edit them. You can use text editor for that such as Atom, NotePad++, VIM and many other ones would work fine.

Navigate to your folder and find this VPK file:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files. [Here](https://wanty5883.gitbook.io/titanfall2/information/modding-tools)

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed. Navigate to your game folder and open this file:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly ?](https://wanty5883.gitbook.io/titanfall2/how-to-start-modding/2.-how-to-backup-extract-and-repack)​

## Editing

To edit the following weapon heat effect you need to find their .vmt files. Further in this guide you will find the different file locations and details about what modifications can be done.

You can edit the heat color, [here](https://wanty5883.gitbook.io/titanfall2/information/color-and-texture-info#usdlayercolor) more information about color and how to edit the way you like.

You can change the heat effect texture to any other texture in the game. Some texture would work, some wouldn't look good and some other texture would just not work. More info [here](https://wanty5883.gitbook.io/titanfall2/information/color-and-texture-info#usdtexture2-and-usdbasetexture) how to edit the texture value.

### Enlable heat effect

For editing Splitter Rifle heat effect, go to this location.

> \materials\models\weapons\titan\_particle\_accelerator

Open the file _`titan_particle_accelerator_heat_charge.vmt`_ and refer to the different info provided.

As additional information given above in this guide, you may know that the Splitter Rifle don't have heat effect by default in the game. However Respawn did created a heat effect for it, but for some reason they did disable this effect. By editing the following instruction you will enable the heat effect.

This are the default value you will have. When you have this `//`, the file interprets all character after as a comment, meaning it won't affect the game. That's usually used as note when you have large file.

```text
//Get the Fraction of ammo left
//"ClipAmmoFraction"
//{
//	"resultVar" "$ClipAmmoFraction"
//}
```

That's the line you need to uncomment. Be sure to not uncomment `//Get the Fraction of ammo left`.

```text
//Get the Fraction of ammo left
"ClipAmmoFraction"
{
	"resultVar" "$ClipAmmoFraction"
}
```

After doing this the heat effect is now enable on the Splitter Rifle.

### Continuous heat effect

On the Splitter Rifle is possible to get continuous heat effect.

I would recommend thoose heat effect texture who look really nice on the Splitter Rifle.

* `particle\energy\energy_burn_loop`
* `particle\blood\blood_anim_spray` Then change the following values, they are my own sample. Do not copy paste this code block in your VMT file, the value in this code block are only the edited values, make sure to replace each one of them into your material file.

```text
"$texture2" "particle\energy\energy_burn_loop"
$allowoverbright 3 //Increase the brightness of the heat effect

$layercolor2 "[2 0 2]" //Pink

"texturescrollrate" "-0.20"
"texturescale"	.50

//invert the fraction
"Multiply" //This value make the heat effect continuous
{
	"srcVar1" "$one"
	"srcVar2" "$ClipAmmoFraction"
	"resultVar" "$alpha"
}
```

### Example

[Here](https://gfycat.com/fr/gifs/detail/sickflashygermanshepherd)

## Repacking <a id="repacking"></a>

​[How to repack VPK files proprely ?](https://github.com/Wanty5883/Titanfall2/wiki/General-Info#how-to-repack-vpk-files-proprely-)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2. You should be able to see your new crosshair!

> Origin Games\Titanfall2\vpk\

