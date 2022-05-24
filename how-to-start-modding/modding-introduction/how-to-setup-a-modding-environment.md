# How to setup a modding environment

In order to perform some modding methods, it is important to have a good modding environment.

If you are new to modding, it is recommended to get started with the basic method, and as you get more used to modding, the advanced approach might suits you better. But do not worry, the advanced approach is a more in-depth method of the basic one, so no need to start everything from scratch !

## Basic

In the first place, a main folder for modding is necessary.\
Creating a Titanfall 2 folder inside a Modding folder is a preferred method. The location of this root folder will depend of your personal preference.

{% hint style="info" %}
If you are using different storage devices, for better performance, the root folder can be in your faster SSD.\
If you are using a dedicated storage device for your games, consider having your root folder there.
{% endhint %}

{% tabs %}
{% tab title="Format" %}
```
<Path>\Modding\Titanfall 2
```
{% endtab %}

{% tab title="Example" %}
```
C:\Users\Wanty\Documents\Modding\Titanfall 2
H:\Modding\Titanfall 2
```
{% endtab %}
{% endtabs %}

After the creation of the Titanfall 2 root folder, more folders have to be created !

{% tabs %}
{% tab title="Struct" %}
```
├── Titanfall 2
│   ├── backup
│   ├── extracted
│   ├── repak
└── └── tools
```
{% endtab %}

{% tab title="Path" %}
```
Titanfall 2\backup
Titanfall 2\extracted
Titanfall 2\repak
Titanfall 2\tools
```
{% endtab %}
{% endtabs %}

As a result, your Titanfall 2 modding folder should look like as in the following screenshot. The purpose of each folders will be explained in details.

![](../../.gitbook/assets/moddingenv\_basicfolders.png)

### Folder - Backup

As the name of the folder suggest, it will be used to store backup of your vpk archives. To perform a backup of a specific VPK archive, the main file and all it's subsequent (typo here) will need to be copied over the backup folder.

A example of a typical backup of the common VPK archive.

{% tabs %}
{% tab title="Struct" %}
```
├── Titanfall 2
│   ├── backup
│   │   ├── client_mp_common.bsp.pak000_000.vpk
│   │   ├── client_mp_common.bsp.pak000_001.vpk
│   │   ├── client_mp_common.bsp.pak000_002.vpk
│   │   ├── client_mp_common.bsp.pak000_003.vpk
│   │   ├── client_mp_common.bsp.pak000_005.vpk
│   │   ├── client_mp_common.bsp.pak000_006.vpk
│   │   ├── client_mp_common.bsp.pak000_007.vpk
│   │   ├── client_mp_common.bsp.pak000_008.vpk
│   │   ├── client_mp_common.bsp.pak000_009.vpk
│   │   ├── client_mp_common.bsp.pak000_010.vpk
│   │   ├── client_mp_common.bsp.pak000_011.vpk
│   │   ├── client_mp_common.bsp.pak000_012.vpk
│   │   ├── client_mp_common.bsp.pak000_013.vpk
│   │   └── englishclient_mp_common.bsp.pak000_dir.vpk
│   ├── extracted
│   ├── repak
└── └── tools
```
{% endtab %}

{% tab title="Path" %}
```
Titanfall 2\backup\client_mp_common.bsp.pak000_000.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_001.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_002.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_003.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_005.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_006.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_007.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_008.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_009.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_010.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_011.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_012.vpk
Titanfall 2\backup\client_mp_common.bsp.pak000_013.vpk
Titanfall 2\backup\englishclient_mp_common.bsp.pak000_dir.vpk
```
{% endtab %}
{% endtabs %}

### Folder - extracted

This folder will be the main folder for extracted VPK files, where the different file to be edited will be in.

As the common and frontend VPK are the most common to work on, they have their own folder, single player (levels) and multiplayer (maps) VPK will have their own sub folder.

In the example following, the folders `common`, `frontend` and `angel city`, would be populated. You don't need to create all the folders inside them, that would be done as their respective VPK archive are extracting.

{% tabs %}
{% tab title="Struct" %}
```
├── Titanfall 2
│   ├── backup
│   ├── extracted
│   │   ├── common
│   │   │   ├── cfg
│   │   │   ├── depot
│   │   │   ├── maps
│   │   │   ├── materials
│   │   │   ├── models
│   │   │   ├── resource
│   │   │   └── scripts
│   │   ├── frontend
│   │   │   ├── cfg
│   │   │   ├── materials
│   │   │   ├── media
│   │   │   ├── particles
│   │   │   ├── resource
│   │   │   ├── scripts
│   │   │   ├── shaders
│   │   │   ├── sound
│   │   │   ├── vgui
│   │   │   ├── gameinfo.txt
│   │   │   ├── platlists_v2.txt
│   │   │   └── splitscreen_config.txt
│   │   ├── mp
│   │   │   └── angel city
│   │   │   │   ├── depot
│   │   │   │   ├── maps
│   │   │   │   ├── materials
│   │   │   │   ├── models
│   │   │   │   ├── resource
│   │   │   └── └── scripts
│   │   └── sp
│   ├── repak
└── └── tools
```
{% endtab %}

