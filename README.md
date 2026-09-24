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
| [UNITY](#unity) | Rendering / UI / NPR / Materials / Weather | 5 |
| [AE](#ae) | Motion / Wallpaper | 1 |

---

<a id="unity"></a>

## UNITY

### Rendering / UI

- [CanvasGroup 与透明渲染](./Unity/CanvasGroup-Alpha-Rendering.md)  
  这篇是我在研究角色淡出时整理出来的。原本只是觉得“把所有图层一起调透明就行”，后来才发现多层图片会互相透出来、叠色。最后把一个问题理清了：多层 UI / 角色图一起淡出时，问题不只是透明度本身，还和图层顺序、混合方式以及渲染流程有关，所以有时候应该用 Dissolve、Dither Fade 或 RenderTexture，而不是单纯把 Alpha 一起往下拉。

- [《终末地》3 渲 2 角色渲染与 Shader 通俗解释](./Unity/Endfield-3D-Toon-Rendering-and-Shader.md)  
  这篇算是我真正开始看懂 3 渲 2 的一篇笔记。以前更多是在看“效果好不好看”，整理完以后开始能分清阴影、脸部、头发高光、描边和后期分别在做什么。也理清了我之前最容易混在一起的问题：3 渲 2 不是一个单独的 Shader 效果，而是模型、贴图、光照、Mask、Render Pass 和后期一起工作的结果。

- [反光地面：Shader、反射、Roughness、Bump 与环境之间的关系](./Unity/Reflective-Floor-Shader-Reflection-Roughness-Bump.md)  
  这篇是我折腾反光地面时留下的笔记。过程中把 Light、Roughness、Bump 和环境之间的关系慢慢理顺了。最后主要理清了几个一直容易混的问题：Roughness 决定反射有多散，Bump 只是扰动表面，不负责“制造反射”；Shader 决定地面有多会反光，而环境里有没有真正可被反射的东西，才决定最后能不能看到倒影。

- [《终末地》雨雪天气与程序化 Mask](./Unity/Endfield-Weather-Procedural-Mask.md)  
  这篇是从《终末地》的雨雪效果一路整理下来的。最有意思的是发现雨、雪、灰尘和边缘磨损虽然看起来完全不同，但背后其实都可以用已有数据去生成 Mask。最后把“程序化 Mask 到底是什么”这件事理清了：Mask 不一定是一张手画的黑白图，它本质上只是 0～1 的权重，可以直接由 Normal、AO、Curvature、Roughness、Metallic、Noise 等数据算出来，再去决定雪、灰尘、湿润或磨损应该出现在哪里。

- [AO：从“角落为什么会变暗”到 Shader 里的实际用法](./Unity/AO-Ambient-Occlusion-Shader.md)  
  这篇是我把 AO 单独拎出来重新整理的一篇。之前总会把 AO、普通阴影和灰尘混在一起，看到角落变暗就很容易理解成“这里比较脏”。整理完以后终于理清了：AO 说的是周围空间有多封闭、环境光有多难进去；它本身不是灰尘，也不是普通 Shadow，但既能直接帮助表现空间感，也能作为 Dust / Dirt 这类程序化 Mask 的一份输入数据。

---

<a id="ae"></a>

## AE

### Motion / Wallpaper

- [终末地 Perlica 动态壁纸](./AE/Wallpaper-Engine-Production.md)  
  这是我做 Perlica 动态壁纸时留下的一次完整记录。光效从分形杂色开始，一层层叠 VR 色差和径向模糊，再用 Evolution 让它动起来。过程中也把一个之前比较模糊的问题理清了：这种会流动的丁达尔光并不是单靠某一个特效做出来的，而是先做出基础纹理，再通过色差、模糊、光源中心和时间变化把它一步步塑造成动态光束；另外也顺便把画幅、循环和 Wallpaper Engine 输出的问题踩了一遍。

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
│   ├── Endfield-Weather-Procedural-Mask.md
│   └── AO-Ambient-Occlusion-Shader.md
└── AE/
    └── Wallpaper-Engine-Production.md
```

New columns are added only when there is real study content to place inside them.
