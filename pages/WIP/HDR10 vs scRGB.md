## HDR10 vs scRGB

**Why does HDR10 seem to work better with non-HDR shaders in comparison to scRGB?**

HDR10 is encoded in such a way that 0 nits is a 0 and 10,000 nits is a 1.

<!-- sRGB's luminance scale is also encoded from 0 to 1 with 0 being the darkest black and 1 being the whitest white.  -->  

scRGB uses the same color primaries as sRGB but it gets its additional colors by using luminance values lesser than 0 and greater than 1 (-0.5 to 7.49).  So in the scRGB colorspace, any colors with a luminance value of 0 to 1 are existing colors within the sRGB colorspace.


Because HDR10 works with numbers in the same way most non-HDR shaders are comfortable with, this results in better compatibility.  
The opposite is true with scRGB because the numbers it uses to describe luminance can fall outside of the normal range used by sRGB. 
This is why some ReShade shaders appear to be compatible with HDR when in reality they are not, or at least not fully.  

**HDR10**

So something I did not mention in my HDR Shader Order guide is that if a game is using HDR10 or if you're using a mod that adds HDR10 native HDR such as RenoDX, 
then you might not need any other shader to make those SDR shaders compatible with HDR.  However, I still highly recommend putting an HDR tonemapper at the end of your shader order, especially when using shaders that effect the peak brightness as it will help keep them under control.
The reason I did not mention this in that guide though is because this can vary by shader, game or HDR method you're using.  I still recommend using Soop's HDR converters with HDR10, but now you know those aren't always necessary. 

- Typically most native HDR is going to be HDR10 and some games, such as Cyberpunk 2077, will even allow you to choose HDR10 or scRGB.
- HDR10 is sometimes referred to as HDR10 PQ, specifically in the case of Cyberpunk 2077, compared to scRGB which is referred to as HDR10 scRGB

**scRGB**

scRGB uses the same core color primaries as sRGB (SDR) and thus can be a better candidate when applying HDR as a post-processing effect (AutoHDR) to a game that doesn't natively support HDR. 
However, as mentioned before, this benefit only helps when converting a game from SDR to HDR but it's actually worse for compatiblity as far as ReShade shaders are concerned.  
scRGB is going to be the real test for shaders that claim to be compatible with HDR.  There is no shortcut or exception with scRGB, you must use one of the techniques listed in my HDR Shader Order guide or else you're going to run into issues.
  