# RSPNVPK

## About

RSPNVPK is a new VPK repacker written by [Mr Steyk](https://github.com/mrsteyk) which creates a VPK patch rather than repacking the entire VPK.

### What can it do:

* Repack a VPK
* Replace files
* Add files
* Delete files

### What can't it do:

* Unpack a VPK

## Downloading

You can get the latest version of the tool from Mr Steyk's [repo](https://github.com/mrsteyk) on the [releases](https://github.com/mrsteyk/RSPNVPK/releases) page.

## Usage

{% hint style="info" %}
**You will only have to backup the `englishclient` VPK files in your `Titanfall2/vpk` directory to restore your game files**
{% endhint %}

Create a folder with the name of the VPK you are looking to make modifications to. For example if you are trying to modify the frontend VPK, rename the folder `englishclient_frontend.bsp.pak000_dir` and drag the `englishclient_frontend.bsp.pak000_dir.vpk` onto the `RSPNVPK.exe` 

You should see a screen that looks like this:

![](../../.gitbook/assets/image%20%2812%29.png)

Like the tool says make sure you have a backup beforehand, then press `ENTER` 

![](../../.gitbook/assets/image%20%2816%29.png)

When the tool is done, you can press `ENTER` to close the tool and you will have a new `client_frontend.bsp.pak000_228.vpk` file. Copy both these files to your VPK folder to install your new mod.

{% hint style="info" %}
To delete files, add a `.delete` to the end of the filename of the file you want to remove from the VPK
{% endhint %}

## Installation

### Windows

To run RSPNVPK from anywhere in windows, you will need to create a folder for the program in a consistent place such as `C:\Program Files\RSPNVPK`. Now you will need to edit your Environmental Variables.

![](../../.gitbook/assets/image%20%2815%29.png)

![](../../.gitbook/assets/image%20%2813%29.png)

Edit your path and add the folder you set up earlier e.g. `C:\Program Files\RSPNVPK` 

Close and reload any console windows you have open and run `RSPNVPK` . It should return **Invalid usage...**

![](../../.gitbook/assets/image%20%2817%29.png)



```
RSPNVPK englishclient_frontend.bsp.pak000_dir.vpk -s
```



