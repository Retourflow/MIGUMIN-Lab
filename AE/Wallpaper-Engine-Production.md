<p align="center">
  <img src="../assets/ae-wallpaper-engine-production.svg" width="100%" alt="After Effects Wallpaper Engine Production" />
</p>

<p align="center">
  <a href="../README.md#ae">← AE</a> ·
  <a href="../README.md#map">KNOWLEDGE MAP</a> ·
  <a href="https://github.com/Retourflow">PROFILE</a>
</p>

---

# 终末地 Perlica 动态壁纸

这篇记录对应我制作并发布的《终末地》Perlica 动态壁纸。

## 成品

**Steam Workshop**

[查看最终发布作品](https://steamcommunity.com/sharedfiles/filedetails/?id=3804142795)

<p align="center">
  <img src="../assets/perlica-wallpaper-preview.webp" width="100%" alt="终末地 Perlica 动态壁纸预览" />
</p>

---

## 学习来源

这次壁纸中的主要光效，参考并学习自这个 AE 教程：

[一种光效的制作方法 · Bilibili](https://www.bilibili.com/video/BV1LZSeBLEBx/?spm_id_from=333.337.search-card.all.click&vd_source=3993a89f92a264dd800a0b540f6ef532)

我这次实际用到的核心思路，不是直接套一个现成的“光效插件”，而是从一层可动画的噪声开始，一步步把它塑造成有方向、有色散、有空间感的光束。

---

## 光效是怎么做出来的

### 1. 线性分形杂色作为基础

最底层先使用 **Fractal Noise / 分形杂色**。

关键不是单纯生成一张随机噪声，而是把它整理成偏线性的结构，让明暗纹理更像一束束可以被拉开的光。

可以先理解成：

```text
普通随机噪声
↓
拉成具有方向性的线性纹理
↓
作为光束的基础形状
```

它负责提供后面所有光线的“骨架”。

---

### 2. 叠加三层 VR 色差

在这层线性分形杂色的基础上，再叠加 **3 层 VR Chromatic Aberrations / VR 色差**。

这样做以后，原本比较单一的亮暗纹理会出现轻微的 RGB 分离和色彩边缘。

可以把它理解成：

```text
分形杂色
+
VR 色差 × 3
=
更有层次的彩色光纹
```

这里不是为了做明显的故障感，而是让光线的边缘和内部颜色更丰富。

---

### 3. 用径向模糊把纹理拉成光束

接下来使用 **Radial Blur / 径向模糊**。

这一步是整个效果真正开始像“光”的地方。

原本的线性纹理会因为径向模糊，被从一个中心位置向外拉开，最后形成类似丁达尔光束的视觉效果。

核心关系可以理解成：

```text
线性杂色纹理
↓
径向模糊
↓
从某个点向外扩散
↓
形成光束
```

其中最重要的参数之一就是：

`Center`

它决定径向模糊的中心，所以也可以把它理解成：

> **光从哪里射出来。**

把 Center 放在画面左上，光就会更像从左上方向进入。

移动到其他位置，整束光的方向也会跟着变化。

这也是这套方法非常方便的地方：不用重新画光，只需要调整中心点，就可以重新定义光源位置。

---

### 4. 用 Evolution 关键帧让光真正动起来

静态的 Fractal Noise 只能得到一张固定纹理。

为了让光效产生持续变化，我给 **Fractal Noise 的 Evolution / 演化** 添加关键帧。

也就是：

```text
Evolution
0°
↓
持续变化
↓
1x / 2x / ...
```

随着 Evolution 改变，分形杂色本身的纹理也会不断变化。

而因为后面的：

```text
VR 色差
+
径向模糊
```

都是建立在这层杂色之上的，所以底层纹理一动，最终生成的光束也会跟着缓慢流动。

因此动画链路其实是：

```text
Fractal Noise Evolution
↓
线性纹理变化
↓
VR 色差随纹理变化
↓
径向模糊重新拉伸
↓
光束产生缓慢流动
```

这比直接给光层做位置移动自然很多，因为变化发生在纹理内部。

---

## 这次光效的完整结构

```text
Fractal Noise
线性分形杂色
        ↓
VR Chromatic Aberrations
× 3
        ↓
Radial Blur
径向模糊
        ↓
Center
控制光源位置
        ↓
Evolution Keyframes
驱动纹理持续变化
        ↓
动态丁达尔式光束
```

这次我真正理解到的一点是：

> **光效的动画不一定是“让光移动”，也可以是让生成光的底层纹理不断变化。**

这样得到的效果会更像自然光在雾气、空气颗粒或者介质中缓慢变化，而不是一张光效贴图在画面上平移。

---

## 本次制作重点

除了光效本身，这次还在 After Effects 里完成了最终桌面版本，并针对实际 Wallpaper Engine 使用场景重新检查构图和输出。

过程中重点处理了：

- 合成尺寸与实际桌面画幅之间的关系
- 16:9 素材放进更宽/更高桌面比例时的边缘显示问题
- 通过预合成统一控制最终画面
- 检查最终输出参数和渲染结果
- 对比 AE 中的画面与真正应用到 Wallpaper Engine 后的显示效果

这次最明显的感受是：

> **AE 里“看起来完整”不代表放进 Wallpaper Engine 后就一定完整。**

最终显示效果还会受到桌面分辨率、画幅比例、Wallpaper Engine 的适配方式以及输出清晰度影响。

---

## 记录关键词

`After Effects` · `Fractal Noise` · `VR Chromatic Aberrations` · `Radial Blur` · `Center` · `Evolution` · `Composition` · `Pre-compose` · `Aspect Ratio` · `Render` · `Wallpaper Engine`
