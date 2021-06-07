# 颜色和纹理信息

## VMT 和& VTF

VMT 和 VTF 是配合着工作的。 VTF 包含纹理（图形）集，VMT包含材料属性设置（值）。.

## VMT

这儿有关于 VMT 文件的进一步信息。下面的一些子标题将会对一些参数进行说明：

### $layercolor

这个参数用来配置一部分纹理的颜色。这个参数并不适用于所有情况，颜色也可以通过外部的VTF文件配置。下面这个语句是你可能在泰坦陨落2中遇到的参数案例：

```text
$layercolor2      "[3 0 3]"
```

_`$layercolor2`_ 使用RGB值，但是值的范围并不是0-255。当在数值两侧使用方括号时，起源引擎将会把方括号中的值解释为百分比值的RGB值。如果你对此方面的参数不熟悉，请参阅[起源VMT颜色参数文档](https://noskill.gitbook.io/titanfall2/how-to-start-modding/modding-tools#graphics-animation-color)，这会让你对此有更深层次的理解。如果你熟悉RGB的值，此案例中的255将对应1值，而0对应的值为0。例如，粉红\[255,0,255\]将会被转换为\[1,0,1\]。另外，纯白色是\[1,1,1\]，纯黑色是\[0,0,0,\]。

在泰坦陨落2中，你可以使用超过1的值，这会使颜色过曝。对于暖色，我们推荐你使用1-5之间的值，再高效果可能就不是很好了（个人观点）。 

### $texture2 & $basetexture

这个值是你想要使用的纹理的路径。这两个参数都可以通过路径值来引用任何纹理文件，当然，在某些情况下，一些纹理可能会错乱或者不工作。下面是一个使用这个值的案例，这些值在默认情况下都指向`materials`文件夹中的子文件夹，且你不需要对路径中的文件添加任何扩展名

```text
"$basetexture" "models\weapons\lstar\lstar_heat_charge_col"
```

下面是上述例子使用的贴图的实际路径：`englishclient_mp_common.bsp.pak000_dir.vpk\materials\models\weapons\lstar`

### **texturescrollrate**

这个值是 `$texture2` & `$basetexture`参数的附加参数。它用来按顺时针（正数）或者逆时针（负数）滚动纹理。

### **texturescale**

这个值将会定义你模型上纹理的大小。

### $allowoverbright

这个值将会增加或减少纹理发光效果的程度。

## VTF

这儿有关于 VTF 文件的进一步信息。下面的一些子标题将会对一些参数进行说明：

### 如何编辑动态纹理颜色

一旦你在 VTFEdit 中加载纹理，请将其以 PNG 格式提取出到你的导出文件夹之外。

> e.g. C:\Users\YourSessionName\Documents\Titanfall 2 Modding\extracted texture

PNG 格式很重要，对于动画纹理，你需要透明的背景。

编辑动画纹理的方式不止有一种，此处只会展示原作者的方法。当然，你也可以通过对视频切片并导入VTFEdit或者其他的一些方法来制作动态纹理，更多方法请自行摸索。

**1. 使用Photoshop载入图片**

将PNG图片导入 Adobe Photoshop 中。由白色和灰色方块组成的背景意味着背景是透明的，这点很重要（当然也可以不是透明的，根据你自己需要来即可），请不要使用此[链接](https://raw.githubusercontent.com/Wanty5883/Titanfall2/master/picture/Animated%20texture1.PNG)中的图片，这只是个例子。

**2.打开渐变贴图**

![](https://github.com/Wanty5883/Titanfall2/raw/master/picture/Animated%20texture2.PNG?raw=true)

一旦你导入了渐变贴图，它将会添加一个图层并改变纹理的颜色。下面这些图片会有助于你的理解。接着请打开渐变贴图工具： 

![](https://github.com/Wanty5883/Titanfall2/raw/master/picture/Animated%20texture3.PNG?raw=true)

![](https://github.com/Wanty5883/Titanfall2/raw/master/picture/Animated%20texture4.PNG?raw=true)

* 1 是不透明度，但是我们暂时不需要调整。
* 2 是颜色，这是我们需要调整的参数。 

从个人观点来说，我更倾向于去还原原来的饱和度。[这儿](https://github.com/Wanty5883/Titanfall2/blob/master/picture/Animated%20texture5.PNG?raw=true)你可以看到我在游戏中使用的例子。这个功能你上手过一遍很容易就能习惯了。

**3. 保存纹理**

一旦你编辑好了你想要的颜色，请将纹理以PNG格式输出（这点很重要），并确保背景依旧是透明的。请不要对你的纹理的其他属性比如大小，压缩率，文件格式等进行修改。

**4. 导入纹理到VTFEdit**

请在 VTFEdit 中按快捷键 _`CTRL+I`_ 来导入材质。 VTFEdit 会要求你对其属性进行一些设置。

* 通用设置：
  * 一般格式 - DXT1
  * Alpha 格式 - DXT5
  * 纹理种类 - Animated Texture
* 大小调整 - 保持默认即可
* Mipmaps 
  * Mipmap 滤镜 - Box
  * 锐化滤镜 - Sharpen Soft
* 法线贴图 - 保持默认即可

然后请点击下方的 _`OK`_。在处理完成之后，你编辑的纹理将会加载进VTFEdit，**它可能看起来会有些奇怪**，但如果你操作没问题的话，游戏应该是能正确读取的。之后，请保存文件，打包好VPK并覆盖游戏文件。