{% tab title="Path" %}
```
Titanfall 2\backup
Titanfall 2\extracted
Titanfall 2\extracted\common\cfg
Titanfall 2\extracted\common\depot
Titanfall 2\extracted\common\maps
Titanfall 2\extracted\common\materials
Titanfall 2\extracted\common\models
Titanfall 2\extracted\common\resource
Titanfall 2\extracted\common\scripts
Titanfall 2\extracted\frontend\cfg
Titanfall 2\extracted\frontend\materials
Titanfall 2\extracted\frontend\media
Titanfall 2\extracted\frontend\particles
Titanfall 2\extracted\frontend\resource
Titanfall 2\extracted\frontend\scripts
Titanfall 2\extracted\frontend\shaders
Titanfall 2\extracted\frontend\sound
Titanfall 2\extracted\frontend\vgui
Titanfall 2\extracted\frontend\gameinfo.txt
Titanfall 2\extracted\frontend\platlists_v2.txt
Titanfall 2\extracted\frontend\splitscreen_config.txt
Titanfall 2\extracted\mp\angel city\depot
Titanfall 2\extracted\mp\angel city\maps
Titanfall 2\extracted\mp\angel city\materials
Titanfall 2\extracted\mp\angel city\models
Titanfall 2\extracted\mp\angel city\resource
Titanfall 2\extracted\mp\angel city\scripts
Titanfall 2\extracted\sp
Titanfall 2\repak
Titanfall 2\tools
```
{% endtab %}
{% endtabs %}

### Folder - repak

The folder used for the output of the VPK tool while repacking a VPK archive. It is a bad practice to repack directly into your game directory. For VPK use of the VPK tool, check:

{% content-ref url="how-to-backup-extract-and-repack.md" %}
[how-to-backup-extract-and-repack.md](how-to-backup-extract-and-repack.md)
{% endcontent-ref %}

### Folder - tools

The folder containing your modding tools for Titanfall 2. Each of those folders would contain the software files for their respective tool.

{% tabs %}
{% tab title="Struct" %}
```
├── Titanfall 2
│   ├── backup
│   ├── extracted
│   ├── repak
│   ├── tools
│   │   ├── Icepick
│   │   ├── Titanfall 2 Toolkit
│   │   ├── TitanfallMapExporter.py
└── └── └── VPK tool
```
{% endtab %}

{% tab title="Path" %}
```
Titanfall 2\backup
Titanfall 2\extracted
Titanfall 2\repak
Titanfall 2\tools
Titanfall 2\tools\Icepick
Titanfall 2\tools\Titanfall 2 Toolkit
Titanfall 2\tools\TitanfallMapExporter.py
Titanfall 2\tools\VPK tool
```
{% endtab %}
{% endtabs %}

## Advanced

In addition to the basic environment, some additionnal folders will be made.

{% tabs %}
{% tab title="Struct" %}
```
├── Titanfall 2
│   ├── backup
│   ├── extracted
│   ├── repak
│   ├── resource
└── └── tools
```
{% endtab %}

{% tab title="Path" %}
```
Titanfall 2\backup
Titanfall 2\extracted
Titanfall 2\repak
Titanfall 2\resource
Titanfall 2\tools
```
{% endtab %}
{% endtabs %}

### Folder - extracted

Using git for your extracted VPK files allow you to have different set of VPK (main, dev, research, etc.) while keeping things under a decent amount of sub folders.

{% embed url="https://en.wikipedia.org/wiki/Git" %}

Git is a powerful tool that can be used in numerous way, your CLI, dedicated software, your code editor of choice, etc.

For the common and frontend VPK, having a separate copy, vanilla (not modded) that will stay vanilla is a time saver, comparing files, restore certain files, etc.Git can be used for a extracted VPK. Idealy, setting up git would be done for the most used VPK, but that is up to personal preference to adapt each users workflow.\
Each VPK folder that has git setup has a extra sub folder so the .git folder is not included while repacking a VPK. The VPK tool does not have the ability to exclude files / folder.

{% hint style="warning" %}
The \*.vpk in the folder structure aren't VPK archive. They are folders name.
{% endhint %}

