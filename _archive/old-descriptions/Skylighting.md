:::center
[![Join the Discord](https://github.com/doodlum/nexusmods-widgets/blob/cs/CommunityShadersDiscordFancy.png?raw=true)](https://discord.gg/nkrQybAsyy)

![Community Shaders Official Addon](https://i.imgur.com/1FSEwwP.png)
:::

# Overview

This advanced Community Shaders addon simulates large scale world-space ambient occlusion. Supports SE, AE, and VR.

:::center
![Skylighting Example](https://i.imgur.com/z3hbgEm.gif)
:::

# Features

Skylighting, also known as **large-scale ambient occlusion**, is part of an extremely difficult set of rendering terms called [Global Illumination](https://www.youtube.com/watch?v=yEkryaaAsBU).

Skylighting creates a soft ambient shadowing effect under structures and dense woods, enhancing contrast and realism in areas without direct lighting, which is tied into every part of Community Shaders to achieve a significantly more advanced lighting model.

Rather than using existing rendering techniques we created our own from scratch, which is significantly more advanced than our original design goals. Out of every feature we have created, this is the most transformative.

## Comparison with ENB

People will know the phrase from ENBSeries so we used the same term, however the effects are implemented very differently. ENB uses the shadow map. This only works properly around midday and midnight. Any other time it will be broken because skylighting will shadow everything at an angle. ENB presets pretty much disable skylighting at sunrise and sunset because it covers the whole map in darkness.

- ENB only does skylighting from one direction. Community Shaders does skylighting from every direction.
- ENB skylighting is computationally expensive to do each frame. Community Shaders tries to spread out the computational cost over multiple frames which may result in infrequent frametimes as a side effect. In the future we might spread it out better.

:::center
![ENB Comparison](https://i.imgur.com/twOigw3.jpeg)

:small[Visualization of shadow-based and CS Skylighting at a low sun angle with a minimum ambient value of 0, not reflective of either in practical use.]
:::

## Wetness

When using [Wetness Effects](https://www.nexusmods.com/skyrimspecialedition/mods/112739), areas under cover will be dry. This means no puddles in sheltered areas. In the future this may be used for snow/frost effects.

:::center
![Wetness Example](https://i.imgur.com/9ia4gvI.gif)
:::

## Dynamic Cubemaps

Skylighting determines when objects are occluded from the sky. This prevents dynamic cubemaps from rendering sky reflections where they wouldn't naturally appear.

:::center
![Dynamic Cubemaps Example](https://i.imgur.com/N6esX0N.gif)
:::

## Water

Water gains similarly improved reflections, and as a bonus it also gets volumetric ambient lighting.

:::center
![Water Example](https://i.imgur.com/H3hJzog.gif)
:::

## Effects

Effects like fog and smoke get skylighting, which means they no longer glow in the dark.

:::center
![Fog Example](https://i.imgur.com/Yfx3YcG.gif)
:::

## Algorithm

**TL;DR**

﻿Baking visibility probes progressively in real time with rasterized unidirectional rays.

**Longer Read**

﻿At a rate of roughly 30 frames per second, it progressively averages directional shadows from different light angles, to approximate how ambient light is occluded by objects surrounding every location, and stores the information as spherical harmonics in a grid roughly centred at the camera. The occlusion info can then be (stochastically) interpolated for the use of **large scale ambient occlusion** and removing [wetness](https://www.nexusmods.com/skyrimspecialedition/mods/112739)﻿ under roofs.

Denoising is not required, however if using temporal anti-aliasing, FSR or DLSS, spatio-temporal blue noise will jitter the skylighting to blur it effectively for free.

:::center
![Algorithm Image](https://i.imgur.com/RkgbUEh.png)

:small[Diagram from [Large Scale Ambient Occlusion: Introduction | Dambuster Studios](https://www.dsdambuster.com/blog/lsao-part-1)]
:::

# Frequently Asked Questions

**How is it different from [SSGI](https://www.nexusmods.com/skyrimspecialedition/mods/130375)?**

- The ambient occlusion (AO) in SSGI﻿ is smaller-scale, screen-space and dynamic.
-  The AO from skylighting is **larger-scale**, doesn't depend on info in the screen, and won't change with camera movement. Only static objects (houses, trees, landscape, etc.) can occlude the light, and dynamic objects only receive the occlusion.
- Additionally, skylighting can affect **transparent objects and water**, and it is **disabled in interiors** because there is no sky.
- It is recommended to combine them both for the full effect, plus indirect light (IL) from SSGI which accounts for bounced light.

# Installation & Requirements

1. Install [Community Shaders](https://www.nexusmods.com/skyrimspecialedition/mods/86492) and all it's requirements.
2. Install this mod below it.
3. (Optional) Install [Screen Space Global Illumination](https://www.nexusmods.com/skyrimspecialedition/mods/130375). It is designed to be used with SSGI but it is not required.

# Compatibility

Compatible with everything.

Moving or toggling objects may create issues. There are no known issues yet but it is a possibility. Skylighting will try not to render occlusion for dynamic objects and will constantly update to mitigate this.

# Contributors

- [ProfJack](https://next.nexusmods.com/profile/ProfJack): Core algorithm
- [Doodlum](https://next.nexusmods.com/profile/doodlum): RE, blurring, fixes and random ideas  
[![Support Me on Ko-Fi](https://github.com/doodlum/nexusmods-widgets/blob/main/Ko-fi_40px_60fps.png?raw=true)](https://ko-fi.com/doodlez) [![Become a patron](https://github.com/doodlum/nexusmods-widgets/blob/main/Patreon_40px.png?raw=true)](https://www.patreon.com/Doodlezoid)
- [jonahex](https://next.nexusmods.com/profile/jonahex/mods): RE
- [FlayaN](https://next.nexusmods.com/profile/FlayaN): VR support

# Source

[![GitHub](https://github-readme-stats.vercel.app/api/pin?username=doodlum&repo=skyrim-community-shaders&theme=github_dark&title-color=329cff&icon_color=ffd43b&bg_color=0d1117C0)](https://github.com/doodlum/skyrim-community-shaders)

# References

- [NVIDIAGameWorks/SpatiotemporalBlueNoiseSDK](https://github.com/NVIDIAGameWorks/SpatiotemporalBlueNoiseSDK)
