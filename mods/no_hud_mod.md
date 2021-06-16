---
description: 'Installation, removal and settings of the No-HUD mod'
---

# 无HUD修改

## 前期准备

To install this mod, you are going to need an archive software. You can find more about that in the [tool page](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools#archives).

## 下载软件并安装

{% hint style="warning" %}
Following the tutorial will disable your Origin Overlay. However it can be enabled again \(more on that in the Removal paragraph\).
{% endhint %}

First, you'll need to download the mod from [here](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools#titanfall), then unpack it into a folder. There's going to be 2 versions in there, one for Nvidia graphic card users and one for AMD users, although both follow the same installation process.

## **需要复制什么以及去哪里复制文件？**

After opening the the right folder, you need to copy the `ShaderFixes` folder and the `d3dx.ini` file and paste it into your main game directory, the one that includes the main Titanfall2.exe file.

Next, copy all of the .dll mod files \(`d3d11.dll`, `d3dcompiler_46.dll` and `nvapi64.dll`\) and paste them into `\Titanfall2\bin\x64_retail`. After this the mod should be ready. You can toggle your in-game HUD on and off by pressing Capslock.

## 移除

To fully remove \(uninstall\) the mod, you'll not only need to remove the files which came from the mod, but also repair your game via Origin. This can be done by entering your Game Library, clicking on Titanfall 2, opening the settings \(they're under the Play button\) and pressing repair. **This process should re-enable your Origin Overlay**, but if it doesn't try, manually re-enabling it in Origin Settings.

{% hint style="info" %}
Following this process will disable all of your current .vpk mods, you'll need to add them again.
{% endhint %}

## 设置

The mod comes with a lot of settings, most of them are related to shaders and rendering, but this guide covers those **related to** the HUD **keybinds**.

### **需要修改什么以及在哪里修改？**

You need to open the `d3dx.ini` file you pasted into your game folder with a text editor, then scroll down to line 86 or use ctrl+f and search for `[Key1]`. If you only want to change your keybind, just type your key into the `key =`  line. Numbers \(0-9\) and letters \(A-Z\) can be inputed by simply typing them in, e.g. `key = Y` would bind your HUD toggle on/off function to Y. For key combinations, you only need to separate your keys with spaces, e.g. `key = C V`. If you wish to use buttons like Tab, Mouse Buttons etc., refer to [this page](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes). You can also change your function type to `hold`, meaning the HUD will disappear when holding a certain button or combination. The `hold` type also supports a `delay` and `release_delay` functions. Those delay the deactivation/activation of the HUD and accept number values, where 1 = 1 millisecond of delay. 

### 电脑平台键位

{% tabs %}
{% tab title="Mouse" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Value</b>
      </th>
      <th style="text-align:left">Button Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>VK_LBUTTON<br /></b>0x01</td>
      <td style="text-align:left">Left mouse button
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>VK_RBUTTON<br /></b>0x02</td>
      <td style="text-align:left">Right mouse button
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_CANCEL</b>
        </p>
        <p>0x03</p>
      </td>
      <td style="text-align:left">Control-break processing
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_MBUTTON</b>
        </p>
        <p>0x04</p>
      </td>
      <td style="text-align:left">Middle mouse button (three-button mouse)
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_XBUTTON1</b>
        </p>
        <p>0x05</p>
      </td>
      <td style="text-align:left">X1 mouse button
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_XBUTTON2</b>
        </p>
        <p>0x06</p>
      </td>
      <td style="text-align:left">X2 mouse button</td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="Modifier Key" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Value</b>
      </th>
      <th style="text-align:left">Button Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>-</b>
        </p>
        <p>0x07</p>
      </td>
      <td style="text-align:left">Undefined
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_BACK</b>
        </p>
        <p>0x08</p>
      </td>
      <td style="text-align:left">BACKSPACE key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_TAB</b>
        </p>
        <p>0x09</p>
      </td>
      <td style="text-align:left">TAB key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>-</b>
        </p>
        <p>0x0A-0B</p>
      </td>
      <td style="text-align:left">Reserved
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_CLEAR</b>
        </p>
        <p>0x0C</p>
      </td>
      <td style="text-align:left">CLEAR key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_RETURN</b>
        </p>
        <p>0x0D</p>
      </td>
      <td style="text-align:left">ENTER key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>-</b>
        </p>
        <p>0x0E-0F</p>
      </td>
      <td style="text-align:left">Undefined
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_SHIFT</b>
        </p>
        <p>0x10</p>
      </td>
      <td style="text-align:left">SHIFT key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_CONTROL</b>
        </p>
        <p>0x11</p>
      </td>
      <td style="text-align:left">CTRL key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_MENU</b>
        </p>
        <p>0x12</p>
      </td>
      <td style="text-align:left">ALT key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_PAUSE</b>
        </p>
        <p>0x13</p>
      </td>
      <td style="text-align:left">PAUSE key
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>VK_CAPITAL</b>
        </p>
        <p>0x14</p>
      </td>
      <td style="text-align:left">CAPS LOCK key</td>
    </tr>
  </tbody>
</table>
{% endtab %}
{% endtabs %}

### **X-Box主机控制**键位

| Value | Button |
| :--- | :--- |
| `XB_A` | ![](../.gitbook/assets/icons8-xbox-a-96.png) |
| `XB_B` | ![](../.gitbook/assets/icons8-xbox-b-96.png)  |
| `XB_X` | ![](../.gitbook/assets/icons8-xbox-x-96.png)  |
| `XB_Y` | ![](../.gitbook/assets/icons8-xbox-y-96.png)  |
| `XB_LEFT_TRIGGER` | ![](../.gitbook/assets/icons8-xbox-lt-96.png)  |
| `XB_LEFT_SHOULDER` | ![](../.gitbook/assets/icons8-xbox-lb-96.png)  |
| `XB_LEFT_THUMB` | ![](../.gitbook/assets/xbox_icon4.png)  |
| `XB_RIGHT_TRIGGER` | ![](../.gitbook/assets/icons8-xbox-rt-96.png)  |
| `XB_RIGHT_SHOULDER` | ![](../.gitbook/assets/icons8-xbox-rb-96.png)  |
| `XB_RIGHT_THUMB` | ![](../.gitbook/assets/xbox_icon3.png)  |
| `XB_DPAD_LEFT` | ![](../.gitbook/assets/xbox_icon2.png)  |
| `XB_DPAD_RIGHT` | ![](../.gitbook/assets/xbox_icon2.png)  |
| `XB_DPAD_UP` | ![](../.gitbook/assets/xbox_icon2.png)  |
| `XB_DPAD_DOWN` | ![](../.gitbook/assets/xbox_icon2.png)  |
| `XB_START` |  |
| `XB_BACK` |  |
| `XB_GUIDE` | ![](../.gitbook/assets/xbox_icon.png)  |

Using this will cause buttons from all connected controllers to activate the function, adding the controller number after `XB` will cause the button from only the specified controller to be used, e.g. `XB2_DPAD_UP`.

