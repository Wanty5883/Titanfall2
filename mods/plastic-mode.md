---
description: >-
  Reduce the LOD of textures in Titanfall 2 for aesthetic, visibility or
  performance improvements.
---

# 低配模式

## 前提条件

This tweak requires [NVIDIA inspector](https://nvidia-inspector.en.lo4d.com/windows) \(NVIDIA GPU\) or [ATI Tray Tools](http://www.majorgeeks.com/files/details/ati_tray_tools.html) \(AMD GPU\). For performance tweaking you may also want a code editor such as [VS Code](https://code.visualstudio.com/) or [Notepad++](https://notepad-plus-plus.org/downloads/).

## 极简模式修改

These changes do not reduce the visual fidelity of the game apart from reducing the LOD. This makes the game look sort of plastic and flat, but doesn't reduce visibility or anything.

![Screenshot of &quot;Plastimosa Mode&quot;](https://blobs.gitbook.com/assets%2F-M0m8qtRgPSU-hMNzaem%2F-M0mkXNQZkvEZMHIAa60%2F-M0ncvrKWsQkq-sgtgOf%2Fimage.png?alt=media&token=87c12de8-0094-484a-a3b8-7dae93d4a8a1)

![Captain Tai Plastimosa in action, penetrating your soul with his transparent eyeballs.](../.gitbook/assets/image.png)

### NVIDIA显卡

#### **Step 1.** Open `NVidiaProfileInspectorDmW.exe` and select "Titanfall 2" from the dropdown.

![](https://blobs.gitbook.com/assets%2F-M0m8qtRgPSU-hMNzaem%2F-M0mkXNQZkvEZMHIAa60%2F-M0ndXim-Hpq7JQyxT25%2Fimage.png?alt=media&token=d4feba4e-3d35-4050-acc7-2930d18daf01)

#### Step 2. set "Antialiasing - Transparency Supersampling" to `0x00000008 AA_MODE_REPLAY_MODE_ALL` 

![](../.gitbook/assets/image-1.png)

#### Step 3. Change "Texture filtering - LOD bias \(DX\)" and "Texture filtering - LOD Bias \(OGL\)" to `0x00000078`.

![](../.gitbook/assets/image-2.png)

#### Step 4. Press the "Apply changes" button.

#### Step 5. Launch Titanfall 2 and enjoy plastimosa mode!

### AMD显卡

_**We are unable to provide screenshots for this section, as we do not own an ATI/AMD/Radeon card to test on. Sorry for any inconvenience.**_

1. Go to direct3d → settings → additional → texture lod adjustment
2. Set to 10 \(or higher, higher value = worse game\)
3. Launch Titanfall 2 and enjoy plastimosa mode!

## 性能修改

These tweaks make your game look like utter shit, to be used in combination with the above options, or independently.

#### Config tweaks

In `C:\Users\<user>\Documents\Respawn\Titanfall2\local` you will find a file titled `videoconfig.txt`. This is where the tweaks below must be made. Find and replace each of these parameters within this file, or copy them from the modified one below. 

{% hint style="warning" %}
**DO NOT COPY THE COMMENTS**
{% endhint %}

```c
"VideoConfig"
{
	"setting.cl_particle_fallback_base"		"0" // makes particles less cool
	"setting.cl_particle_fallback_multiplier"		"0" // makes particles even less cool
	"setting.mat_picmip"		"4" // screws with shading and texture loading
	"setting.r_lod_switch_scale"		"0" // makes everything not in the player's viewmodel insanely low detail
	mat_disable_bloom 1 // removes shiny bits around light sources
	mat_specular 0 // just raises performance, fucks with reflections a bit
	mat_bumpmap 0 // something texture related
	r_dynamic 0 // fuck if i know something to do with dynamic lighting
}
```

Do not use these tweaks in combination with V-sync or AA methods other than TSAA. This will cause stuttering.

## Sources and credits

[Titanfall 2 on low-end PCs](http://www.neogaf.com/forum/showthread.php?t=1306327)

[aske1836's comment from discussion "Titanfall 2 is truly a visual spectacle at the absolute minimum](https://www.reddit.com/r/titanfall/comments/6ux5ef/titanfall_2_is_truly_a_visual_spectacle_at_the/dlx9zc3/)"

