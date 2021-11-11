# Gameinfo.txt

**`GameInfo.txt`** is a [KeyValues](./) config file that describes a Source mod. Apart from containing metadata like the name of the mod or a link to the developer's website, it also defines which games it depends on and the **SearchPaths** that the engine uses to look up resources. It is stored in the mod's root folder. Source, the SDK tools and Steam rely on it.

{% hint style="info" %}
**Note:**Booleans are represented as 0 or 1.
{% endhint %}

{% hint style="info" %}
**Note:**If a string contains spaces or tabs you have to wrap it in "quote marks".
{% endhint %}

## Basic settings

### Name

Keys that affect the menu and window title.

#### &#x20;Game `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

The name of the mod in ASCII. Displayed in Steam and used as the window title. Only displayed in the main menu if Title isn't specified.

#### &#x20;Title `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

&#x20;A [Unicode](http://en.wikipedia.org/wiki/Unicode) string displayed in the main menu of your mod. You can also new line the menu text by adding another key of the same name `Title`, but append either 2 or a higher number onto it.

{% hint style="info" %}
**Note:** The higher the number, the further down the text will be.
{% endhint %}

#### &#x20;GameLogo `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Half-Life 2: Episode Two / Source 2007)

&#x20;Rather than displaying the `Title` text on the main menu, display the content in `resource\GameLogo.res`. See [Adding Your Logo to the Menu](https://developer.valvesoftware.com/wiki/Adding\_Your\_Logo\_to\_the\_Menu).

### Options&#xD;

&#x20;Keys that affect what tabs and options that show up in the Options panel. Also see [Customizing Options: Keyboard](https://developer.valvesoftware.com/wiki/Customizing\_Options:\_Keyboard).

#### Type `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

Affects which tabs appear in which order in the Options panel, the value will either be `Singleplayer_Only` or `Multiplayer_Only`. Omit this key if your mod has both SP and MP modes.

#### NoDifficulty `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>`

Hides the difficulty tab (this happens automatically if your mod is `Multiplayer_Only`.)

#### HasPortals `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>`&#x20;

(New with Half-Life 2: Episode Two / Source 2007)Shows the Portal options tab.

#### NoCrosshair `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>`

Hides the multiplayer crosshair selection menu.

#### AdvCrosshair `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>`

Enables the special advanced crosshair options. **To do: **How to implement.

#### NoModels `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>`

Hides the multiplayer model selection menu.

#### NoHIModel `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>`

Hides toggle checkbox for `cl_himodels`, which was used in [GoldSource](https://developer.valvesoftware.com/wiki/GoldSource). Only displayed properly if `cl_himodels` exists in the first place.

#### Hidden\_Maps `<`[`subkey`](https://developer.valvesoftware.com/w/index.php?title=Subkey\&action=edit\&redlink=1)`>`

Maps in the subkey do not appear in the "Create a Server" dialogue. Does not stop users from being able to load them from the console though. Syntax is `mapname 1`, with one entry per line. Don't include `.bsp`. Remember to open and close the subkey with { and }.

### Steam games list

Keys that affect how your game or mod shows up in the Steam Library page.

\
Developer `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

The developer of the mod. Usually either the Mod Team's name, or a single person's name.

Developer\_URL `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`Your or the mod's URL. Must start with `http://`.

Manual `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

URL to the mod's manual; can also be a local file.

Icon `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

Local path relative to GameInfo.txt, to an uncompressed 16x16 TGA that will appear as your mod's icon in Steam. Do not include the file extension. The larger 32px pixel icon that appears in Steam's Detail View should be placed next to the 16px one and called `<icon>_big.tga`.

{% hint style="info" %}
&#x20;**Note:**For transparency to work, the TGA must be saved in 32-bit mode with active alpha channel.
{% endhint %}

### Engine and tools

Keys that affect how the engine/tools runs and some options for the tools themselves.

Nodegraph `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Half-Life 2: Episode Two / Source 2007)

Whether or not to enable building [nodegraphs](https://developer.valvesoftware.com/wiki/Nodegraph) (.ain files) for maps.

GameData `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>`

Path to a [FGD](https://developer.valvesoftware.com/wiki/FGD) file, relative to [Hammer](https://developer.valvesoftware.com/wiki/Hammer)'s location. This is needed for [instances](https://developer.valvesoftware.com/wiki/Instances) to be compiled into maps. It is not used by Hammer itself.

InstancePath `<`[`string`](https://developer.valvesoftware.com/wiki/String)`>` (New with Source 2013)

The default location in which to look for [Instance](https://developer.valvesoftware.com/wiki/Instance) VMFs.

SupportsDX8 `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Left 4 Dead)

