:::center
[![Join the Discord](https://github.com/doodlum/nexusmods-widgets/blob/cs/CommunityShadersDiscordFancy.png?raw=true)](https://discord.gg/nkrQybAsyy)

![Community Shaders Official Addon](https://i.imgur.com/1FSEwwP.png)
:::

# Overview

This Community Shaders addon casts shadows from clouds. Supports SE, AE, and VR.

This is a custom technique developed in a collaboration between [me](https://next.nexusmods.com/profile/ProfJack) and [doodlum](https://next.nexusmods.com/profile/doodlum). The cloud shadows are aligned with the sun, using the actual clouds system rather than a scrolling texture, meaning that when clouds cover it the player will be shrouded in darkness. Clouds are rendered from the perspective of the player and unprojected to cover the world, acting as an extremely fast approximation. The cloud shadows texture itself is rendered during the cubemap reflections rendering as a side effect, meaning that it has no additional draw calls. 

The cloud shadows are also used for volumetric lighting, meaning that godrays from the sun can be occluded too. Momentary breaks in the clouds during cloudy weather should be visually striking.

:::center
![Cloud Shadows Example](https://i.imgur.com/PyytBI6.gif)
:::

# Installation & Requirements

1. Install [Community Shaders](https://www.nexusmods.com/skyrimspecialedition/mods/86492) and all it's requirements.
2. Install this mod below it.

# Contributors

- [ProfJack](https://next.nexusmods.com/profile/ProfJack)
- [doodlum](https://next.nexusmods.com/profile/doodlum)  
[![Support Me on Ko-Fi](https://github.com/doodlum/nexusmods-widgets/blob/main/Ko-fi_40px_60fps.png?raw=true)](https://ko-fi.com/doodlez) [![Become a patron](https://github.com/doodlum/nexusmods-widgets/blob/main/Patreon_40px.png?raw=true)](https://www.patreon.com/Doodlezoid)

# Source

[![GitHub](https://github-readme-stats.vercel.app/api/pin?username=doodlum&repo=skyrim-community-shaders&theme=github_dark&title-color=329cff&icon_color=ffd43b&bg_color=0d1117C0)](https://github.com/doodlum/skyrim-community-shaders)
