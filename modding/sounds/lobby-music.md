---
description: Guide on changing the lobby music.
---

# Lobby music

## Preparation <a id="preparation"></a>

Navigate to your folder and find this folder:

> Origin Games\Titanfall2\vpk\

Copy these file and paste them in an empty folder somewhere else:

* englishclient\_mp\_common.bsp.pak000\_dir.vpk
* client\_mp\_common.bsp.pak000\_000.vpk

You will need the Titanfall VPK Tool, the program which will allow you to open and repack Titanfall VPK files and RAD Tools Bik, which lets you convert videos to the BIK format, both found [here.](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools)​

## Unpacking <a id="unpacking"></a>

Now that these files have been backed up and everything installed, navigate to your game folder and open this file using the VPK tool:

> Origin Games\Titanfall2\vpk\englishclient\_mp\_common.bsp.pak000\_dir.vpk

​[How to extract VPK's properly?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack)​

## Editing

To add custom music open this file using Notepad:

> EXTRACTED-VPK\scripts\vscripts\client\cl\_music.gnut

and use CTRL+F to search for `void function LoopLobbyMusic()`

Place this under `string soundAlias`:

```cpp
    int musicLenght;
    while(true)
    {
        musicLenght = GetConVarInt("sp_deathtips_tip6")
        GetLocalClientPlayer().ClientCommand("lobbymusic")
        wait musicLenght;
    }
```

The final product should look like this:

```cpp
void function LoopLobbyMusic()
{
	string soundAlias
	int musicLenght;
	while(true)
	{
		musicLenght = GetConVarInt("sp_deathtips_tip5")
		GetLocalClientPlayer().ClientCommand("lobbymusic")
		wait musicLenght;
	}	
	
	bool classicMusicAvailable = !IsItemLocked( GetLocalClientPlayer(), "classic_music" )

	if ( GetConVarBool( "sound_classic_music" ) && classicMusicAvailable )
		soundAlias = "music_lobby_ambient_classic"
	else
		soundAlias = "music_lobby_ambient"

	if ( file.currentMusicPlaying == soundAlias )
		return

	clGlobal.levelEnt.Signal( "MusicPlayed" )
	clGlobal.levelEnt.EndSignal( "MusicPlayed" )
	clGlobal.levelEnt.EndSignal( "MusicStopped" )

	entity player = GetLocalClientPlayer()
	OnThreadEnd(
	function() : ( player )
		{
			if ( IsValid( player ) && file.currentMusicPlaying != "" )
				FadeOutSoundOnEntity( player, file.currentMusicPlaying, DEFAULT_FADE_TIME )
		}
	)

	file.currentMusicPlaying = soundAlias

	while ( true )
	{
		wait 2.0 //Hack. Make music restarting in lobbies slightly less bad.

		player = GetLocalClientPlayer()
		if ( !IsValid( player ) )
			return

		var soundHandle = EmitSoundOnEntity( player, soundAlias )

		WaitSignal( soundHandle, "OnSoundFinished" )
	}
}
```

After editing the file save it and move to the next step.

## Creating autoexec.cfg <a id="autoexec"></a>

To easily change your music you need to use a config file.

start by creating a file named **autoexec.cfg** in:

> Origin Games\Titanfall2\r2\cfg

After creating the file open it with Notepad and paste the following in the file:

```cpp
alias lobbymusic "playvideo lobbymusic 1 1 1; sp_deathtips_tip5 LENGHT"
```

and replace `LENGHT` with the lenght of your music in seconds.

After saving add `+exec autoexec.cfg` to your launch options for titanfall on Origin.

![Origin launch options](../../.gitbook/assets/kuva%20%281%29.png)

## Converting music <a id="converting"></a>

To use custom sounds in Titanfall 2 we need to use a workaround and play them as video instead. Use RAD Tools to convert a music video to a .bik video. The music HAS to be as a video for it to work.

Open RAD Tools and navigate to the location of your downloaded video. Select the video and press the **BINK IT!** button. In the menu that opens name the sound to **lobbymusic.bik** and press the **Bink** button on the right side of the window.

After compressing the video using RAD Tools move the new **lobbymusic.bik** to

> Origin Games\Titanfall2\r2\media

{% hint style="danger" %}
Remember to change LENGHT in the autoexec to the lenght of your video for proper looping. 

You can turn down the original lobby music in the ingame settings.
{% endhint %}



## Repacking <a id="repacking"></a>

​[How to repack VPK files properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2 and open multiplayer. You should be able to hear your music.

> Origin Games\Titanfall2\vpk\

