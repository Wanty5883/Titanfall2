---
description: 材质$flags和$flags2参数控制材质的渲染方式。
---

# 材质标志

材质 `$flags` 和 `$flags2` 参数控制材质的渲染方式。 `$flag` 允许在渲染中实时进行更改，但是 `$flags2` 是只读的，可以帮助引擎或其他代码正确使用材质。 在下面的链接中可以中找到枚举[https://github.com/ValveSoftware/source-sdk-2013/blob/master/mp/src/public/materialsystem/imaterial.h](https://github.com/ValveSoftware/source-sdk-2013/blob/master/mp/src/public/materialsystem/imaterial.h)

也可以通过下面的.vmt样例设置标志：

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

$flags 可以包含以下标志：

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

$flags2 可以包含以下标志：

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

