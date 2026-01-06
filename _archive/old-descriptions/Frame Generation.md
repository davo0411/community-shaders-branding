:::center
[![Join the Discord](https://github.com/doodlum/nexusmods-widgets/blob/cs/CommunityShadersDiscordFancy.png?raw=true)](https://discord.gg/nkrQybAsyy)

![Community Shaders Official Addon](https://i.imgur.com/1FSEwwP.png)
:::

# Overview

This Community Shaders addon adds AMD FSR 3.1 Frame Generation and NVIDIA DLSS Frame Generation.

# Features

Frame Generation can up to double the framerate with significantly improved frame pacing, resulting in a much smoother, reliable experience.

- **NVIDIA DLSS Frame Generation** is added using the [Streamline Integration Framework](https://github.com/NVIDIAGameWorks/Streamline).
  - For DX11 compatibility, an older version of Streamline is used alongside a slightly outdated DLSSG DLL. Later versions of either plugins do not support DX11.
  - All included files are made and signed by NVIDIA, along with their corresponding licenses. You will not find them on the [NVIDIA DLSS DLLS](https://www.nexusmods.com/site/mods/866) page.
- **AMD FSR 3.1** is added through the [AMD FidelityFX™ SDK - AMD GPUOpen API](https://gpuopen.com/amd-fidelityfx-sdk/). It uses a custom-made DirectX 12 swap chain proxy.
  - The DLL is signed by AMD.

This feature automatically sets up optimizations similar to [SSE Display Tweaks](https://www.nexusmods.com/skyrimspecialedition/mods/34705). **Display Tweaks is not recommended**, but is still supported.

Frame Generation works best at _60fps interpolated to 120fps_. This ensures extremely reliable frame pacing which will feel better than higher, variable frame rates. 

- :yellow[**No Multi Frame Generation or Reflex 1/2 for now. NVIDIA has been informed, it is up to them to come up with a way to support it.**]
- :green[**AMD Anti-Lag 2 should be supported.**]

# Installation & Requirements

Frame Generation requires any GPU which supports DirectX 12. It is limited to 120hz+ monitors unless you force enable Frame Generation in-game

**The game must be in Windowed or Borderless Mode.**

1. Install [Community Shaders](https://www.nexusmods.com/skyrimspecialedition/mods/86492) and all it's requirements.
2. Install this mod below it.

If using [Reshade](https://www.reshade.me/):
- Rename the Reshade DLL from dxgi.dll/d3d11.dll to ReShade64.dll
- Community Shaders will load it and render it under the UI, before frame generation.

# Usage

- The Frame Generation type is automatically selected based on what is compatible.

# Compatibility

- [SSE Display Tweaks](https://www.nexusmods.com/skyrimspecialedition/mods/34705) is not recommended, but is still compatible.
- Does not support VR. VR uses spacewarp, which is better.
- Compatible with Reshade, see **Installation & Requirements** above.

# Contributors

- [doodlum](https://next.nexusmods.com/profile/doodlum): Primary contributor  
[![Support Me on Ko-Fi](https://github.com/doodlum/nexusmods-widgets/blob/main/Ko-fi_40px_60fps.png?raw=true)](https://ko-fi.com/doodlez) [![Become a patron](https://github.com/doodlum/nexusmods-widgets/blob/main/Patreon_40px.png?raw=true)](https://www.patreon.com/Doodlezoid)
- [PureDark](https://next.nexusmods.com/profile/PureDark): For information and help
- [FlayaN](https://next.nexusmods.com/profile/FlayaN): For linking Streamline to Community Shaders



# Source

[![GitHub](https://github-readme-stats.vercel.app/api/pin?username=doodlum&repo=skyrim-community-shaders&theme=github_dark&title-color=329cff&icon_color=ffd43b&bg_color=0d1117C0)](https://github.com/doodlum/skyrim-community-shaders)

# References

- [NVIDIAGameWorks/Streamline](https://github.com/NVIDIAGameWorks/Streamline): Streamline Integration Framework
- [GPUOpen-LibrariesAndSDKs/FidelityFX-SDK](https://github.com/GPUOpen-LibrariesAndSDKs/FidelityFX-SDK): The main repository for the FidelityFX SDK
