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
  这篇是我在研究角色淡出时整理出来的。原本只是觉得“把所有图层一起调透明就行”，后来才发现多层图片会互相透出来、叠色，所以顺便把 CanvasGroup、渲染顺序和更自然的消失方式一起弄明白了。

- [《终末地》3 渲 2 角色渲染与 Shader 通俗解释](./Unity/Endfield-3D-Toon-Rendering-and-Shader.md)  
  这篇算是我真正开始看懂 3 渲 2 的一篇笔记。以前更多是在看“效果好不好看”，整理完以后开始能分清阴影、脸部、头发高光、描边和后期分别在做什么。

- [反光地面：Shader、反射、Roughness、Bump 与环境之间的关系](./Unity/Reflective-Floor-Shader-Reflection-Roughness-Bump.md)  
  这篇是我折腾反光地面时留下的笔记。过程中把 Light、Roughness、Bump 和环境之间的关系慢慢理顺了，也终于能判断地面太亮、太像镜子或者根本没有倒影时到底该改哪里。

- [《终末地》雨雪天气与程序化 Mask](./Unity/Endfield-Weather-Procedural-Mask.md)  
  这篇是从《终末地》的雨雪效果一路整理下来的。最有意思的是发现雨、雪、灰尘和边缘磨损虽然看起来完全不同，但背后其实都可以用已有数据去生成 Mask，再决定效果应该出现在哪里。

---

<a id="ae"></a>

## AE

### Motion / Wallpaper

- [终末地 Perlica 动态壁纸](./AE/Wallpaper-Engine-Production.md)  
  这是我做 Perlica 动态壁纸时留下的一次完整记录。光效从分形杂色开始，一层层叠 VR 色差和径向模糊，再用 Evolution 让它动起来；最后还顺手把 Wallpaper Engine 的画幅和输出问题一起踩了一遍。

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
