# 武器视野

## 用到的VPK

{% hint style="success" %}
* englishclient\_mp\_common.bsp.pak000\_dir.vpk
{% endhint %}

你将会用到Titanfall VPK Tool来打开和重新打包《泰坦陨落2》VPK 文件。 [工具链接](https://noskill.gitbook.io/titanfall2/v/chinese/how-to-start-modding/modding-introduction/modding-tools)

{% page-ref page="../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

## 介绍

《泰坦陨落2》和其他起源引擎游戏处理武器瞄准放大的效果时（即右键瞄准），是通过改变武器视野为一个较小的数字来达到放大的效果。本指南将会指导你修改任何武器右键放大时的视野，我们将通过修改每个武器/瞄准镜的 `"zoom_fov"` 变量来实现这一点。

## 编辑

进入下面的解包文件夹：

> \scripts\weapons

这个文件夹包含所有武器的"配置文件"，修改文件所产生的风险由你自己承担。如果因为你修改核心数值而导致的账号封禁，别把责任归咎于我。

在文件中找到这部分代码：

```text
	// Behavior
```

在这一节中，找到名为`"zoom_fov"`的行；这是我们将要修改的变量，以便在使用武器右键瞄准时，变为所需要的缩放。在代码行中查找如下所示的数字：

```text
"zoom_fov"                                        "35"
```

这是小帮手精英`"zoom_fov"` 的默认变量值。 所以当 `"zoom_fov"` 设置为 `"35"`,且基础腰射视野设为110时，我们所得到的实际的水平视野为69.51。

{% hint style="danger" %}
 放大时武器的水平视野取决于你的腰射视野设置。
{% endhint %}

作为基础知识， 变量`"zoom_fov"` 的值设置得越低，你的武器在右键瞄准时放大的幅度就越大；变量的值设置得越高，放大的幅度就越小。您可以修改的变量最大值是 `"70"`。 当 `"zoom_fov"` 设为 `"70"`时，你的武器视野将不会再次放大，并且时刻保持为腰射视野。

你也可以对每件武器不同的瞄准镜设置不同的放大视野。为此，找到你正在编辑的武器的 `Mods` 部分。我们将使用小帮手精英上的HCOG镜作为例子，查找如下内容：

```text
hcog
		{
			"bodygroup3_set"	"1"
			"bodygroup4_set"	"0"
			"bodygroup5_set"	"0"
			"viewmodel_offset_ads"							"0 -6.7 -0.75"
			"zoom_fov"										"35"
			"anim_alt_idleAttack"	"1"

			"dof_zoom_nearDepthStart"						"6.161"
			"dof_zoom_nearDepthEnd"							"9.204"
		}
```

现在将代码行 `"zoom_fov"` 添加到这一节之中，后面加上几个空格，然后在英文状态的双引号中添加一个数字，如下所示：

```text
hcog
		{
			"zoom_fov"        "45"
			"bodygroup3_set"	"1"
			"bodygroup4_set"	"0"
			"bodygroup5_set"	"0"
			"viewmodel_offset_ads"							"0 -6.7 -0.75"
			"zoom_fov"										"35"
			"anim_alt_idleAttack"	"1"

			"dof_zoom_nearDepthStart"						"6.161"
			"dof_zoom_nearDepthEnd"							"9.204"
		}
```

你为每个瞄准镜设置变量`zoom_fov`的数值应该是互不相同的。这样你就可以在游戏中随时装备不同的瞄准镜，从而获得所需要的武器视野缩放。

## 如何换算

In order to determine exactly what your true horizontal FOV will be when ADS, we can use this formula:

Take your `cl_fovScale`value and multiply it by the variable you choose for your `"zoom_fov"`. If you don't know your `cl_fovScale`, then you can determine that by dividing your hip fire FOV by 70. For this example we will use 110 FOV. 

{% hint style="info" %}
**110/70 = 1.5714** &lt;---- this number is our cl\_fovScale \(when fov is set to 110\)
{% endhint %}

We then multiply that number \(cl\_fovScale\) by whatever number we chose for our zoom\_fov variable. In this example we will use "56", as that's what I currently have it set to for my Wingman Elite. 

{% hint style="info" %}
1.5714 x 56 = **87.99** &lt;---- this number is your horizontal FOV in 4:3 aspect ratio
{% endhint %}

4:3 aspect ration is what Source Engine uses to calculate our actual horizontal FOV. Now we need to convert this number to 16:9, which will give us our _true_ horizontal fov. For this, you can just use a tool like [mouse-sensitivity.com](https://www.mouse-sensitivity.com/). Select Titanfall 2, and by default, the calculator should look like this:

![](../../.gitbook/assets/image%20%286%29.png)

All we need to do here is in put the FOV number we just acquired from our previous calculation, in my example I got 87.99

![Make sure you leave FOV type on &quot;Hdeg 4:3&quot;](../../.gitbook/assets/mspaint_emdvxagox7.png)

Now scroll down and you will be greeted with your converted fov calculations:

![](../../.gitbook/assets/mspaint_fapoueshho.png)

The green number next to Actual HFOV is your true horizontal FOV when zoomed in with a weapon.

## 重新打包

{% page-ref page="../../how-to-start-modding/modding-introduction/how-to-backup-extract-and-repack.md" %}

### 杂项注释

The in game slider for FOV is wrong. When fov is set to 110, your `cl_fovScale` remains at 1.55, which means your horizontal fov is actually 108.5, instead of 110. To always ensure that you're playing on the correct fov. Take the number you wish to have for your horizontal fov and divide it by 70. Using 110 as an example 110/70 = 1.5714. We then need to change the `cl_fovScale` variable in order to actually have 110 fov in game. To do this, go to 

> \Documents\Respawn\Titanfall2\profile

And open up `profile.cfg`. Ctrl + F to find `cl_fovScale` and then set it to 1.5714 or whatever number you used to get the correct variable. Save it, and next time you're in game you will have the correct fov. Reminder: changing your fov again in game will require you to redo this change. 

