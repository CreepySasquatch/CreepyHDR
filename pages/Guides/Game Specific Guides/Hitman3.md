---
title: [Hitman 3 / World of Assassination]
type: 
summary:
description: Hitman 3 / World of Assassination HDR guide
sidebar: false
---

{% include callout.html type="note" content="<b>In 2023 Hitman 3 was renamed to Hitman: World of Assassination, and all three recent Hitman games (Hitman 1 in 2016, Hitman 2 in 2018, and Hitman 3 in 2021) are now part of this single game.</b>" %}

## What you'll need:

1. **Official copy of Hitman 3 / Hitman: World of Assassination**
	- We do not support pirated versions of the game.	
1. **Hitman 3 RenoDX mod:** <https://www.nexusmods.com/hitman3/mods/1002?tab=files>
1. **ReShade Addon version 6.5.1 or later:** <https://reshade.me/#download>

	<img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Guide-Generic-Images/Download%20ReShade.jpg?raw=true" title="ReShade Download Page" style="width:744px;height:297px;"/>
	
1. **Special K (Direct Download Link):** <https://sk-data.special-k.info/SpecialK.exe>
	- Used to apply the Exclusive Fullscreen bypass that is needed to get the HDR to work properly.
	

{% include callout.html type="important" content="If you haven't already done so, please make sure you know what the peak brightness is for your display.  This may also be listed as the maximum brightness while in HDR mode." %}


## Installation Steps:

1. **Download everything mentioned in the links above (RenoDX mod, ReShade, and Special K).**
1. **Install ReShade version 6.5.1 (or newer) with Addon support:**
	1. <details><summary>Pick DirectX 10/11/12 when prompted for the Rendering API version: </summary> 
	<img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Hitman3/ReShade%20DirectX.jpg?raw=true" title="Hitman3 DirectX" style="width:360px;height:466px;"/>
	
	1. In the shader selection screen make sure to select Lilium's HDR Analysis tool.  This will come in handy when configuring the in-game HDR settings.
		- <details><summary>This is listed under <b>ReShade HDR shaders by Lilium</b> and the shader is called <b>lilium_hdrand_sdr_analysis.fx</b>. You can click <b>Sort by:</b> and change the option to <b>A to Z</b> to make finding Lilium's shaders easier: </summary>		
	<img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Guide-Generic-Images/ReShade-Lilium-Shaders.jpg?raw=true" title="Lilium Shaders" style="width:359px;height:470px;"/>
	
	1. When you get to the select addons screen DO NOT PICK ANY ADDONS...*unless you know what the addons are for and are actually going to use them*.  Unneeded addons will hurt your game performance and selecting them all is likely to make your game crash or not boot at all.
		- <details><summary>This is listed under <b>ReShade HDR shaders by Lilium</b> and the shader is called <b>lilium_hdrand_sdr_analysis.fx</b>. You can click <b>Sort by:</b> and change the option to <b>A to Z</b> to make finding Lilium's shaders easier. </summary>		
	<img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Guide-Generic-Images/ReShade%20Skip%20Addons.jpg?raw=true" title="ReShade Addons" style="width:363px;height:468px;"/>
1. **Extract the *renodx-hitmanwoa.addon64* mod file into your *Hitman3/Retail* folder.** This folder will also have the Hitman3.exe file in it, but NOT the Launcher.exe file.
	- <details><summary><b>Pro Tip:</b> If you saw <i>renodx-hitmanwoa</i> instead of <i>renodx-hitmanwoa.addon64</i> then make sure you have <b>File name extensions</b> turned on in Windows Explorer: </summary><img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Guide-Generic-Images/View-File-Name-Extensions.jpg?raw=true" title="View File Extensions" style="width:472px;height:443px;"/>
1. **Install Special K:**
	- Install location doesn't matter. 
	- Without this installed the RenoDX mod won't work.
1. **Start the Special K game launcher, also known as SKIF:**
	1. You'll probably notice that Special K has automatically added some other games you already had installed.  
	1. If you do not see Hitman 3 in the list, then on the bottom left corner of the Special K launcher click **Add Game**
	1. Browse to your Hitman 3 / Hitman: World of Assassination install folder and select Launcher.exe, NOT Hitman3.exe.
1. **Select Hitman 3 / Hitman: World of Assassination and click Play.**
	- <details><summary>Special K Launcher: </summary><img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Hitman3/SK-Hitman3.jpg?raw=true" title="SpecialK Hitman3" style="width:477px;height:255px;"/>
1. **Either within the game launcher's options or the in-game graphics options make sure *Display Mode* is set to *Exclusive Fullscreen***
1. **Once you start the game you should see both Special K and ReShade appear on the top portion of the screen:** 
	- <details><summary>How Speical K and ReShade appear when loading together: </summary><img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Guide-Generic-Images/SK-ReShade.jpg?raw=true" title="SK ReShade Startup" style="width:100%;height:100%;"/>
1. **If the ReShade UI stays up press the HOME key, then skip tutorial. Close the ReShade UI by pressing the HOME key again.**
1. **Press the CTRL + SHIFT + BACKSPACE keys at the same time to open the Special K in-game menu.**
1. **Within the Special K menu, click HDR, then check the box next to *Enable "Fake Fullscreen" Mode***
1. **Close the Special K menu by clicking the X on the top right of the menu.  Restart the game for the Fake Fullscreen mode to take effect.**
	- You'll need to start Hitman 3 with Special K each time you want to play it with the RenoDX mod

## Configuring White Point

1. **From the main menu select Options, then Graphics:**
	- <details><summary>Options menu: </summary><img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Hitman3/Hitman3-Options.jpg?raw=true" title="Hitman 3 Options" style="width:100%;height:100%;"/>
1. **Double check that Display Mode is set to Exclusive Fullscreen, otherwise the HDR setting won't appear.**
1. **Once you see the HDR menu, go into it and make sure HDR is enabled.**
1. **Go back to the Graphics options, and select Gamma Correction.**
1. **Open up the ReShade menu, and enable Lilium's HDR Analysis:**
	- If HDR isn't enabled then this shader will show as Lilium's SDR Analysis.
	- <details><summary>If the ReShade UI is too small, go into the ReShade settings tab, and then look for the **Global font** setting: </summary><img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Guide-Generic-Images/ReShade-Settings.jpg?raw=true" title="ReShade Font Settings" style="width:669px;height:964px;"/>
1. **With Lilium's HDR Analysis enabled, adjust the Gamma Correction. Whatever value is listed as the Max nits while inside the options menu is your WHITE POINT.**
	- Typical white point value is around 200-300 nits.  If you're not sure just leave the Gamma Correction at 1.00 which is about 200 nits.
	- <details><summary>White point adjustment: </summary></summary><img src="https://github.com/CreepySasquatch/HDRMods/blob/main/images/Hitman3/Hitman3-GammaCorrection.jpg?raw=true" title="White Point" style="width:960px;height:540px;"/>

## Configuring Peak Brightness

1. **Peak Brightness is configured via the Max Intensity slider within the game's HDR options.**
1. **Peak Brightness = Max Intensity multiplied by the Paper White value (in Nits) divided by 2.**
	- This is only a rough calculation and you'll want to use the HDR Analysis Tool while loaded into a destination to verify this value.  The maximum nits will obviously vary as you move the camera around so check it every so often and adjust the Max Intensity value as needed.
	- This calculation is ONLY for this specific Hitman 3 RenoDX mod (specifically the version released on June 28th, 2025).  This may change in a future update to this mod so pay attention to any updated notes in the mod description.

	
	