When false, prevents the game from being ran in older [DirectX Versions](https://developer.valvesoftware.com/wiki/DirectX\_Versions) such as DX8 and below, since they do not support the full range of graphic effects, also prevents [Studiomdl](https://developer.valvesoftware.com/wiki/Studiomdl) from producing `.sw.vtx` and `.dx80.vtx` files for models, as they aren't needed.

SupportsVR `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Source 2013)

Whether or not the game supports being ran in VR mode.

SupportsXBox360 `<`[`boolean`](https://developer.valvesoftware.com/wiki/Boolean)`>` (New with Left 4 Dead)

Whether or not the game supports Xbox 360.

{% hint style="info" %}
&#x20;**Confirm:**Does this enable being able to use a Xbox 360 controller with the game?
{% endhint %}

### FileSystem

Keys that are within the subkey `FileSystem`.

SteamAppID `<`[`integer`](https://developer.valvesoftware.com/wiki/Integer)`>`

The [AppID](https://developer.valvesoftware.com/wiki/Steam\_Application\_IDs) of the game the mod is to be based on. The mod will have access to all of this game's content, and will not be playable unless it is installed, the mod will also be ran with the game's executable as well. If you're uploading your Source game to Steam, this will be your game's AppID. Otherwise, this will be 243750 for Source 2013 Multiplayer, 243730 for Source 2013 Singleplayer, 630 for [Alien Swarm](https://developer.valvesoftware.com/wiki/Alien\_Swarm), or the AppID of the game you're basing it off of if you're not working with source code.

{% hint style="info" %}
&#x20;**Note:**Most older Source mods will use AppID 215 for Source 2006 and 218 for Source 2007. If your making a new mod, you shouldn't use these IDs as they're for a obviously deprecated Source engine branch that was replaced by Source 2013 and Alien Swarm. Only use them for legacy support.
{% endhint %}

{% hint style="info" %}
&#x20;**Note:**Your mod won't be protected by [VAC](https://developer.valvesoftware.com/wiki/VAC) if it is based on a singleplayer game.
{% endhint %}

~~AdditionalContentId `<`~~[~~`integer`~~](https://developer.valvesoftware.com/wiki/Integer)~~`>`~~ [![\<Obsolete>](https://developer.valvesoftware.com/w/images/6/63/Obsolete\_small.png)](https://developer.valvesoftware.com/wiki/Obsolete)

Deprecated. Another AppID that the mod has access to. This feature was added to the SDK source code but somehow never made it to Valve's other games; you will have to build your own binaries to use it. If you need to mount multiple apps using this, [make these changes](https://developer.valvesoftware.com/wiki/Mounting\_multiple\_games).

{% hint style="warning" %}
**Bug:** The engine understands this command, but the SDK tools unfortunately do not. The best solution, currently, is to copy the content of the game to a location on your hard drive and add an absolute `SearchPath` to it. Remember to delete the SearchPath before you release.
{% endhint %}

~~ToolsAppId `<`~~[~~`integer`~~](https://developer.valvesoftware.com/wiki/Integer)~~`>`~~ [![\<Obsolete>](https://developer.valvesoftware.com/w/images/6/63/Obsolete\_small.png)](https://developer.valvesoftware.com/wiki/Obsolete)

Deprecated. This is the AppID of the SDK currently in use.

## SearchPaths

`SearchPaths` is a subkey within `FileSystem`. It contains a key for every search path. When the engine needs a file it traverses the search paths, stopping when the desired file has been found, hence the order of the search paths is important.

{% hint style="info" %}
&#x20;**Note:**A thing to keep in mind, is the order that you put the search paths in is important, if there are 2 files of the same name that are in 2 different search paths, and you list them both, the search path at the top will win, and use that file.
{% endhint %}

### Directories

The directory, which is the value of the key, will either be relative to the `SteamAppID`'s root directory (i.e. where the executable of the game is located), relative to GameInfo.txt or absolute. A example of each one respectively would be this:

```
Game       |All_Source_Engine_Paths|HL2 // Go to the executable directory, and mount a folder called HL2 in it.
Game       |GameInfo_Path|. // Go to the directory of where GameInfo.txt is located, and mount the folder it's in.
Game       "C:\MyFolderOfContent\content" // Mount this absolute directory, useful for mounting content temporarily.
```

{% hint style="info" %}
&#x20;**Note:**In order to mount a [VPK](https://developer.valvesoftware.com/wiki/VPK) file, you need to add the VPK's name at the end of the directory with the `.vpk` extension. If the VPK is a multi-chunck VPK, then put the name of the VPK in without the "\_dir" or "\_###" at the end.
{% endhint %}

The 2 variables above will start the search in a certain directory, `|All_Source_Engine_Paths|` will start the directory within the root folder, and `|GameInfo_Path|` will start it in the folder where GameInfo.txt is located. Both of these variables can be appended with any number of folders. There are also some special commands you can append in addition to the folders and variables, the known ones are:

* `../`\
  Goes back one folder, this will useful for mounting other games' content like [Portal](https://developer.valvesoftware.com/wiki/Portal), since AdditionalContentID is deprecated. If you wanted to mount Portal, and your game is in, say for example `"<SteamFolder>\SteamApps\Common\MyGame\FolderWhereGameInfoIs"`, you would create a search path like this to mount it's content:

```
// Start in the executable directory, then go back one folder so we're in Common, and then go into Portal/portal and mount portal_pak.vpk
Game       |All_Source_Engine_Paths|../Portal/portal/portal_pak.vpk 
```

Here is also an example of how to mount a [SourceMod](https://developer.valvesoftware.com/wiki/Modification):

```
// Start in the executable directory, then go back two folders so we're in SteamApps, and then go into SourceMods and mount the MySourceMod folder.
Game       |All_Source_Engine_Paths|../../SourceMods/MySourceMod
```

* `.`\
  This stops the search in the current directory, this should only be used if you want to directly mount where `|All_Source_Engine_Paths|` or `|GameInfo_Path|` are. An example of both:

```
// Mount both |All_Source_Engine_Paths| and |GameInfo_Path| variables' path.
Game       |All_Source_Engine_Paths|.
Game       |GameInfo_Path|.
```

* `/*`\
  Mount every sub-folder and [VPK](https://developer.valvesoftware.com/wiki/VPK) in the current directory, this command is what makes the custom folder work in most update to date Source games. An example of it's use:

```
// Mount the custom folder's sub-folders and VPKs.
Game       |GameInfo_Path|custom/*
```

### Keys

In most older Source games, the only keys for search pathing is `Game` and `Platform`, while these keys will suit most search pathing, in Source 2013 a few new keys where introduced that add more control.

{% hint style="info" %}
&#x20;**Tip:**[Insurgency](https://developer.valvesoftware.com/wiki/Insurgency) and [Day of Infamy](https://developer.valvesoftware.com/wiki/Day\_of\_Infamy) use the same search pathing system as Source 2013, so commands and keys that work in Source 2013 will work for them as well!
{% endhint %}

The current keys known so far are:

* `Game`\
  Adds the path as a simple search path. Will add any content it finds.
* `Game_Write` (New with Source 2013)\
  Marks the search path as a Game write path. This is usually where the game executable is. It marks the directory as the default directory for writing (configuration files, etc) for this game.
* `GameBin` (New with Source 2013)\
  A special key that requires that the path lead to a game's binary files (where `Server.dll` and `Client.dll` are located), and will use any other DLL files it finds. This should lead to your own mod's `Bin` folder, or the game you're basing it off's `Bin` folder if you're not building your own DLLs.
* `Platform`\
  Adds a special search path to the folder containing core engine files, this will usually lead to the game's `Platform` folder.
* `Mod` (New with Source 2013)\
  Marks the search path as a Mod path. This is usually where the game executable is. **To do: **What does this do exactly?
* `Mod_Write` (New with Source 2013)\
  Marks the search path as a Mod write path. This is usually where GameInfo.txt is. It marks the directory as the default directory for writing (configuration files, etc) for this mod.
* `Default_Write_Path`\
  A fallback for when either Mod\_Write or Game\_Write isn't specified. This is usually where GameInfo.txt is. **To do: **What does this "Write" exactly?
* `VPK` (New with Contagion)\
  Used to mount a [VPK](https://developer.valvesoftware.com/wiki/VPK) by name. Do not put `.vpk` at the end.

In Source 2013, you may also append keys to each other by separating each key name by a `+` sign, this way if you need to use one directory for multiple keys, instead of writing this:

```
Game      |GameInfo_Path|MyFolder
Mod       |GameInfo_Path|MyFolder
```

It can instead be shortened like this:

```
Game+Mod  |GameInfo_Path|MyFolder
```

This saves you time from having to retype the directory over again.

### Automatic localization

Source automatically creates localized search paths. If you mount the folder `HL2`, then when your mod runs in French `HL2_French` is automatically mounted just above it, overriding any content in `HL2`. **To do: **Does this also apply for the mod folder?

## Example

A full working GameInfo.txt ready for a Source 2013 Singleplayer mod.

```
GameInfo
{
	Game			"My Mod Name"
	GameLogo		0
	Nodegraph		1
	Title			"My Mod Title"
	Developer 		"My Name"
	Developer_URL 	"https://developer.valvesoftware.com/wiki/Main_Page"
	Type			Singleplayer_Only
	SupportsDX8 	0
	SupportsVR		0
	SupportsXbox360	0
	GameData		HalfLife2.fgd
	FileSystem
	{
		SteamAppId	243730
		SearchPaths
		{
			GameBin		|All_Source_Engine_Paths|SourceTest/Bin // Using the SourceTest DLLs.
			
			// Source 2013 Singleplayer comes with Episode 2, Episode 1, and Lost Coast content. So let's mount it.
			Game		|All_Source_Engine_Paths|EP2/EP2_Pak.vpk // EP2 content has the highiest priority.
			Game		|All_Source_Engine_Paths|Episodic/EP1_Pak.vpk
			Game		|All_Source_Engine_Paths|SourceTest/SourceTest_Pak.vpk // Lost Coast
			
			// Source 2013 Multiplayer comes with HL2 Deathmatch, and Lost Coast content, so let's mount the HL2 Deathmatch content too.
			Game		"|All_Source_Engine_Paths|../Source SDK Base 2013 Multiplayer/HL2MP/HL2MP_Pak.vpk" // Has to be in quotes because of spaces.
			
			Game		|All_Source_Engine_Paths|HL2/HL2_Misc.vpk
			Game		|All_Source_Engine_Paths|HL2/HL2_Sound_Misc.vpk
			Game		|All_Source_Engine_Paths|HL2/HL2_Sound_VO_English.vpk // Optional, just dialog.
			Game		|All_Source_Engine_Paths|HL2/HL2_Textures.vpk
			
			Game+Game_Write+Mod+Mod_Write+Default_Write_Path	|GameInfo_Path|.
			
			// These search for loose files in the folders, incase we missed anything.
			Game		|All_Source_Engine_Paths|EP2
			Game		|All_Source_Engine_Paths|Episodic
			Game		|All_Source_Engine_Paths|SourceTest
			Game		|All_Source_Engine_Paths|HL2

			Platform	|All_Source_Engine_Paths|Platform
			Platform	|All_Source_Engine_Paths|Platform/Platform_Misc.vpk
		}
	}
}
```

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Gameinfo.txt](https://developer.valvesoftware.com/wiki/Gameinfo.txt)
{% endhint %}









