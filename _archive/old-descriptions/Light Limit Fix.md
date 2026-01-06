:::center
[![Join the Discord](https://github.com/doodlum/nexusmods-widgets/blob/cs/CommunityShadersDiscordFancy.png?raw=true)](https://discord.gg/nkrQybAsyy)

![Community Shaders Official Addon](https://i.imgur.com/1FSEwwP.png)
:::

# Overview

This Community Shaders addon removes limits on the number of lights, adds particle lights, contact shadows, and more.

This project is the result of months of work on Community Shaders and [my](https://next.nexusmods.com/profile/doodlum) own personal journey into learning more advanced C++, DirectX 11 and HLSL programming, and collaboration via GitHub. This release would only have been possible with the help of [alandtse](https://next.nexusmods.com/profile/alandtse) who went above and beyond to support not just VR, but to improve Community Shaders in so many ways. [Nukem](https://next.nexusmods.com/profile/Nukem) was a major contributor by documenting major parts of the renderer and offering additional support. [Jonahex](https://github.com/Jonahex) provided the base for Community Shaders. [powerofthree](https://next.nexusmods.com/profile/powerofthree) reversed the particles which means particle lights were only possible without their major contributions to CommonLibSSE.

# Features

:yellow[**Please note:** The shadow limit is not yet unlocked.]

- Custom **clustered shading** implementation for high-performance, scalable lighting. **Starfield uses this too!**
- **Unlimited light sources** such as torches and magic lights.
- **Full support for "ENB light" particle lights.**
- **Extended particle lights system** via configuration files.
- Particle lights affect **NPC detection.**
- **Contact shadows** for all lights.
- High-performance lighting for **grass**.
- Full **VR support**.

## Clustered Shading

Clustered shading is the magic which makes this project possible. This is what lets us have completely **bug-free, scalable lights**, to achieve a **true light limit fix** and **optimized particle lights**. In the _Particle Lights_ section, the benefits of this system will become more apparent. If you would like to learn about the benefits of clustered shading, you can read an intuitive article here: [A Primer On Efficient Rendering Algorithms & Clustered Shading](http://www.aortiz.me/2018/12/21/CG.html)

:::center
![Cluster Shading Example](https://i.imgur.com/j7TpuOe.png)
:::

Here is a visualization of lights handled by clustered shading when using [ELFX Shadows](https://www.nexusmods.com/skyrimspecialedition/mods/63790). The red squares indicate where the light limit was reached. None of these lights now contribute to the light limit, they are unlimited.

Clustered shading was implemented based on advice from [mwilsnd / Ultra](https://next.nexusmods.com/profile/mwilsnd), the GitHub projects [pezcode/Cluster](https://github.com/pezcode/Cluster) and [mateeeeeee/Adria-DX11](https://github.com/mateeeeeee/Adria-DX11), and the presentation [Practical Clustered Shading](https://www.humus.name/Articles/PracticalClusteredShading.pdf).

## Unlimited Dynamic Lights

Expect all torches, projectiles, hazards and exterior lights to have **no restriction**. A lot of lights in interiors are still not fixed, but will now **no longer conflict** with any dynamically placed lights.

## Unlimited Magic Lights

The limit of only 4 magic lights has been increased to 2,147,483,647. Now, every actor in the game can cast a light without any restriction. In this example, [Luminous Atronachs](https://www.nexusmods.com/skyrimspecialedition/mods/27732) is used.

:::center
![Unlimited Magic Lights Example](https://i.imgur.com/QwcC8rS.jpg)
:::

## Particle Lights

Particle lights are designed to be fully backwards-compatible with "ENB light" meshes by using reversed information about the renderer to reconstruct the light colour on the CPU to create true light sources which can be used in the clustered shading system, and detected by NPCs.

This means that **any mod which offers "ENB light" is compatible with the Light Limit Fix**, such as the mods [ENB Light](https://www.nexusmods.com/skyrimspecialedition/mods/22574?tab=description), [ENB Lights For Effect Shaders](https://www.nexusmods.com/skyrimspecialedition/mods/56362), and the [Rudy102 "ENB Light" series](https://next.nexusmods.com/profile/rudy102/mods?gameId=1704).

Due to how these lights were designed, they have numerous **benefits** over the ones provided by "ENB":

- Uses clustered shading over deferred shading to be much more scalable. 
- True **specular lighting** so that **metallic** surfaces are lit correctly, as well as **hair**.
- Supports **parallax shadows**.
- **Transparent** objects such as glass and [Blended Roads](https://www.nexusmods.com/skyrimspecialedition/mods/8834) can receive lighting from particle lights.
- **First-person meshes** can emit light.
- Disables rendering particle light meshes to completely eliminate overdraw, **massively increasing performance**.
- No FOV issues or distortion.
- No false-positive lights, e.g. white flickering torches.
- No restriction on radius, lights can be of any size.

The Light Limit Fix also contains a **cool addition**: They can be **detected by NPCs** for stealth and gameplay purposes!

:::center
![Soulgems and Tables Example](https://i.imgur.com/5KpDuaF.gif)
:::

Particle lights were implemented based on the documentation [A Guide to Skyrim Particle Systems](https://www.nexusmods.com/skyrimspecialedition/articles/1391) and ENB Complex Lights and information provided by [Rudy102](https://next.nexusmods.com/profile/rudy102) and [fadingsignal](https://next.nexusmods.com/profile/fadingsignal).

## Contact Shadows

:yellow[**Contact Shadows are disabled by default.**]

**Every light in the game** can now cast small shadows in screen-space.

Contact shadows are designed to have the **lowest performance cost possible**, but are completely smooth when TAA or similar is used, by using temporal accumulation.

:::center
![Contact Shadows Example](https://i.imgur.com/YYbahvk.gif)
:::

## VR Support

**VR is fully supported without compromise**. Please note that there may be a larger performance impact in VR.

## Light Limit Visualization

:yellow[To enable visualizations you must add the shader define **LLFDEBUG** in the advanced settings menu.]

3 different options for **visualizing lights** are offered:
- Visualize the light limit; Red when the "strict" light limit is reached (portal-strict lights).
- Visualize the number of strict lights.
- Visualize the number of clustered lights.

# Installation & Requirements

1. Install [Community Shaders](https://www.nexusmods.com/skyrimspecialedition/mods/86492) and all it's requirements.
2. Install this mod below it.

# Contributors

- [doodlum](https://next.nexusmods.com/profile/doodlum): Responsible for the original implementation of all listed features outside of VR.  
[![Support Me on Ko-Fi](https://github.com/doodlum/nexusmods-widgets/blob/main/Ko-fi_40px_60fps.png?raw=true)](https://ko-fi.com/doodlez) [![Become a patron](https://github.com/doodlum/nexusmods-widgets/blob/main/Patreon_40px.png?raw=true)](https://www.patreon.com/Doodlezoid)
- [alandtse](https://next.nexusmods.com/profile/alandtse): VR support, refactoring, bug fixes, miscellaneous improvements.
- [Nukem](https://next.nexusmods.com/profile/Nukem): Documenting the renderer, additional support.
- [jonahex](https://github.com/Jonahex): Original RE of lighting and grass shaders, portal strict lighting support.
- [powerofthree](https://next.nexusmods.com/profile/powerofthree): RE of particles, contributions to CommonLibSSE.
- [rudy102](https://next.nexusmods.com/profile/rudy102) and [fadingsignal](https://next.nexusmods.com/profile/fadingsignal): Information about particle lights.
- [mwilsnd / Ultra](https://next.nexusmods.com/profile/mwilsnd): Suggestions and feedback about clustered shading.

# Source

[![GitHub](https://github-readme-stats.vercel.app/api/pin?username=doodlum&repo=skyrim-community-shaders&theme=github_dark&title-color=329cff&icon_color=ffd43b&bg_color=0d1117C0)](https://github.com/doodlum/skyrim-community-shaders)

# References

- [A Primer On Efficient Rendering Algorithms & Clustered Shading](http://www.aortiz.me/2018/12/21/CG.html)
- [Practical Clustered Shading](https://www.humus.name/Articles/PracticalClusteredShading.pdf)
- [pezcode/Cluster](https://github.com/pezcode/Cluster)
- [mateeeeeee/Adria-DX11](https://github.com/mateeeeeee/Adria-DX11)
- [Turbo, An Improved Rainbow Colormap for Visualization – Google Research Blog](https://blog.research.google/2019/08/turbo-improved-rainbow-colormap-for.html)
- [Screen space shadows](https://panoskarabelas.com/posts/screen_space_shadows/)
- [A Guide to Skyrim Particle Systems and ENB Complex Lights](https://www.nexusmods.com/skyrimspecialedition/articles/1391)
