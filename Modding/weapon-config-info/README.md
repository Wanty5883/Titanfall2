---
description: >-
  This weapons page will lead you to modding every aspect of your Pilot Weapon,
  from making your gun blind you to making your gun not exist this page will
  lead you to the guide you need.
---

# Weapon

## Weapon Effects

Modify the visual aspect of your weapon. This will modify what effect your weapon makes, This includes what your muzzle flash looks like to what the bullet projectile looks like as well.&#x20;

{% content-ref url="../../game-values/fx/fx-raw-data/fx-weapon/" %}
[fx-weapon](../../game-values/fx/fx-raw-data/fx-weapon/)
{% endcontent-ref %}

## Crosshair modding

This guide will show you how to change what your crosshair looks like.&#x20;

{% content-ref url="crosshair-modding/" %}
[crosshair-modding](crosshair-modding/)
{% endcontent-ref %}

## Weapon positioning&#x20;

This guide will show you how to change what the position of your weapon is on screen. This means your weapon can be moved to the center of the screen doom style or even making the gun left handed, It's all up to your tastes.

{% content-ref url="weapon-positioning.md" %}
[weapon-positioning.md](weapon-positioning.md)
{% endcontent-ref %}

## Weapon FOV

Guide to changing the weapon viewmodel fov

{% content-ref url="weapon-fov.md" %}
[weapon-fov.md](weapon-fov.md)
{% endcontent-ref %}

## Hipfire Zoom

How to create a zoom effect while hipfiring.

{% content-ref url="hipfire-zoom.md" %}
[hipfire-zoom.md](hipfire-zoom.md)
{% endcontent-ref %}

## Special/Unique weapon mods

These mods are restricted only to these weapons and won't apply to any others, this guide will show you how to mod them.

{% content-ref url="weapons/" %}
[weapons](weapons/)
{% endcontent-ref %}









## Arguments

{% tabs %}
{% tab title="RUI_CrosshairData Args" %}
| Argument           | Value                                 | Note |
| ------------------ | ------------------------------------- | ---- |
| adjustedSpread     | weapon\_spread                        |      |
| adsFrac            | player\_zoomFrac                      |      |
| ammoFrac           | progress\_weapon\_clip\_ammo\_frac    |      |
| ammoFrac           | progress\_grapple\_power              |      |
| chargeFrac         | player\_chargeFrac                    |      |
| chargeLevel        | player\_chargeLevel                   |      |
| chargeMaxTime      | eWeaponVar.custom\_float\_0           |      |
| chargeStartTime    | weapon\_script\_time\_0               |      |
| clipAmmo           | weapon\_ammo                          |      |
| clipSize           | weapon\_clipSize                      |      |
| crosshairMovementX | crosshair\_movement\_x                |      |
| crosshairMovementY | crosshair\_movement\_y                |      |
| dryfireTime        | weapon\_latest\_dryfire\_time         |      |
| isActive           | weapon\_is\_active                    |      |
| isAmped            | weapon\_is\_amped                     |      |
| isFiring           | weapon\_is\_firing                    |      |
| isGrappleInRange   | grapple\_in\_range                    |      |
| isLocked           | smartammo\_locked                     |      |
| isReloading        | weapon\_is\_reloading                 |      |
| isSprinting        | player\_is\_sprinting                 |      |
| readyFrac          | progress\_ready\_to\_fire\_frac       |      |
| regenRate          | eWeaponVar.regen\_ammo\_refill\_rate  |      |
| smartFov           | eWeaponVar.smart\_ammo\_search\_angle |      |
| teamColor          | crosshair\_team\_color                |      |
{% endtab %}

{% tab title="Mods Args" %}
| Argument         | Value                                | Note |
| ---------------- | ------------------------------------ | ---- |
| ammo             | weapon\_ammo&#xD;                    |      |
| ammoFrac         | weapon\_ammofrac&#xD;                |      |
| chargeFrac       | progress\_weapon\_charge\_frac&#xD;  |      |
| clipAmmo         | weapon\_ammo&#xD;                    |      |
| clipCount        | weapon\_stockpileClipCount&#xD;      |      |
| clipSize         | weapon\_clipSize&#xD;                |      |
| inCooldown       | weapon\_is\_inCooldown&#xD;          |      |
| isActive         | weapon\_is\_active&#xD;              |      |
| isAmped          | weapon\_is\_amped&#xD;               |      |
| isCooling        | weapon\_is\_inCooldown&#xD;          |      |
| isFiring         | weapon\_is\_firing&#xD;              |      |
| isInCooldown     | weapon\_is\_inCooldown&#xD;          |      |
| isReloading      | weapon\_is\_reloading&#xD;           |      |
| lastDryFireTime  | weapon\_latest\_dryfire\_time        |      |
| lifetimeShots    | weapon\_lifetime\_shots&#xD;         |      |
| pchargeFrac      | player\_chargeFrac&#xD;              |      |
| proOwnedByPlayer | proscreen\_owner\_is\_player&#xD;    |      |
| proValue         | proscreen\_int0                      |      |
| readyFrac        | progress\_ready\_to\_fire\_frac&#xD; |      |
| readyToFireFrac  | progress\_ready\_to\_fire\_frac      |      |
| vis              | player\_zoomfrac&#xD;                |      |
| zoomFrac         | player\_zoomfrac                     |      |
{% endtab %}
{% endtabs %}
