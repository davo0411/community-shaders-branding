:::center
[![Join the Discord](https://github.com/doodlum/nexusmods-widgets/blob/cs/CommunityShadersDiscordFancy.png?raw=true)](https://discord.gg/nkrQybAsyy)
:::

# Overview

- **Unified** Shader Cache with fast multi-threaded compilation to a Disk Cache for instant start-up.
- **Asynchronous** shader compilation for in-game shader hot-reloading in a second.
- **Direct access** to the game through SKSE and CommonLibSSE-NG.
- **In-game menu** with tips, powered by ImGui.
- Designed for **speed** and **reliability**.
- Fixes **bugs**.
- **New features** for mod authors.
- **VR** support.
- **Open Source** - [GPL-3.0](https://github.com/doodlum/skyrim-community-shaders#license)﻿. Community can add features and maintain without worry it'll go closed source.

# Features

- Significantly improved performance of rendering terrain.
- Fixed incorrect normal-mapping on environment mapping and multi-layer parallax.
- Fixed green reflections on water.
- Fixed TAA on VR lighting shaders jittering in the right eye.
- Included [Sky Reflection Fix](https://www.nexusmods.com/skyrimspecialedition/mods/110604).
- Fixed screenspace reflections performance issues and artefacts.
- Improved screenspace reflections quality.
- Fixed water refraction looking incorrect.
- Fixed objects glowing in the dark. Better than [Fixed Mesh Lighting](https://www.nexusmods.com/skyrimspecialedition/mods/53653).
- Improved water reflections.
- Improved screenspace reflections.
- Improved subsurface scattering.
- Improved grass and tree LOD lighting.
- Fixed shadow seams.
- HQ shadows.
- Fixed normal map blending on characters.
- Fixed water blending.
- Fixed eye adaptation black screen.
- Fixed double sided object shading.
- Force disabled the "improved" snow shader.
- Force disabled the "image based lens flares" shader.
- Unlocked internal HDR rendering.
- Water reflections, SSR, and Volumetric Lighting for VR.
- Shadows for water shaders.
- Shadows for transparent objects such as eyes.
- DLAA and FSR 3.1 Native AA support.
- Renderpass limit fix.
- [Physically Based Rendering](https://www.nexusmods.com/skyrimspecialedition/articles/9414).
- [Extended Materials﻿](https://www.nexusmods.com/skyrimspecialedition/articles/9413).
- [Dynamic Cubemaps﻿](https://www.nexusmods.com/skyrimspecialedition/articles/9412).
- And more...﻿

## Shader Cache

The Shader Cache is the collection of compiled shaders which replace the vanilla shaders at runtime. Clearing the shader cache will mean that shaders are recompiled only when the game re-encounters them. This is only needed for hot-loading shaders for development purposes.

## Disk Cache

The Disk Cache is a collection of compiled shaders on disk, which are automatically created when shaders are added to the Shader Cache. If you do not have a Disk Cache, or it is outdated or invalid, you will see "Compiling Shaders" in the upper-left corner. The window will not freeze but you will be unable to interact with the game until this completes. After it has completed upon reloading the game you will not see this again, and there should be no delay.

This Disk Cache is located in **Data/ShaderCache**. Delete this folder to wipe it.

:::spoiler
![IMG](https://i.imgur.com/uUynO09.png)
:::

# Installation & Requirements

- Skyrim 1.5.97, VR, or the latest Skyrim version on Steam or GOG.
- An **:green[NVIDIA]**, **:red[AMD]**, or **:blue[Intel ARC]** GPU. 
Non-ARC Intel GPUs are *not* supported.
- SE/AE - [Address Library for SKSE Plugins](https://www.nexusmods.com/skyrimspecialedition/mods/32444)
- VR - [VR Address Library for SKSEVR](https://www.nexusmods.com/skyrimspecialedition/mods/58101)

# Usage

To access the menu, press the **END** key.

# Compatibility

- **:red[Not compatible with ENB. This mod disables all features if ENB is present, otherwise the game will crash.]**
- Not compatible with Shader Tools (Parallax Fix, ShaderTools Updated). **:red[Delete SSEShaderTools.dll and ShaderTools.dll.]**
- Included and therefore redundant: [Sky Reflection Fix](https://www.nexusmods.com/skyrimspecialedition/mods/110604).
- If using ReShade, use the add-on support version, and rename the dxgi.dll/d3d11.dll to ReShade64.dll.

# Contributing

This is a community project, which means any (well, most) contributions are welcome. Check out our [GitHub](https://github.com/doodlum/skyrim-community-shaders) and [Discord server](https://discord.gg/nkrQybAsyy) to get involved.

# Source

[![GitHub](https://github-readme-stats.vercel.app/api/pin?username=doodlum&repo=skyrim-community-shaders&theme=github_dark&title-color=329cff&icon_color=ffd43b&bg_color=0d1117C0)](https://github.com/doodlum/skyrim-community-shaders)

- [CommonlibNG](https://github.com/alandtse/CommonLibVR/tree/ng)

# Credits

# Contributors

- [Nukem](https://www.nexusmods.com/users/4995023) for the original RE of game shaders, rendering, and help.
- [aers](https://www.nexusmods.com/users/2025634) for additional RE and help.
- [Jonahex](https://github.com/Jonahex) for TruePBR, RE, the original shader cache, and help.
- [Doodlum](https://next.nexusmods.com/profile/doodlum) for maintenance of the CS repo, and being the main developer of the project.
- [ffarrell17](https://nexusmods.com/users/24095639) for UI-related work.
- [ProfJack](https://next.nexusmods.com/profile/ProfJack) for glints in TruePBR, their UI overhaul and additional changes.
- [alandtse](https://nexusmods.com/users/95120793) for numerous improvements and VR support, significant contributions to backend systems.
- [FlayaN](https://next.nexusmods.com/profile/FlayaN) for UI, numerous improvements and VR support.
- [ceejbot](https://nexusmods.com/users/60096776) for build system improvements.
- [LaoBro](https://nexusmods.com/users/37300915) for minor contributions and ideas.
- [Jiaye](https://next.nexusmods.com/profile/jiayev) for feature work and optimisations.
- [davo0411](https://next.nexusmods.com/profile/Davo0411) for feature work and UI improvements, nexus redesign.
- [soda](https://next.nexusmods.com/profile/oGSoda) for UI improvements.
- [sicsix](https://next.nexusmods.com/profile/sicsix1) for feature work and optimisations.
- [Duke Skyloafer](https://next.nexusmods.com/profile/dukeskyloafer) for logo design & Nexus mod page updates.