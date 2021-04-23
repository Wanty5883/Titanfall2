---
description: >-
  这个武器页面用于引导你修改铁驭武器的方方面面， from making your gun blind you to making your gun not
  exist 这个页面将引导你至所需的指南。
---

# 武器

## 武器效果

修改武器的视觉效果。这将改变你的武器所产生的各种效果，包括你的枪焰和弹道。

{% page-ref page="weapon-effects.md" %}

## 准星修改

本指南将向你展示如何更改准星显示。 

{% page-ref page="crosshair-modding/" %}

## 武器定位

本指南将向你展示如何更改武器在屏幕上的位置。这意味着你的武器可以使用移动到屏幕中心的末日风，甚至使枪在左手边，这一切都取决于你的喜好。

{% page-ref page="weapon-positioning.md" %}

## 武器视野

更改武器视图模型视野指南

{% page-ref page="weapon-fov.md" %}

## 一键更换武器视野

如何在腰射时使用缩放效果。

{% page-ref page="weapon-fov-1.md" %}

## 特殊/独特武器修改

这些修改只限于文章中的武器，不适用于其他武器；本指南将告诉你如何修改它们。

{% page-ref page="weapons/" %}









## 参数

{% tabs %}
{% tab title="RUI\_CrosshairData Args" %}
| 参数 | Value | Note |
| :--- | :--- | :--- |
| adjustedSpread | weapon\_spread |  |
| adsFrac | player\_zoomFrac |  |
| ammoFrac | progress\_weapon\_clip\_ammo\_frac |  |
| ammoFrac | progress\_grapple\_power |  |
| chargeFrac | player\_chargeFrac |  |
| chargeLevel | player\_chargeLevel |  |
| chargeMaxTime | eWeaponVar.custom\_float\_0 |  |
| chargeStartTime | weapon\_script\_time\_0 |  |
| clipAmmo | weapon\_ammo |  |
| clipSize | weapon\_clipSize |  |
| crosshairMovementX | crosshair\_movement\_x |  |
| crosshairMovementY | crosshair\_movement\_y |  |
| dryfireTime | weapon\_latest\_dryfire\_time |  |
| isActive | weapon\_is\_active |  |
| isAmped | weapon\_is\_amped |  |
| isFiring | weapon\_is\_firing |  |
| isGrappleInRange | grapple\_in\_range |  |
| isLocked | smartammo\_locked |  |
| isReloading | weapon\_is\_reloading |  |
| isSprinting | player\_is\_sprinting |  |
| readyFrac | progress\_ready\_to\_fire\_frac |  |
| regenRate | eWeaponVar.regen\_ammo\_refill\_rate |  |
| smartFov | eWeaponVar.smart\_ammo\_search\_angle |  |
| teamColor | crosshair\_team\_color |  |
{% endtab %}

{% tab title="Mods Args" %}
| Argument | Value | Note |
| :--- | :--- | :--- |
| ammo | weapon\_ammo |  |
| ammoFrac | weapon\_ammofrac |  |
| chargeFrac | progress\_weapon\_charge\_frac |  |
| clipAmmo | weapon\_ammo |  |
| clipCount | weapon\_stockpileClipCount |  |
| clipSize | weapon\_clipSize |  |
| inCooldown | weapon\_is\_inCooldown |  |
| isActive | weapon\_is\_active |  |
| isAmped | weapon\_is\_amped |  |
| isCooling | weapon\_is\_inCooldown |  |
| isFiring | weapon\_is\_firing |  |
| isInCooldown | weapon\_is\_inCooldown |  |
| isReloading | weapon\_is\_reloading |  |
| lastDryFireTime | weapon\_latest\_dryfire\_time |  |
| lifetimeShots | weapon\_lifetime\_shots |  |
| pchargeFrac | player\_chargeFrac |  |
| proOwnedByPlayer | proscreen\_owner\_is\_player |  |
| proValue | proscreen\_int0 |  |
| readyFrac | progress\_ready\_to\_fire\_frac |  |
| readyToFireFrac | progress\_ready\_to\_fire\_frac |  |
| vis | player\_zoomfrac |  |
| zoomFrac | player\_zoomfrac |  |
{% endtab %}
{% endtabs %}

