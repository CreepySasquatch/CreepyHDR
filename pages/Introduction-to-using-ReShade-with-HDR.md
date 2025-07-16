---
title: [Introduction to using ReShade with HDR]
type: 
summary: 
description: Introduction to using HDR with ReShade
sidebar: false
---

{% include callout.html type="note" content="This guide is more of a general overview. It won't give you all the
answers but will at least get you pointed in the right direction. For a
more thorough explanation of covered topics feel free to ask us in the
[HDR Wasteland Discord server](https://discord.com/invite/yRYASQrg8r)." %}

## What is HDR?

HDR stands for **H**igh **D**ynamic **R**ange. It allows for a wider
range of colors, increased contrast, and more detailed shadows and
highlights. It requires an HDR compatible display that is also capable
of showing HDR content. This last point is very important as some
monitors will say they are HDR / HDR10 compatible but aren't actually
able to show HDR content. Do your research before buying an HDR monitor
as they vary wildly in price, quality, and overall functionality.
Generally speaking, HDR will look better on an OLED display when
compared to a VA or IPS panel.

## What is a nit?

A nit is a unit of brightness, specifically measured as candelas per square meter (cd/m²).  It is important to know the maximum brightness value of your display when configuring HDR shaders, as this will often be used for shader settings that mention "target brightness" or "output brightness". 
You can find your display's maximum brightness value by looking up your display's spec sheet (literally Google ***display model*** spec sheet and it should be one of the first results).

{% include callout.html type="tip" content="It's common for display manufacturers to list the SDR and HDR maximum brightness separately.  
SDR brightness doesn't usually exceed 300 nits whereas HDR maximum brightness can be anywhere from 400 to over 1000 nits or possibly even higher."%}

## Does ReShade work with HDR?

Generally speaking, most ReShade shaders are not compatible with HDR;
however, you can get around that in a few different ways. In theory you
can get most shaders working with HDR but which method you'll need to
use can vary by game. If a game has the option to use different graphics
APIs then the methods can vary with those as well. These methods are
discussed below.

## HDR with ReShade Methods:

{% include callout.html type="note" content="Expect to do some experimenting to find which method works best for
your particular use case. There often isn't a best way to do things in
most situations." %}

{% include callout.html type="important" content="With the exception of Special K, games that use DirectX 9 or older
need to converted to DX11/12 or Vulkan to work with any of the methods
below; though it's still recommended even with Special K, it's just not
required." %}

- **Soop's scRGB / HDR10 Converters --** The only way to use ReShade
  with Native HDR or the popular RenoDX mods. Just place any shaders
  in-between the Before and After parts of the converter. You can use
  the converters alongside the various AutoHDR methods and inverse
  tonemappers as well. Just place Soop's converters after the inverse
  tonemapper. <https://github.com/smolbbsoop/smolbbsoopshaders>

- **AutoHDR Addon --** a Reshade addon that's used to convert a game
  from SDR to HDR. Must be used with one of the inverse tonemappers. Can
  also use in games that have native HDR, but you need to make sure HDR
  is disabled within the game's settings.
  <https://github.com/EndlesslyFlowering/AutoHDR-ReShade>

- **Lilium's DXVK --** a fork of DXVK that Lilium modified to give it
  HDR capabilities. Similar to the AutoHDR addon in that it's used to
  convert a game from SDR to HDR. Must be used with one of the inverse
  tonemappers and if a game has native HDR you should disable it.
  Converts a game's API to Vulkan which makes it useful for DX9 games.
  <https://github.com/EndlesslyFlowering/dxvk>

- **Lilium's Inverse Tonemapper --** shader that is used to convert the
  luminance range from SDR to HDR. Must be used alongside the AutoHDR
  addon, Lilium's DXVK, or Special K (when tonemap mode is set to Raw
  Framebuffer). 
  <https://github.com/EndlesslyFlowering/ReShade_HDR_shaders>

{% include callout.html type="note" content="Inverse Tone Mapper is sometimes abbreviated as **ITM**" %}

- **Pumbo's AdvanceAutoHDR --** shader that is an alternative to
  Lilium's Inverse Tonemapper but can also be used to modify native HDR
  as well. <https://github.com/Filoppi/PumboAutoHDR>

- **Special K --** a separate program that can either be run "globally"
  in its launcher form or "locally" when you place the renamed
  SpecialK32/64.dll into the game's installation folder (similar to how
  ReShade is installed when done manually). Can be used to modify a
  game's native HDR or convert an SDR game to HDR. Has its own built-in
  inverse tonemapper but can also be used with Lilium's inverse
  tonemapper or Pumbo's AdvancedAutoHDR shader.
  
  <details>
  <summary>More info on Special K:</summary>
	<ol>
	<ul>
    <li>Special K's pipeline remastering feature (OpenGL and DX11 only) is
    an advanced feature which allows the HDR remastering process to
    start earlier in the graphics pipeline (similar to RenoDX). In
    simple terms, it can make the final HDR output look better but isn't
    recommended for first-time users of Special K because of the
    additional steps it takes to get it configured.</li>

    <li>Recommend grabbing the latest version of the installer from the
    Special K Discord: <a href="https://discord.com/invite/specialk">https://discord.com/invite/specialk</a></li>

    <li>Special K gets updated often so I recommend turning on automatic
    updates. You can also grab updates from their Discord's
    nightly-builds channel.</li>

    <li>Special K is not compatible with most of Otis' camera tools but this
    will depend on the game it's being used in.</li>

    <li>Special K can also be used for much more than HDR but that's out of
    the scope of this quick overview.</li>
	</ul>
	</ol>
	</details>

### RenoDX

Uses ReShade to inject itself into a game (in the form of a ReShade
addon). RenoDX mods should be treated as native HDR, and as far as the
graphics rendering pipeline is concerned RenoDX **IS** native HDR.
RenoDX is the best way to experience HDR if you're not using any other
shaders. As mentioned earlier, you'll need to use Soop's HDR converters
if you want to use non-HDR shaders with RenoDX. List of all the
currently available RenoDX mods can be found here:
<https://github.com/clshortfuse/renodx/wiki/Mods>

## Taking and Sharing HDR Screenshots

{% include callout.html type="note" content="HDR PNGs will automatically tonemap to SDR when viewed on non-HDR
displays. Hardware acceleration must be turned on in Discord for HDR
PNGs to tonemap properly. Otherwise, they will need to be opened in
a web browser." %}

- **ReShade:** as of version 6.4, ReShade is capable of taking HDR
  screenshots in the HDR PNG format, which are compatible with Discord.

{% include callout.html type="important" content="ReShade's **save before and after images** screenshot feature will not work
when using one of the inverse tonemapping shaders because it will
disable the inverse tonemapper as well which will produce a
washed-out image in the before shot." %}

- **Special K** is able to take HDR screenshots in multiple HDR image
  formats including HDR AVIF, JXR, and HDR PNG.

- **SKIV (Special K Image Viewer)** is a handy tool can be used to
  properly view HDR images and see detailed information about the image.
  
   <details>
   <summary>More info on SKIV:</summary>
	<ol>
	<ul>
    <li>Convert HDR images to another HDR image type (such as JXR to HDR
    PNG) and export HDR images to SDR.</li>
    <li>Crop HDR images using by holding ctrl + left click, then select the
    area you want to keep, release the left click which will then save
    the cropped image to your clipboard, paste the image back into SKIV.</li>
	<li>Can take HDR screenshots which essentially makes it an HDR version
    of the Windows snipping tool.</li>
	<li>SKIV automatically comes with Special K when you install the latest
    version from the Discord. You'll find SKIV in the main Special K
    install directory.</li>
	<li>SKIV does not need Special K to function so if you have no interest
    in using Special K you can move SKIV.exe to its own folder, then
    uninstall Special K. I do recommend moving SKIV to a folder, and not
    just place the program on your desktop because it will automatically
    download any additional needed files that are required when saving
    an image to that particular file type. So you'll end up with more
    than just SKIV.exe in that folder.</li>
	</ul>
	</ol>
	</details>

- **Windows Game Bar** can take HDR screenshots in the JXR file format.

- **Nvidia Overlay** can take HDR screenshots in the JXR file format and can
  also record HDR video.

- **OBS** can capture HDR screenshots in the JXR file format and record HDR
  video.

  - OBS HDR setup guide:
    <https://www.reddit.com/r/IntelligentGaming2020/comments/x4s8h4/how_to_capture_record_hdr_high_dynamic_range/>

## Links to Helpful Resources

- **HDR Den Discord:** <https://discord.gg/R2Bt3uptw6>. This server is
  dedicated to all things HDR. Home to RenoDX, PumboAutoHDR, and
  Lilium's HDR ReShade shaders. This is a good place for asking about
  the technical details of HDR and for inquiring about what kind of HDR
  display you should get.

- **Special K Discord:** <https://discord.com/invite/specialk>. You can
  find the latest Special K updates here and support is also provided.
  If you're interested in the non-HDR aspects of Special K such as the
  various texture mod packs then this is the place to ask.

- **HDR Wasteland Discord:** <https://discord.com/invite/yRYASQrg8r>. A
  new server made by yours truly, CreepySasquatch. Dedicated to using
  ReShade with HDR and specializes in using non-HDR shaders with HDR.
  Home to Soop's collection of shaders and Creepy's HDR ReShade guides.
  If you're interested in using shaders such as RTGI or Filmdeck with
  HDR or you want to learn how to take better HDR screenshots then this
  is the Discord server for you.
  
- **ReShade Discord:** <https://discord.com/invite/PrwndfH>.  The official ReShade server.  
  If you have a question about ReShade that doesn't necessarily revolve around HDR then this is the place to go.  This is also the server to join if you're interested in making your own addons or shaders.
  Make sure to use the #help channel for any support questions.

- **Marty's Mods ReShade guides:** <https://guides.martysmods.com/>.
  Nice collection of general ReShade guides, but nothing specifically
  for HDR.

- **PC Gaming Wiki:** <https://www.pcgamingwiki.com/wiki/Home>. If you
  need help finding specific information about a game, such as what API
  it uses.

- **Special K Wiki**: <https://wiki.special-k.info/>. If you want to
  learn more about the various features Special K has to offer.

- **FRAMED Screenshot Guides**: <https://framedsc.com/basics.htm>. If
  you're interested in learning how to take better screenshots this is a
  good place to start. Nothing specifically for HDR but still a good
  resource nonetheless.
