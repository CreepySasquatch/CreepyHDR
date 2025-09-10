---
title: [ReShade Preset Guide]
type: 
summary: 
description: Introduction to using HDR with ReShade
sidebar: false
---

## SDR Shader Order (aka, normal ReShade shaders)

{% include callout.html type="important" content="Remember that shaders are rendered from TOP to BOTTOM.  Whatever shader is on top will be affected by every other shader below it and vice-versa." %}
 
1. Any shaders that explicitly say to place them on top of the shader order, such as Immerse Launchpad or Zenteon Framework.  Do not put these inside of Soop's HDR converters.  
1. Ambient Occlusion, Ray Tracing, and Global Illumination shaders
1. Bloom and Fog shaders
1. Color grading shaders should generally go after AO, RT, GI, Bloom, and Fog shaders.  However; that being said, it's often fun to combine a few of them to see what happens when placed before and after the other types of shaders.
1. Sharpening, Anti-Aliasing, and Depth of Field shaders
1. Image correcting shaders such as Deband or Denoise, as well as any lens / dirt shaders like Film Grain or Lens Flare, should be placed toward the bottom. This would also apply to shaders that apply borders or cropping guides.

<a href="https://imgflip.com/i/a59obk"><img src="https://i.imgflip.com/a59obk.jpg" title="made at imgflip.com"/></a>