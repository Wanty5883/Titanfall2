---
description: How to change pretty much all of your weapons to the same crosshair at once.
---

# Batch crosshair modding

## Prerequisites

This guide requires that you understand the basics outlined in Modding introduction, How to backup, extract & repack, and Modding tools. If you do not understand these concepts, please click below.

{% content-ref url="../../../start-modding/modding-intro/" %}
[modding-intro](../../../start-modding/modding-intro/)
{% endcontent-ref %}

This guide also requires that you download a program called TextCrawler 3. Download link can be found [here](https://www.digitalvolcano.co.uk/tcdownloads.html). Any other application capable of making batch modifications based on regular expressions will also work. Other required tools can be found on the tools page.

{% content-ref url="../../../start-modding/modding-intro/tools/" %}
[tools](../../../start-modding/modding-intro/tools/)
{% endcontent-ref %}

This guide is for Windows 10, and we will not provide extended support for other operating systems. Sorry.

## Guide

### Step 1. Isolation of files you'd like to modify

Create a folder for yourself to perform these edits within, mine is called `CrosshairMods`. Place the config files for weapons you'd like to modify. We don't recommend setting titan weapons to all the same, as most of these have alternate states and etc not friendly to static, stock crosshairs. Once this folder is created and it contains your config files move on to the next step.

### Step 2. Open TextCrawler, and configure settings.

![](<../../../.gitbook/assets/image (4) (1).png>)

This step consists of 5 parts, listed below.

1. Slap the path to that folder containing configs you made before into this box
2. Select the "Regular Expression" tab.
3. Change the "Rex Ex:" box to `ui/crosshair_\w+` this filters for all strings beginning with `ui/crosshair_` and stops the selection at the end of the "word" (section of text with no spaces)
4. Set the "Replace:" box to the full id of the crosshair you would like to make your base.
5. Click "Find"

### Step 3. Verify settings are working correctly

![](<../../../.gitbook/assets/image (3).png>)

If all is done correctly, you should see a list of your configs appear with the crosshair settings within them highlighted. Make sure that all of your configs have the "Matches" column value of 1. If this is not the case you will have to manually modify as these configs have multiple overlaid crosshairs.

### Step 4. Batch change your configs

If all is to your satisfaction, click the "Replace" button, and confirm your choice in the popup.

### Step 5. Clean up folders and configs

Open up a config, and verify that the change has gone through, and delete all the `.bak` files created during your edit. Once finished, move all of your configs back into your scripts/weapons folder and repack.

## Footnotes

If you screw something up by improperly using this program, your fault, not ours. If something in this guide is incorrect, message us on discord by tagging `@Frontier Militia`

{% content-ref url="../../../" %}
[..](../../../)
{% endcontent-ref %}
