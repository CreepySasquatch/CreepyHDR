---
title: [HDR Shader Order]
type:
summary:
description: HDR Shader Order
sidebar: false
---

## SDR to HDR Conversions
- Requires the AutoHDR addon, Lilium's DXVK, or Special K (set tonemap mode within SK to Raw Framebuffer)
- Requires either Pumbo's AdvancedAutoHDR shader OR Lilium's Inverse Tone Mapper shader

{% include callout.html type="warning" content="Do not use the AutoHDR addon from MajorPainTheCactus as it's outdated.  Use the version from EndlessFlowering (Lilium) instead.  **Link:** <https://github.com/EndlesslyFlowering/AutoHDR-ReShade>" %}

**Simple version for those new to ReShade:**

```
TOP OF SHADER ORDER
All other shaders
Either Lilium's Inverse Tone Mapper or Pumbo's AdvancedAutoHDR
BOTTOM OF SHADER ORDER
```


**More advanced version that can lead to a better end result:**

```
TOP OF SHADER ORDER
Shaders not compatible with HDR can go here
Either Lilium's Inverse Tone Mapper or Pumbo's AdvancedAutoHDR
scRGB Converter (Before) / HDR10 Converter (Before)
Place most shaders not compatible with HDR here
scRGB Converter (After) / HDR10 Converter (After)
Lilium's Tone Mapping
BOTTOM OF SHADER ORDER
```

{% include callout.html type="tip" content="It's not recommended to go above 600 nits when entering the peak brightness in Inverse Tone Mapping shaders because this can lead to blown out highlights.  If your display goes above 600 nits, enter the actual peak brightness value in Lilium's Tone Mapping shader." %}

## Native HDR / RenoDX / Luma

**If using ReShade with either native HDR or a mod that adds native HDR to a game such as RenoDX or Luma:**

```
TOP OF SHADER ORDER
scRGB Converter (Before) / HDR10 Converter (Before)
Shaders not compatible with HDR go here
scRGB Converter (After) / HDR10 Converter (After)
Lilium's Tone Mapping / AdvancedAutoHDR
BOTTOM OF SHADER ORDER
```

## Shader Order Tips

- Lilium's Tone Mapping shader is placed at the bottom to prevent shaders from exceeding the maximum amount of nits your display can support.  It's also used to help prevent overblown highlights.  
- Lilium's HDR Analysis shader should always go at the very bottom of your shader order, even after the tone mapper.  The only exception to this would be if you want to see what the output looks like at different points of your ReShade preset.  A good example would be comparing the output after the inverse tone mapper vs after the tone mapper.  Just remember that any shader that is below the HDR analysis shader won't be seen by it.

## Soop's HDR Converters Additional Info

**Download link:** <https://github.com/smolbbsoop/smolbbsoopshaders>

**Soop's HDR Converters introduces a ReShade global preprocessor command *_SOOP_COLOUR_SPACE* that will attempt to force ReShade to compile the shaders for the specified colorspace.**

**_SOOP_COLOUR_SPACE supported values:**  
1. *SOOP_SRGB*
1. *SOOP_SCRGB*
1. *SOOP_HDR10*

This is really handy for those weird situations when HDR shaders refuse to compile because they think the game is in SDR but the AutoHDR addon or Lilium's DXVK is present.

{% include callout.html type="note" content="Both **colorspace** and **colourspace** are correct spellings of the word but only **colourspace** works as the global preprocessor command.  *Colorspace* is more popular in America, while *colourspace* is more prominant in the UK." %}