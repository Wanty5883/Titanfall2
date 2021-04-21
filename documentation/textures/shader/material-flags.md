---
description: Material $flags and $flags2 parameters control how the material is rendered.
---

# Material Flags

Material `$flags` and `$flags2` parameters control how the material is rendered. `$flag` can be changed in real-time to allow changes in rendering, but `$flags2` is read-only and assists the engine or other code in using the material correctly. Enumerations found in [https://github.com/ValveSoftware/source-sdk-2013/blob/master/mp/src/public/materialsystem/imaterial.h](https://github.com/ValveSoftware/source-sdk-2013/blob/master/mp/src/public/materialsystem/imaterial.h)

The flags can also be set via the .vmt Example:

```text
#Sets the MATERIAL_VAR_VERTEXCOLOR and MATERIAL_VAR_VERTEXALPHA flag
UnlitGeneric
{
$basetexture brick/brickwall003a
$vertexcolor 1
$vertexalpha 1
}
```

### $flags

$flags can contain the following flags:

| **Flag** | **Value** | **Comment** |
| :--- | :--- | :--- |
| MATERIAL\_VAR\_DEBUG | 1 |  |
| MATERIAL\_VAR\_NO\_DEBUG\_OVERRIDE | 2 |  |
| MATERIAL\_VAR\_NO\_DRAW | 4 |  |
| MATERIAL\_VAR\_USE\_IN\_FILLRATE\_MODE | 8 |  |
| MATERIAL\_VAR\_VERTEXCOLOR | 16 | [$vertexalpha](https://developer.valvesoftware.com/wiki/$vertexalpha) |
| MATERIAL\_VAR\_VERTEXALPHA | 32 | [$vertexalpha](https://developer.valvesoftware.com/wiki/$vertexalpha) |
| MATERIAL\_VAR\_SELFILLUM | 64 | [$selfillum](https://developer.valvesoftware.com/wiki/$selfillum) |
| MATERIAL\_VAR\_ADDITIVE | 128 |  |
| MATERIAL\_VAR\_ALPHATEST | 256 | [$alphatest](https://developer.valvesoftware.com/wiki/$alphatest) |
| MATERIAL\_VAR\_MULTIPASS | 512 |  |
| MATERIAL\_VAR\_ZNEARER | 1024 |  |
| MATERIAL\_VAR\_MODEL | 2048 | [$model](https://developer.valvesoftware.com/wiki/$model) |
| MATERIAL\_VAR\_FLAT | 4096 |  |
| MATERIAL\_VAR\_NOCULL | 8192 | [$nocull](https://developer.valvesoftware.com/wiki/$nocull) |
| MATERIAL\_VAR\_NOFOG | 16384 | [$nofog](https://developer.valvesoftware.com/wiki/$nofog) |
| MATERIAL\_VAR\_IGNOREZ | 32768 | [$ignorez](https://developer.valvesoftware.com/wiki/$ignorez) |
| MATERIAL\_VAR\_DECAL | 65536 |  |
| MATERIAL\_VAR\_ENVMAPSPHERE | 131072 |  |
| MATERIAL\_VAR\_NOALPHAMOD | 262144 |  |
| MATERIAL\_VAR\_ENVMAPCAMERASPACE | 524288 |  |
| MATERIAL\_VAR\_BASEALPHAENVMAPMASK | 1048576 |  |
| MATERIAL\_VAR\_TRANSLUCENT | 2097152 | [$translucent](https://developer.valvesoftware.com/wiki/$translucent) |
| MATERIAL\_VAR\_NORMALMAPALPHAENVMAPMASK | 4194304 |  |
| MATERIAL\_VAR\_NEEDS\_SOFTWARE\_SKINNING | 8388608 |  |
| MATERIAL\_VAR\_OPAQUETEXTURE | 16777216 |  |
| MATERIAL\_VAR\_ENVMAPMODE | 33554432 |  |
| MATERIAL\_VAR\_SUPPRESS\_DECALS | 67108864 |  |
| MATERIAL\_VAR\_HALFLAMBERT | 134217728 | [Half Lambert](https://developer.valvesoftware.com/wiki/Half_Lambert) |
| MATERIAL\_VAR\_WIREFRAME | 268435456 |  |
| MATERIAL\_VAR\_ALLOWALPHATOCOVERAGE | 536870912 |  |
| MATERIAL\_VAR\_IGNORE\_ALPHA\_MODULATION | 1073741824 |  |

### $flags2

$flags2 can contain the following flags:

| **Flag** | **Value** | **Comment** |
| :--- | :--- | :--- |
| MATERIAL\_VAR2\_LIGHTING\_UNLIT | 0 |  |
| MATERIAL\_VAR2\_LIGHTING\_VERTEX\_LIT | 1 |  |
| MATERIAL\_VAR2\_LIGHTING\_LIGHTMAP0 | 2 |  |
| MATERIAL\_VAR2\_LIGHTING\_BUMPED\_LIGHTMAP | 4 |  |
| MATERIAL\_VAR2\_LIGHTING\_MASK | 7 | Sum of 3 above |
| MATERIAL\_VAR2\_DIFFUSE\_BUMPMAPPED\_MODEL | 8 |  |
| MATERIAL\_VAR2\_USES\_ENV\_CUBEMAP | 16 |  |
| MATERIAL\_VAR2\_NEEDS\_TANGENT\_SPACES | 32 |  |
| MATERIAL\_VAR2\_NEEDS\_SOFTWARE\_LIGHTING | 64 |  |
| MATERIAL\_VAR2\_BLEND\_WITH\_LIGHTMAP\_ALPHA | 128 |  |
| MATERIAL\_VAR2\_NEEDS\_BAKED\_LIGHTING\_SNAPSHOTS | 256 |  |
| MATERIAL\_VAR2\_USE\_FLASHLIGHT | 512 |  |
| MATERIAL\_VAR2\_USE\_FIXED\_FUNCTION\_BAKED\_LIGHTING | 1024 |  |
| MATERIAL\_VAR2\_NEEDS\_FIXED\_FUNCTION\_FLASHLIGHT | 2048 |  |
| MATERIAL\_VAR2\_USE\_EDITOR | 4096 |  |
| MATERIAL\_VAR2\_NEEDS\_POWER\_OF\_TWO\_FRAME\_BUFFER\_TEXTURE | 8192 |  |
| MATERIAL\_VAR2\_NEEDS\_FULL\_FRAME\_BUFFER\_TEXTURE | 16384 |  |
| MATERIAL\_VAR2\_IS\_SPRITECARD | 32768 |  |
| MATERIAL\_VAR2\_USES\_VERTEXID | 65536 |  |
| MATERIAL\_VAR2\_SUPPORTS\_HW\_SKINNING | 131072 |  |
| MATERIAL\_VAR2\_SUPPORTS\_FLASHLIGHT | 262144 |  |

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Material\_Flags](https://developer.valvesoftware.com/wiki/Material_Flags)
{% endhint %}

