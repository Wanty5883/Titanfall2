---
description: >-
  This weapons page will lead you to modding every aspect of your Pilot Weapon,
  from making your gun blind you to making your gun not exist this page will
  lead you to the guide you need.
---

# 武器

## 武器特效

Modify the visual aspect of your weapon. This will modify what effect your weapon makes, This includes what your muzzle flash looks like to what the bullet projectile looks like as well. 

{% page-ref page="weapon-effects.md" %}

## 准星修改

This guide will show you how to change what your crosshair looks like. 

{% page-ref page="crosshair-modding/" %}

## 武器定位

This guide will show you how to change what the position of your weapon is on screen. This means your weapon can be moved to the center of the screen doom style or even making the gun left handed, It's all up to your tastes.

{% page-ref page="weapon-positioning.md" %}

## 武器FOV

Guide to changing the weapon viewmodel fov

{% page-ref page="weapon-fov.md" %}

## 瞄准FOV

How to create a zoom effect while hipfiring.

{% page-ref page="weapon-fov-1.md" %}

## 特殊/独特武器修改

These mods are restricted only to these weapons and won't apply to any others, this guide will show you how to mod them.

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

