---
description: Installation, removal and settings of the No-HUD mod
---

# No-HUD Mod

## Preparation

To install this mod, you are going to need an archive software. You can find more about that in the [tool page](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools#archives).

## Download and Installing&#x20;

{% hint style="warning" %}
Following the tutorial will disable your Origin Overlay. However it can be enabled again (more on that in the Removal paragraph).
{% endhint %}

First, you'll need to download the mod from [here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools#titanfall), then unpack it into a folder. There's going to be 2 versions in there, one for Nvidia graphic card users and one for AMD users, although both follow the same installation process.

## **What and where to copy?**

After opening the the right folder, you need to copy the `ShaderFixes` folder and the `d3dx.ini` file and paste it into your main game directory, the one that includes the main Titanfall2.exe file.

Next, copy all of the .dll mod files (`d3d11.dll`, `d3dcompiler_46.dll` and `nvapi64.dll`) and paste them into `\Titanfall2\bin\x64_retail`. After this the mod should be ready. You can toggle your in-game HUD on and off by pressing Capslock.

## Removal

To fully remove (uninstall) the mod, you'll not only need to remove the files which came from the mod, but also repair your game via Origin. This can be done by entering your Game Library, clicking on Titanfall 2, opening the settings (they're under the Play button) and pressing repair. **This process should re-enable your Origin Overlay**, but if it doesn't try, manually re-enabling it in Origin Settings.

{% hint style="info" %}
Following this process will disable all of your current .vpk mods, you'll need to add them again.
{% endhint %}

## Settings

The mod comes with a lot of settings, most of them are related to shaders and rendering, but this guide covers those **related to** the HUD **keybinds**.

### **What and where to edit?**

You need to open the `d3dx.ini` file you pasted into your game folder with a text editor, then scroll down to line 86 or use ctrl+f and search for `[Key1]`. If you only want to change your keybind, just type your key into the `key = ` line. Numbers (0-9) and letters (A-Z) can be inputed by simply typing them in, e.g. `key = Y` would bind your HUD toggle on/off function to Y. For key combinations, you only need to separate your keys with spaces, e.g. `key = C V`. If you wish to use buttons like Tab, Mouse Buttons etc., refer to [this page](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes). You can also change your function type to `hold`, meaning the HUD will disappear when holding a certain button or combination. The `hold` type also supports a `delay` and `release_delay` functions. Those delay the deactivation/activation of the HUD and accept number values, where 1 = 1 millisecond of delay.&#x20;

### PC keybind

{% tabs %}
{% tab title="Mouse" %}
| **Value**                                                   | Button Name                                         |
| ----------------------------------------------------------- | --------------------------------------------------- |
| <p><strong>VK_LBUTTON</strong><br><strong></strong>0x01</p> | <p>Left mouse button<br></p>                        |
| <p><strong>VK_RBUTTON</strong><br><strong></strong>0x02</p> | <p>Right mouse button<br></p>                       |
| <p><strong>VK_CANCEL</strong></p><p>0x03</p>                | <p>Control-break processing<br></p>                 |
| <p><strong>VK_MBUTTON</strong></p><p>0x04</p>               | <p>Middle mouse button (three-button mouse)<br></p> |
| <p><strong>VK_XBUTTON1</strong></p><p>0x05</p>              | <p>X1 mouse button<br></p>                          |
| <p><strong>VK_XBUTTON2</strong></p><p>0x06</p>              | X2 mouse button                                     |
{% endtab %}

{% tab title="Modifier Key" %}
| **Value**                                     | Button Name              |
| --------------------------------------------- | ------------------------ |
| <p><strong>-</strong></p><p>0x07</p>          | <p>Undefined<br></p>     |
| <p><strong>VK_BACK</strong></p><p>0x08</p>    | <p>BACKSPACE key<br></p> |
| <p><strong>VK_TAB</strong></p><p>0x09</p>     | <p>TAB key<br></p>       |
| <p><strong>-</strong></p><p>0x0A-0B</p>       | <p>Reserved<br></p>      |
| <p><strong>VK_CLEAR</strong></p><p>0x0C</p>   | <p>CLEAR key<br></p>     |
| <p><strong>VK_RETURN</strong></p><p>0x0D</p>  | <p>ENTER key<br></p>     |
| <p><strong>-</strong></p><p>0x0E-0F</p>       | <p>Undefined<br></p>     |
| <p><strong>VK_SHIFT</strong></p><p>0x10</p>   | <p>SHIFT key<br></p>     |
| <p><strong>VK_CONTROL</strong></p><p>0x11</p> | <p>CTRL key<br></p>      |
| <p><strong>VK_MENU</strong></p><p>0x12</p>    | <p>ALT key<br></p>       |
| <p><strong>VK_PAUSE</strong></p><p>0x13</p>   | <p>PAUSE key<br></p>     |
| <p><strong>VK_CAPITAL</strong></p><p>0x14</p> | CAPS LOCK key            |
{% endtab %}
{% endtabs %}

### **X-Box Controller Keybinds**

| Value               | Button                                         |
| ------------------- | ---------------------------------------------- |
| `XB_A`              | ![](../.gitbook/assets/icons8-xbox-a-96.png)   |
| `XB_B`              | ![](../.gitbook/assets/icons8-xbox-b-96.png)   |
| `XB_X`              | ![](../.gitbook/assets/icons8-xbox-x-96.png)   |
| `XB_Y`              | ![](../.gitbook/assets/icons8-xbox-y-96.png)   |
| `XB_LEFT_TRIGGER`   | ![](../.gitbook/assets/icons8-xbox-lt-96.png)  |
| `XB_LEFT_SHOULDER`  | ![](../.gitbook/assets/icons8-xbox-lb-96.png)  |
| `XB_LEFT_THUMB`     | ![](../.gitbook/assets/xbox\_icon4.png)        |
| `XB_RIGHT_TRIGGER`  | ![](../.gitbook/assets/icons8-xbox-rt-96.png)  |
| `XB_RIGHT_SHOULDER` | ![](../.gitbook/assets/icons8-xbox-rb-96.png)  |
| `XB_RIGHT_THUMB`    | ![](../.gitbook/assets/xbox\_icon3.png)        |
| `XB_DPAD_LEFT`      | ![](../.gitbook/assets/xbox\_icon2.png)        |
| `XB_DPAD_RIGHT`     | ![](../.gitbook/assets/xbox\_icon2.png)        |
| `XB_DPAD_UP`        | ![](../.gitbook/assets/xbox\_icon2.png)        |
| `XB_DPAD_DOWN`      | ![](../.gitbook/assets/xbox\_icon2.png)        |
| `XB_START`          |                                                |
| `XB_BACK`           |                                                |
| `XB_GUIDE`          | ![](../.gitbook/assets/xbox\_icon.png)         |

Using this will cause buttons from all connected controllers to activate the function, adding the controller number after `XB` will cause the button from only the specified controller to be used, e.g. `XB2_DPAD_UP`.