```
├── Titanfall 2
│   ├── backup
│   ├── extracted
│   │   ├── common
│   │   │   ├── .git
│   │   │   └── englishclient_mp_common.bsp.pak000_dir.vpk
│   │   ├── common_vanilla
│   │   ├── frontend
│   │   │   ├── .git
│   │   │   └── englishclient_frontend.bsp.pak000_dir.vpk
│   │   ├── frontend_vanilla
│   │   ├── mp
│   │   │   ├── angel city
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_angel_city.bsp.pak000_dir.vpk
│   │   │   ├── black water canal
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_black_water_canal.bsp.pak000_dir.vpk
│   │   │   ├── boomtown
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_grave.bsp.pak000_dir.vpk
│   │   │   ├── coliseum classic
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_coliseum.bsp.pak000_dir.vpk
│   │   │   ├── coliseum pillars
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_coliseum_column.bsp.pak000_dir.vpk
│   │   │   ├── colony
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_colony02.bsp.pak000_dir.vpk
│   │   │   ├── complex
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_complex3.bsp.pak000_dir.vpk
│   │   │   ├── crashsite
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_crashsite3.bsp.pak000_dir.vpk
│   │   │   ├── deck
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_lf_deck.bsp.pak000_dir.vpk
│   │   │   ├── drydock
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_drydock.bsp.pak000_dir.vpk
│   │   │   ├── eden
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_eden.bsp.pak000_dir.vpk
│   │   │   ├── exoplanet
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_thaw.bsp.pak000_dir.vpk
│   │   │   ├── forwardbase kodai
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_forwardbase_kodai.bsp.pak000_dir.vpk
│   │   │   ├── glitch
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_glitch.bsp.pak000_dir.vpk
│   │   │   ├── meadow
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_lf_meadow.bsp.pak000_dir.vpk
│   │   │   ├── relic
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_relic02.bsp.pak000_dir.vpk
│   │   │   ├── rise
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_rise.bsp.pak000_dir.vpk
│   │   │   ├── stacks
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_lf_stacks.bsp.pak000_dir.vpk
│   │   │   ├── township
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_lf_township.bsp.pak000_dir.vpk
│   │   │   ├── traffic
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_lf_traffic.bsp.pak000_dir.vpk
│   │   │   ├── uma
│   │   │   │   ├── .git
│   │   │   │   └── englishclient_mp_lf_uma.bsp.pak000_dir.vpk
│   │   │   └── wargames
│   │   │       ├── .git
│   │   │       └── englishclient_mp_wargames.bsp.pak000_dir.vpk
└── └── └── sp
            ├── englishclient_sp_beacon.bsp.pak000_dir.vpk
            ├── englishclient_sp_beacon_spoke0.bsp.pak000_dir.vpk
            ├── englishclient_sp_boomtown.bsp.pak000_dir.vpk
            ├── englishclient_sp_boomtown_end.bsp.pak000_dir.vpk
            ├── englishclient_sp_boomtown_start.bsp.pak000_dir.vpk
            ├── englishclient_sp_crashsite.bsp.pak000_dir.vpk
            ├── englishclient_sp_hub_timeshift.bsp.pak000_dir.vpk
            ├── englishclient_sp_s2s.bsp.pak000_dir.vpk
            ├── englishclient_sp_sewers1.bsp.pak000_dir.vpk
            ├── englishclient_sp_skyway_v1.bsp.pak000_dir.vpk
            ├── englishclient_sp_tday.bsp.pak000_dir.vpk
            ├── englishclient_sp_timeshift_spoke02.bsp.pak000_dir.vpk
            └── englishclient_sp_training.bsp.pak000_dir.vpk
```

### Folder - repak

To make things easier, some batch scripts can be used to rename and move the freshly made VPK in your game directory.

Based on the following format and examples, you can adapt it to fit your setup.

{% tabs %}
{% tab title="Format" %}
{% code title="Modding\Titanfall 2\repak\<Script Name>.bat" %}
```
move /y pak000_000.vpk "<Game Directory>\vpk\<VPK archive name>"
move /y pak000_dir.vpk "<Game Directory>\vpk\<VPK directory name>"
```
{% endcode %}
{% endtab %}

{% tab title="common.bat" %}
{% code title="Modding\Titanfall 2\repak\common.bat" %}
```
move /y pak000_000.vpk "C:\Program Files (x86)\Origin Games\Titanfall 2\vpk\client_mp_common.bsp.pak000_000.vpk"
move /y pak000_dir.vpk "C:\Program Files (x86)\Origin Games\Titanfall 2\vpk\englishclient_mp_common.bsp.pak000_dir.vpk"

```
{% endcode %}
{% endtab %}

{% tab title="frontend.bat" %}
{% code title="Modding\Titanfall 2\repak\frontend.bat" %}
```
move /y pak000_000.vpk "C:\Program Files (x86)\Origin Games\Titanfall 2\vpk\client_frontend.bsp.pak000_000.vpk"
move /y pak000_dir.vpk "C:\Program Files (x86)\Origin Games\Titanfall 2\vpk\englishclient_frontend.bsp.pak000_dir.vpk"
```
{% endcode %}
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Be careful while using the scripts. If you launch a script for the wrong VPK, it will lead to your game crashing.\
The script has no way to tell the difference between the correct VPK to rename automatically. With that said, if mistakes are done, it can easily be fixed using your backup files.
{% endhint %}

### Folder - resource

Depending of what you are doing in modding, you might want to have dedicated folder for some type of game assets.

A typical setup would look like that

{% tabs %}
{% tab title="Struct" %}
```
├── Titanfall 2
│   ├── backup
│   ├── extracted
│   ├── repak
│   ├── resource
│   │   ├── blender
│   │   ├── docs
│   │   ├── materials
│   │   ├── media
│   │   └── textures
└── └── tools
```
{% endtab %}

{% tab title="Path" %}
```
```
{% endtab %}
{% endtabs %}
