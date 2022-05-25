---
description: Entspy is a tool that can view and edit the entity properties of a BSP file.
---

# Entspy

**Entspy** is a tool that can view and edit the [entity](https://developer.valvesoftware.com/wiki/Entity) properties of a [BSP](https://developer.valvesoftware.com/wiki/BSP) file.\
The program is useful for tweaking small entity properties without compile the map again.\
The latest version of the program is version 0.8, released at the 2nd October 2005.

![The Entspy interface.](../../../../../.gitbook/assets/entspy1.gif)

## Adding spawnpoints to a map

Adding extra spawnpoints to a map is one common reason that you might want to edit a map's entities using Entspy. This is a step-by-step guide of how to do it.

1\. Start a local server running the map. One way to do this is issue the console commands `sv_lan 1` and `map mapname`. This will load the map.

2\. Turn on cheats. Type `sv_cheats 1` in the console.

3\. Type `map_showspawnpoints` in the console. All valid spawnpoints in the map will now show as green boxes.

4\. Type `cl_showpos 1`. Your current map coordinates (X, Y, Z) now show at the top-right of the screen (after "pos:").

5\. Stand in various places, not too near the current spawnpoints, where you wish to create a new spawnpoint. Take a note of your location at each point (you only need record the coordinates to the nearest integer).

6\. Quit the game and load the map in Entspy.

7\. In the list of entities, find the type of spawnpoint you wish to create. For example, in CS:S, the entity `info_player_counterterrorist` marks the CT spawns, and the entity `info_player_terrorist` marks the T spawns.

8\. Make a copy the spawnpoint entity by selecting it and pressing the "Copy" button under the entity list.

9\. Edit the "origin" properties of the copied spawnpoint to match the position you recorded in step 5. Note that you may wish to subtract about 50 units from the z-coordinate (last number) to ensure the spawnpoint height is correct.

10\. Repeat from step 7 for the rest of the positions you recorded.

11\. Save the map using the "File/Save BSP" menu item.

12\. Now load the altered map into the game as before, and issue `map_showspawnpoints` again. You should see your new spawnpoints as green boxes. If they show as red, they are invalid. A spawnpoint is invalid if it intersects with a solid object (such as the ground), or is too close to another entity (such as another spawnpoint). The typical spawnpoint spacing is about 80 units.

![The CT spawn in cs\_office. Green boxes are existing spawnpoints. The current player position is shown at the top-right of the screen](../../../../../.gitbook/assets/cs\_office0000.jpg)

![Adding a new spawnpoint to cs\_office, by copying an existing info\_player\_counterterrorist entity, and editing the "origin" property to match the coordinates of the player position.](../../../../../.gitbook/assets/entspy\_edit.png)

## Video tutorial

{% embed url="https://www.youtube.com/watch?v=irO8V8U9YYY" %}

{% hint style="info" %}
Reference:&#x20;

* [https://developer.valvesoftware.com/wiki/Entspy](https://developer.valvesoftware.com/wiki/Entspy)
* [http://www.bagthorpe.org/bob/cofrdrbob/entspy.html](http://www.bagthorpe.org/bob/cofrdrbob/entspy.html)
{% endhint %}
