# Vtex - Troubleshooting

The following is a list of errors and problems that can occur while using [Vtex](./).

When listing a new error here, please follow the established format.

## Local Steam service is not running

Vtex will give the following error:

```
SteamStartup() failed: SteamStartup(0xf,0x0012F0E4) failed with error 108: The local Steam Service is not running
```

Steam must run while Vtex is run. Start Steam to fix this.

## Problem figuring out outputdir

Vtex will give the following error:

```
Problem figuring out outputdir for <path>
```

As a first step, check that the texture to convert is really in the `\sourcesdk_content\gamedir\materialsrc` folder, where gamedir is the game folder (`cstrike`/`dod`/`hl2`/`hl2mp`).

If the texture is in the correct folder, the error might instead be caused by a complication with the environment variables. Primarily, this should be able to be eliminated by using [VConfig](../../game-directory.md) and ensuring the selected mod has been run at least once. However, there are cases where this doesn't solve the problem.

One solution is to remove the instance of the VProject Environment variable. In Windows XP this can be accomplished by the following:

1. Right-click on My computer and click on Properties.
2. Select the Advanced tab.
3. Click on Environment Variables near the bottom of the window.
4. In the System variables section scroll down and highlight the line VProject.
5. Click the Delete button.
6. Click OK twice to exit.

However, this solution will create the Unable to find gameinfo.txt error instead. **To do: **Delete this non-functioning solution alternative?

### **Alternative Solution**

vtex.exe cannot understand spaces in the input file. One solution is to create a folder directly on the C:/ drive with the same name as the original one the vtex shortcut was pointing at. For example, create C:/tf instead of C:\Program Files\Steam\steamapps\\\<account\_name>\team fortress 2\tf. Update the vtex.exe shortcut to point to this new folder. In this folder, put the gameinfo.txt from the original folder, as well as an empty materialsrc and materials folder. Place your file to be converted in the new materialsrc folder. Now drag-and-drop the file onto the vtex shortcut, and the output will be in the new materials folder.
