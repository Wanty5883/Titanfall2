# How to use RSPNVPK

RSPNVPK is a new VPK repacker written by [Mr Steyk](https://github.com/mrsteyk) which creates a VPK patch rather than repacking the entire VPK. It can repack a VPK, replace, add, or delete files in a VPK. It can't, however unpack a VPK, so you would still have to use the VPKTool if you need to do that.

You can get the latest version from Mr Steyek's repository on the [releases page](https://github.com/mrsteyk/RSPNVPK/releases). If not found check [here](https://github.com/squidgyberries/RSPNVPK).

## Usage

{% hint style="info" %}
Unlike the VPKTool, only the `englishclient` VPK files are edited, so you will only have to backup the `englishclient` VPK files in your `Titanfall2/vpk` directory to restore your game files. Because RSPNVPK does not make back ups, make sure to back up your files before editing.
{% endhint %}

To edit a VPK, create a folder with the name of the VPK you are looking to make modifications to. For example, if you are trying to modify `englishclient_frontend.bsp.pak000_dir.vpk`, rename the folder `englishclient_frontend.bsp.pak000_dir`. For each file you want to edit/add/replace, you want to create the filepath that those files would be in. For example, [if you wanted to change `r1_english.txt`](../../../Modding/user-interface/text-modding-r1\_language.md), you would put the edited file in `englishclient_frontend.bsp.pak000_dir\resource`.

![](<../../../.gitbook/assets/image (18).png>)

To delete files in the VPK, just add a `.delete` extension to that file in the correct filepath. In this example [I will remove the sunflares from the game](../../../Modding/misc/remove-sun-flares.md):

![](<../../../.gitbook/assets/image (20).png>)

Once you are done with your edits, copy your folder and the VPK file into the RSPNVPK folder:

![](<../../../.gitbook/assets/image (19).png>)

Next, drag the VPK file onto `RSPNVPK.exe`, and a window showing what files will be edited will be opened:

![](<../../../.gitbook/assets/image (21).png>)

When the tool is done, you can press ENTER to close the tool and you will have a new `client_frontend.bsp.pak000_228.vpk` file. Copy both of the VPK files these files to your game directory to install your modifications.

