<table>
  <tr>
    <td width="230" align="center" valign="middle">
      <img src="./assets/migumin-mascot.webp" width="180" alt="MIGUMIN chibi assistant" />
    </td>
    <td align="left" valign="middle">
      <img src="https://readme-typing-svg.herokuapp.com?font=Cascadia+Code&weight=700&size=22&pause=1000&color=9ED7A7&center=false&vCenter=true&width=540&lines=Let%27s+learn+and+improve+together~" alt="Let's learn and improve together~" />
    </td>
  </tr>
</table>

<p align="center">
  <a href="https://github.com/Retourflow"><b>PROFILE</b></a> ·
  <a href="#map"><b>MAP</b></a> ·
  <a href="#unity"><b>UNITY</b></a> ·
  <a href="#ae"><b>AE</b></a>
</p>

> **Core:** document what I actually learn and understand.  
> This repository is organized as **column → article**, not as a daily study diary.

<a id="map"></a>

## Map

| Column | Area | Articles |
| --- | --- | ---: |
| [UNITY](#unity) | Rendering / UI / NPR / Materials / Weather | 4 |
| [AE](#ae) | Motion / Wallpaper | 1 |

---

<a id="unity"></a>

## UNITY

### Rendering / UI

- [CanvasGroup 与透明渲染](./Unity/CanvasGroup-Alpha-Rendering.md)  
  理解多层 UI / 角色图层在同时改变 Alpha 时为什么会互相显形、叠色，以及 CanvasGroup、渲染顺序、RenderTexture、Dissolve / Dither Fade 等方案之间的区别。

- [《终末地》3 渲 2 角色渲染与 Shader 通俗解释](./Unity/Endfield-3D-Toon-Rendering-and-Shader.md)  
  从普通 3D 模型出发，理解 Toon Shading、Ramp、Face SDF、头发高光、Mask、描边、Render Pass 与后期如何共同把角色塑造成二次元风格。

- [反光地面：Shader、反射、Roughness、Bump 与环境之间的关系](./Unity/Reflective-Floor-Shader-Reflection-Roughness-Bump.md)  
  梳理 Light、Normal、Shader、Mask、Roughness、Bump 与 Environment 的分工，并理解低 Roughness 地面为什么会反光、为什么还需要微弱 Bump 和环境内容来形成真实倒影。

- [《终末地》雨雪天气与程序化 Mask](./Unity/Endfield-Weather-Procedural-Mask.md)  
  从全局天气参数出发，理解 Wetness、Snow Layer 与程序化 Mask 如何驱动角色、地面和建筑对雨雪作出不同响应，并延伸到 Dust、Edge Wear 与反射系统。

---

<a id="ae"></a>

## AE

### Motion / Wallpaper

- [终末地 Perlica 动态壁纸](./AE/Wallpaper-Engine-Production.md)  
  使用线性分形杂色、三层 VR 色差、径向模糊与 Evolution 关键帧制作动态光束，并记录从 AE 合成到 Wallpaper Engine 发布时的画幅与输出处理。

  **Published work:** [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=3804142795)

---

### Repository structure

```text
MIGUMIN-Lab/
├── README.md
├── assets/
├── Unity/
│   ├── CanvasGroup-Alpha-Rendering.md
│   ├── Endfield-3D-Toon-Rendering-and-Shader.md
│   ├── Reflective-Floor-Shader-Reflection-Roughness-Bump.md
│   └── Endfield-Weather-Procedural-Mask.md
└── AE/
    └── Wallpaper-Engine-Production.md
```

New columns are added only when there is real study content to place inside them.
