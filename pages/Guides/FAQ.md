---
title: [FAQ]
type:
summary:
description: Frequently asked questions about using ReShade with HDR
sidebar: false
---

## How do I fix this weird pink image? 

#### All my screenshots look like this:  

{% include image.html file="/Guide-Generic-Images/AutoHDR addon without having HDR.png" max-width="512px" %}

**Solution:** You're probably using the AutoHDR addon when you don't have HDR enabled in Windows or your display doesn't support HDR.  Remove the AutoHDR addon either by manually deleting it from the game folder or running the ReShade installer again > Select "Update ReShade and Effects" > Click "Skip" on the shader selection screen > On the addon screen DO NOT select any addons unless you know you need them. 

{% include callout.html type="tip" content="This often happens when picking all addons during the ReShade installation process.  Unlike shaders, you never want to pick any addons unless you know what they're used for." %}


## ENB Compatibility

**There are two very important things to remember when trying to use ENB with HDR:**

1. RenoDX / NativeHDR is rendered BEFORE ENB which is rendered BEFORE ReShade.
1. ENB is only designed to work within the SDR colorspace and any HDR rendered before it, aka RenoDX or native HDR, will have it's output effectively clamped to SDR when ENB is active.
	* Try using Lilium's HDR Analysis and you'll see exactly what I mean.  You'll notice the nits drop drastically when ENB is enabled, especially in bright scenes.  
	* ENB's menu will also be hard to read when using it with RenoDX.  When using ENB with AutoHDR instead of RenoDX, you won't have this issue.

So by it's very nature, ENB does not get along with HDR very well.  

The easiest way to work around this is by using a post-processing form of HDR, aka AutoHDR, typically in the form of the AutoHDR addon alongside an inverse tonemapping shader.  

The result won't technically be as color accurate compared to using RenoDX without ENB, but if you want have any sort of HDR that works with ENB then this will be your best solution.  


## Why would I want to use AutoHDR over RenoDX?

The whole purpose of using RenoDX over AutoHDR is to get the game to have proper HDR that is at the game engine level and not just a post process effect.  

However, because ENB is taking away this benefit by clamping the RenoDX output to SDR, then there's really no downside to using the AutoHDR addon or Special K to apply HDR after ENB.
* By using AutoHDR the ENB UI will appear as it should so you can actually use the menu, and you're further enhancing the ENB effect by applying HDR to it as well.  
* If you like to use other ReShade effects on top of it then it also becomes a lot easier because you know when the HDR is being applied when compared to ENB and the other ReShade shaders that you're using.

What it comes down to is if you're more concerned with having the best HDR **OR** if you want to use the benefits that ENB provides such as better lighting and parallax textures.
Also, if you're going to be modding your game to the point where you're replacing textures, adding lighting mods, ENB, ReShade, and so on, then the difference between using RenoDX and AutoHDR is probably going to be minor at best.

In this situation though, it's really up to you to decide what looks best and what kind of look you're wanting.  


## FakeHDR Shaders

**I'm going to say this once and only once...FakeHDR IS NOT HDR!!!**
There is a reason why it's called **FAKE** HDR.  FakeHDR still works within the SDR colorspace.  It's basically just a fancy way of saying it increases the contrast to give it an "HDR" look.
So beware of ReShade presets that claim to add HDR or be an HDR preset when in reality it's just FakeHDR.  If you open the ReShade preset file in a text editor you'll see FakeHDR written in the shader list if it's present.  

{% include callout.html type="note" content="This FakeHDR section was mainly added to poke fun at the FakeHDR shaders that exist.  I'm well aware some do more than just add contrast, and if you want to use them go for it.  However, if you decide to publish a preset on Nexus Mods using a FakeHDR shader, please don't call it an HDR preset." %}