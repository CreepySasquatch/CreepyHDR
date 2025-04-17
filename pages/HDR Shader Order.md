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




## Notes

{% include callout.html type="important" content="Lilium's Tone Mapping shader is placed at the very end to prevent shaders from exceeding the maximum amount of nits your display can support.  Without this you will very likely end up with blown out highlights." %}

{% include callout.html type="warning" content="When using the HDR analysis shader make sure it is after every other enabled shader aka at the very bottom of your shader order, after Lilium's Tone Mapping.  In other words, you want it to see what you're seeing." %}

{% include callout.html type="tip" content="Shaders not compatible with HDR can either go before Lilium's Inverse Tone Mapper or Pumbo's AdvancedAutoHDR shader or you can place them in-between Soop's HDR converters.  Usually non-HDR shaders will look better when placed in-between the HDR converters because they will be modifying the game after it went through the SDR to HDR conversion and thus will be affecting a wider range of colors." %}

{% include callout.html type="note" content="Most, if not all, HDR compatible shaders that do not do any tonemapping on their own will work in both HDR and SDR.  If you are familiar with the general order of non-HDR shaders, that order should still be respected." %}

**Examples of HDR compatible shaders include but are not limited to:**

- MaxG2D's HDR Saturation
- MaxG2D's HDR Bloom
- MaxG2D's HDR Motion Blur
- Lilium's RCAS
- Lilium's CAS
- Lilium's Filmgrain