---
description: VPK (Valve Pak) files are uncompressed archives used to package game content.
---

# VPK - Valve Pak file

&#x20;**VPK** (Valve Pak) files are uncompressed archives used to package game content. Valve's post-[GCF](https://developer.valvesoftware.com/wiki/GCF) games store [materials](../textures/valve-material-type-vmt.md), [models](https://developer.valvesoftware.com/wiki/MDL), [particles](https://developer.valvesoftware.com/wiki/Particles), [choreography scenes](https://developer.valvesoftware.com/wiki/VCD) and many other file types in VPK files.\
VPKs are also used to distribute mods via the the `addoninstaller` tool that ships with some games, such as [Left 4 Dead 2](https://developer.valvesoftware.com/wiki/Left\_4\_Dead\_2).

## Creation

VPKs can be created with the [command line](https://developer.valvesoftware.com/wiki/Command\_line) tool `vpk.exe`.

The tool can be located in the bin folders for most Source games, such as the ones below. The tool is not game dependent, however it is suggested that you use the tool that corresponds to the game you are creating the vpk for. The version in one game may not be as up to date as the version in another due to game updates.

|  Game                                                                                                                                                                                                                                                                                             |  Path to VPK.exe                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| [![\<Alien Swarm>](https://developer.valvesoftware.com/w/images/c/c9/AS-16px.png)](https://developer.valvesoftware.com/wiki/Alien\_Swarm)[Alien Swarm](https://developer.valvesoftware.com/wiki/Alien\_Swarm)                                                                                     | C:\Program Files (x86)\Steam\SteamApps\common\Alien Swarm\bin                                          |
| [![\<Team Fortress 2>](https://developer.valvesoftware.com/w/images/8/84/Tf2-16px.png)](https://developer.valvesoftware.com/wiki/Team\_Fortress\_2)[Team Fortress 2](https://developer.valvesoftware.com/wiki/Team\_Fortress\_2)                                                                  | C:\Program Files (x86)\Steam\SteamApps\common\Team Fortress 2\bin                                      |
| [![\<Left 4 Dead>](https://developer.valvesoftware.com/w/images/c/c0/L4D-16px.png)](https://developer.valvesoftware.com/wiki/Left\_4\_Dead)[Left 4 Dead](https://developer.valvesoftware.com/wiki/Left\_4\_Dead)                                                                                  | C:\Program Files (x86)\Steam\SteamApps\common\Left 4 Dead\bin                                          |
| [![\<Counter-Strike: Source>](https://developer.valvesoftware.com/w/images/c/c7/Css.png)](https://developer.valvesoftware.com/wiki/Counter-Strike:\_Source)[Counter-Strike: Source](https://developer.valvesoftware.com/wiki/Counter-Strike:\_Source)                                             | C:\Program Files (x86)\Steam\SteamApps\common\Counter-Strike Source\bin                                |
| [![\<Source>](https://developer.valvesoftware.com/w/images/5/5a/Source\_icon\_16x16.gif)](https://developer.valvesoftware.com/wiki/Source) [Source SDK Base 2013](https://developer.valvesoftware.com/wiki/Source\_SDK\_Base)                                                                     | C:\Program Files (x86)\Steam\SteamApps\common\Source SDK Base 2013\\\<Singleplayer or Multiplayer>\bin |
| [![\<Counter-Strike: Global Offensive>](https://developer.valvesoftware.com/w/images/3/35/Csgo.png)](https://developer.valvesoftware.com/wiki/Counter-Strike:\_Global\_Offensive) [Counter-Strike: Global Offensive](https://developer.valvesoftware.com/wiki/Counter-Strike:\_Global\_Offensive) | C:\Program Files (x86)\Steam\SteamApps\common\Counter-Strike Global Offensive\bin                      |
| [![\[Portal 2\]](https://developer.valvesoftware.com/w/images/7/77/Portal2-16px.png)](https://developer.valvesoftware.com/wiki/Portal\_2) [Portal 2](https://developer.valvesoftware.com/wiki/Portal\_2)                                                                                          | C:\Program Files (x86)\Steam\steamapps\common\Portal 2\bin                                             |

&#x20;For servers installed using [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD), it is located in the server's bin\ directory. On Linux, it is named vpk\_linux32 instead of vpk.exe.

### Linux / Unix

On Linux / Unix clients, the vpk file can be found replacing "`C:\Program Files (x86)\Steam\SteamApps\common`" for "`~/.steam/steam/SteamApps/common/`". However, it is named `vpk_linux32` instead of `vpk.exe`.

\
If you are running on a 64-bit system, this binary will not work by default. You must tell it to use the 32-bit libraries located in the same directory. This can be done by setting the `LD_LIBRARY_PATH` variable.\
The following script, if created in the above listed bin directories, will create a wrapper to properly launch the 32-bit executable; then a link (or desktop shortcut) to `vpk.sh` (if saved as said name) can be created, from there:

```
#!/bin/bash
DIR=$(dirname "${BASH_SOURCE[0]}")
export LD_LIBRARY_PATH=$(cd "$DIR" && pwd)
exec "$DIR/vpk_linux32" "${@}"
```

Alternatively, if you're running 64-bit Linux, you can use this script to execute the `vpk_linux32` binary successfully. Save this script to "`/usr/local/bin/vpk`" and set it as an executable in the file's properties, for ease of use:

```
#!/bin/bash
VPK_LINUX=$(find "${HOME}/.local/share/Steam" -type f -iname "vpk_linux32" -print | head -n 1)
VALVE_LIB_DIR=$(dirname "${VPK_LINUX}")
LD_LIBRARY_PATH="${VALVE_LIB_DIR}:${LD_LIBRARY_PATH}" "${VPK_LINUX}" "${@}"
```

{% hint style="info" %}
**Note:** The "`${@}`" is for drag-and-drop with \*.desktop files and arguments when using the `vpk` command via console.
{% endhint %}

### Windows

On Windows, a shortcut (\*.lnk) linked to the `vpk.exe` file in the `bin` folder can be created instead, making it so that you can drag-and-drop folders onto the shortcut and get a \*.vpk file in return, and vice-versa.A easily-created shortcut named "vpk" can be left in the `custom` folder, making packaging folders into vpk's and vice-versa (while also debugging your custom files) a lot easier instead of having to do it from the command prompt.

## Commands

### Usage

`vpk [options] <command> <command arguments...>vpk [options] <directory>vpk [options] <vpkfile>`

### Example

`vpk -?`Lists all of the help info, list of available arguments, and info about each argument.

### Create VPK/Add Files

#### `vpk <dirname>`

Creates a pack file named \<dirname>.vpk. Must be an existing location. The VPK will appear next to the directory.

{% hint style="info" %}
**Tip:**Drag a folder onto the tool in Explorer to trigger this command.
{% endhint %}

#### `vpk a <vpkfile> <filename1> <filename2> ...`

Add file(s).

#### `a <vpkfile> @<filename>`

Adds the files referenced in a "response file" (not response rules). Note the `@` symbol.

#### `k vpkfile <keyvalues_filename>`

Add files references in a [keyvalues](../programming/keyvalues/) control file.

{% hint style="warning" %}
**Bug:** They will appear inside the VPK with their full path (`C:\etc\`) intact - is there a way to avoid this?
{% endhint %}

#### `vpk <directory>`

Create VPK from directory structure.

{% hint style="info" %}
**Note:**This is invoked when a directory is dragged onto the VPK tool.
{% endhint %}

### Extract Files

#### `vpk x <vpkfile> <filename1> <filename2> ...`

Extract file(s).

#### `vpk <vpkfile>`

Extract all files from VPK.

{% hint style="info" %}
**Note:**This is invoked when a .VPK file is dragged onto the VPK tool.
{% endhint %}

### Display VPK Info

#### `vpk l <vpkfile>`

List contents of VPK.

#### `vpk L <vpkfile>`

List Detailed contents of VPK.

### VPK Integrity/Security

#### `vpk checksig <vpkfile>`

Verify signature of specified VPK file. Requires -k to specify key file to use.

### Misc.

#### `vpk generate_keypair <keybasename>`

Generate public/private key file. Output files will be named \<keybasename>.publickey.vdf and \<keybasename>.privatekey.vdf

{% hint style="info" %}
**Note:**Remember: your private key should be kept private.
{% endhint %}

### Options

{% hint style="info" %}
**Tip:**Please note the case of these options. A capital letter is different than a lowercase letter.
{% endhint %}

#### -v

Verbose output.

#### -M

Produce a multi-chunk VPK.** **

{% hint style="info" %}
**Note:**Required if creating a VPK with key values.
{% endhint %}

* Each chunk is a file limited to around 200MB.
* To reduce patch sizes, chunks are never overwritten. New/modified files are instead written to a brand new chunk every time you run the tool.![](https://developer.valvesoftware.com/w/images/c/cc/Note.png)** **

{% hint style="info" %}
**Note:**Multi-chunk generations only works when creating a VPK from a response file.
{% endhint %}

{% hint style="info" %}
**Tip:**To inspect a multi-chunk VPK open the '\_dir' file.
{% endhint %}

#### `-P`

Use SteamPipe-friendly incremental build algorithm. Use with 'k' command. For optimal incremental build performance, the control file used for the previous build should exist and be named the same as theinput control file, with '.bak' appended, and each file entryshould have an 'md5' value. The 'md5' field need not be theactual MD5 of the file contents, it is just a unique identifierthat will be compared to determine if the file contents has changedbetween builds.

#### `-c <size>`

Use specified chunk size (in MB). Default is 200.

#### `-a`

Align files within chunk on n-byte boundary. Default is 1.

#### `-K`

With commands 'a' or 'k': Sign VPK with specified private key.

#### `-k`

With commands 'a' or 'k': Public key that will be distributed and used by third parties to verify signatures.With command 'checksig': Check signature using specified key file.

## Examples

Listed below are some examples of using the tool and what they will do.

### Making custom vpks for a mod

Content must be a subdirectory under sound/materials/models in the root dir of your VPK, or else they won't appear in hammer. IE your sounds should be located in sound/foo/thisIsASound.wav in your custom vpk, models under models/, materials under materials/, ect.

VPKs must be mounted in gameinfo.txt.

### Creating A Key Value File and VPK

1\. Create a folder with the correct directory structure and files that you wish to use such as `mymod/resource/ui/<file.res>`2. Use the command line in a prompt or a bat:`vpk generate_keypair <name>vpk -M -k <name>.publickey.vdf -K <name>.privatekey.vdf "C:\Program Files (x86)\Steam\SteamApps\common\Team Fortress 2\bin\mymod"`3. In the folder where the vpk tool is located there will now be a public key vdf, a private key vdf, a vpk named mymod\_000 and a vpk named mymod\_dir.

{% hint style="danger" %}
&#x20;**Warning: **Never disclose or share your private key vdf or the key. Only share the public key.
{% endhint %}

* You must distribute your mod with both the mymod\_dir and mymod\_000 vpks for the keyvalue to work.

## Response File

A "response file" contains a list of files to be added to a VPK. Paths are relative to the current directory of the `vpk` tool.

Below is a Python script which generates a response file and then builds a multi-chunk VPK. Put it in your mod folder. You will need to edit the three variables at the top.

```
# User settings (don't use the \ character)
target_folders = [ "materials", "models", "particles", "scenes" ]
file_types = [ "vmt", "vtf", "mdl", "phy", "vtx", "vvd", "pcf", "vcd" ]
vpk_path = "C:/Program Files (x86)/Steam/steamapps/common/SourceFilmmaker/game/bin/vpk.exe"

# Script begins
import os,subprocess
from os.path import join
response_path = join(os.getcwd(),"vpk_list.txt")

out = open(response_path,'w')
len_cd = len(os.getcwd()) + 1

for user_folder in target_folders:
	for root, dirs, files in os.walk(join(os.getcwd(),user_folder)):
		for file in files:
			if len(file_types) and file.rsplit(".")[-1] in file_types:
				out.write(os.path.join(root[len_cd:].replace("/","\\"),file) + "\n")

out.close()

subprocess.call([vpk_path, "-M", "a", "pak01", "@" + response_path])
```

[![\[Portal 2\]](https://developer.valvesoftware.com/w/images/7/77/Portal2-16px.png)](https://developer.valvesoftware.com/wiki/Portal\_2) To handle this process for portal 2 you can also use the [P2 Multichunk Tool](https://developer.valvesoftware.com/wiki/P2\_Multichunk\_Tool), to automate the response file creation and the creation of the vpk files.

#### Excluded files

Executable and archive files are discarded by the VPK tool:

```
.zip .reg .rar .msi .exe .dll .com .cmd .bat
```

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/VPK](https://developer.valvesoftware.com/wiki/VPK)
{% endhint %}

