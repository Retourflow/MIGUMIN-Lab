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
  记录多层 UI / 角色图片一起变透明时，为什么后面的图层会透出来、颜色会叠在一起，以及有哪些更自然的淡出和消失做法。

- [《终末地》3 渲 2 角色渲染与 Shader 通俗解释](./Unity/Endfield-3D-Toon-Rendering-and-Shader.md)  
  用比较简单的方式理解 3 渲 2 角色是怎么从普通 3D 模型变成二次元效果的，包括阴影、脸部、头发高光、描边和后期。

- [反光地面：Shader、反射、Roughness、Bump 与环境之间的关系](./Unity/Reflective-Floor-Shader-Reflection-Roughness-Bump.md)  
  解释反光地面为什么会反光，以及 Light、Roughness、Bump 和环境分别在控制什么，方便判断地面太亮、太像镜子或没有倒影时该检查哪里。

- [《终末地》雨雪天气与程序化 Mask](./Unity/Endfield-Weather-Procedural-Mask.md)  
  整理雨天和雪天材质是怎么做的：雨怎么让材质变湿，雪怎么判断积在哪里，以及怎么用 Normal、AO、Curvature 等数据自动生成 Mask。

---

<a id="ae"></a>

## AE

### Motion / Wallpaper

- [终末地 Perlica 动态壁纸](./AE/Wallpaper-Engine-Production.md)  
  记录这张 Perlica 动态壁纸的制作方法：用分形杂色、VR 色差、径向模糊和 Evolution 做出会流动的光束，并处理最终输出到 Wallpaper Engine 时的画幅和渲染问题。

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
