---
description: Guide on changing the lobby music.
---

# Sounds - Lobby music

  

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

> EXTRACTED-VPK\scripts\vscripts\client\cl_music.gnut

and use CTRL+F to search for **void function LoopLobbyMusic()**.

Place this under **string soundAlias**: 
```cpp
 	int musicLenght
	musiclenght = GetConVarInt("sp_deathtips_tip6")
	while(true);
	{
		GetLocalClientPlayer().ClientCommand("lobbymusic")
		wait musicLenght
	}
```
The final product should look like this:

![kuva](https://user-images.githubusercontent.com/36992687/113929087-488fcf80-97f8-11eb-86fa-756d5bc7e9e9.png)

After editing the file save it and move to the next step.

## Creating autoexec.cfg <a id="autoexec"></a>

To easily change your music you need to use a config file. 

start by creating a file named **autoexec.cfg** in:

> Origin Games\Titanfall2\r2\cfg

After creating the file open it with Notepad and paste the following in the file:
```cpp
alias lobbymusic "playvideo lobbymusic1 1 1 1; sp_deathtips_tip6 LENGHT"
```
and replace **LENGHT** with the lenght of your music in seconds.

After saving add **+exec autoexec.cfg** to your launch options for titanfall on Origin.

![kuva](https://user-images.githubusercontent.com/36992687/113929456-c18f2700-97f8-11eb-905d-f6041442c4a8.png)

## Converting music <a id="converting"></a>

To use custom sounds in titanfall 2 we need to use a workaround and play them as video instead.
Use RAD Tools to convert a music video to a .bik video. The music HAS to be as a video for it to work.

Open RAD Tools and navigate to the location of your downloaded video. Select the video and press the **BINK IT!** button. In the menu that opens name the sound to **lobbymusic.bik** and press the **Bink** button on the right side of the window. 

After binking the video move the new **lobbymusic.bik** to

> Origin Games\Titanfall2\r2\media

{% hint style="danger" %}
Remember to change LENGHT in the autoexec to the lenght of your video for proper looping.  
{% endhint %}

## Repacking <a id="repacking"></a>

​[How to repack VPK files properly ?](https://noskill.gitbook.io/titanfall2/how-to-start-modding/how-to-backup-extract-and-repack#how-to-repack-vpk-files-properly)​

After following step by step the previous link

Rename pak000\_000.vpk _to_ **client\_mp\_common.bsp.pak000\_000.vpk**

Rename pak000\_dir.vpk _to_ **englishclient\_mp\_common.bsp.pak000\_dir.vpk**

Place both of the renamed files back into your game directory and then launch Titanfall 2 and open multiplayer. You should be able to hear yout music.

> Origin Games\Titanfall2\vpk\
