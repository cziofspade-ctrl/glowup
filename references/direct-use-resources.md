# Direct-use Resource Library · 可直接调用资源库

本页收录适合 Glowup 在 SillyTavern 美化中直接调用、复制、下载、安装或改造的资源。目标不是“堆素材”，而是优先复用成熟资产，再把精力放到真正有创意的组合与交互上。

## 使用原则

1. 用户明确要求免费时，优先选无需会员、无需付费解锁核心资源的来源。
2. 优先 inline SVG / 本地 SVG / NPM 包；避免把主题核心功能绑死在第三方远程 URL。
3. 使用前检查单个资源的许可证，不因为网站整体“免费”就默认每个条目都相同。
4. 静态图标优先 currentColor、保留 viewBox、由 CSS 控制尺寸。
5. 动画 SVG 优先保留内部 CSS / SMIL 结构；需要主题适配时再抽成 CSS 变量。
6. 外部库只引入实际需要的部分，避免为了一个 20px 图标引入整套框架。

---

# A. 静态 SVG 图标

## SVG Repo
https://www.svgrepo.com/

用途：大范围搜索图标、插画、图形。
特点：50 万+ open-licensed SVG；可在线编辑；无 Premium 搜索结果混入。
注意：SVG Repo 收录多种许可证，具体图标页必须单独检查。

适合：
- 菜单 / 设置 / 时间 / 天气 / 人物 / 状态图标
- 插画装饰
- 找不同视觉风格的同类 icon

## Lucide
https://lucide.dev/

用途：统一、克制的线性 UI 图标。
特点：开源、SVG、可调 stroke / size / color；适合 inline SVG 或包导入。
适合：
- 工具栏
- 设置项
- 发送 / 保存 / 刷新 / 菜单等功能 icon

## Tabler Icons
https://tabler.io/icons

用途：大型、统一的线性 SVG 图标集。
特点：MIT；可直接 inline SVG、下载或 NPM 安装。
适合：
- 功能 UI
- 状态栏
- 需要风格统一的大量图标

## Phosphor Icons
https://phosphoricons.com/

用途：多 weight 的统一图标系统。
适合需要同一图标在 thin / regular / bold / fill 等状态之间切换的界面。

---

# B. 动态 SVG / 动态图标

## Sveegees
https://www.sveegees.com/

用途：直接复制带动画的 SVG。
特点：当前约 400+ 动画 SVG；loader、arrow、UI、media、weather、chat 等；SVG 内置 CSS 动画；无需 JS。
许可：站点说明个人与商业项目免费、无需署名。

适合：
- 加载器
- 箭头
- 播放 / 暂停
- 聊天 / 媒体按钮
- 小型天气动画

## Meteocons
https://meteocons.com/

用途：天气与环境状态。
特点：500+ 动画天气图标；SVG / Lottie；Fill、Flat、Line、Monochrome 四种风格。
可安装：
`npm install @meteocons/svg`

适合：
- 天气状态栏
- 月相
- 温度 / 风 / UV / 警报
- 日夜状态

## Line MD
https://github.com/JoJk0/line-md

用途：Material 风格动态 SVG，尤其适合 icon → icon transition。
适合：
- menu → close
- sunny ↔ moon
- loader
- 状态切换

优先用于“图标发生形变”，而不是淡出后换图。

---

# C. SVG 背景 / 图案 / 纹理

## Hero Patterns
https://heropatterns.com/

用途：可重复 SVG background pattern。
特点：直接生成 CSS background code；CC BY 4.0。
适合：
- 面板底纹
- 纸张 / 几何 / 低对比装饰背景

## Haikei
https://haikei.app/

用途：生成 waves、blobs、grids、gradients、symbols 等 SVG。
免费层：无需注册，15 个 generator；可无限下载 SVG。
适合：
- 状态栏背景
- 不规则分区
- 波浪 / blob / 网格 / 生成式背景

## BGJar
https://bgjar.com/

用途：直接生成多种 SVG 背景。
例：wave、circuit board、contour line、snow、cloudy、stars、abstract paper、blob。
适合：
- 快速生成主题底图
- 科技 / 星空 / 纸张 / 天气类背景

## fffuel
https://www.fffuel.co/

用途：免费 SVG generators、颜色、gradient、pattern、texture、shape、blob。
额外：可生成 inline CSS / base64 背景素材。
适合：
- 不想额外上传图片时生成可嵌入 CSS 的纹理
- 渐变 / blob / grain / pattern

## Pattern Monster
https://pattern.monster/

用途：SVG pattern generator。
注意：当前免费与 Premium 混合。用户要求完全免费时应主动过滤 Free，不把 Premium 当默认推荐。

---

# D. CSS 动画 / 设计 token

## Animista
https://animista.net/

用途：挑选、调节并复制单个 CSS animation。
特点：可调 duration / easing / delay 等，只复制真正需要的动画。
许可：生成 CSS 可用于个人与商业项目，FreeBSD。

适合：
- 进入 / 退出
- hover / focus
- attention animation
- 不值得引入 JS 动画库的小交互

## Open Props
https://open-props.style/

用途：直接调用 CSS custom properties。
特点：MIT，可 CDN 或 NPM；包含颜色、尺寸、阴影、easing、animation、gradient 等 tokens。
CDN 示例：
`@import "https://unpkg.com/open-props";`

适合：
- 快速建立统一的 spacing / shadow / easing / color 体系
- 避免 AI 每个组件都随手造不同数值

注意：SillyTavern 长期主题优先抽取实际需要的变量，不必永远依赖 CDN。

---

# E. JavaScript / React 动画引擎

## Motion
https://motion.dev/

用途：复杂布局、gesture、scroll、shared layout 动画。
特点：JavaScript / React / Vue；免费开源。
适合：
- React 状态栏
- drag / press / hover
- layout transition
- scroll-linked animation

不要为了简单 opacity / transform 动画引入。

## Anime.js
https://animejs.com/

用途：轻量时间线、SVG、文字、draggable、复杂 easing。
支持 NPM、ESM、CDN。
CDN 示例：
`import { animate } from 'https://esm.sh/animejs';`

适合：
- SVG path
- timeline
- 多元素编排
- 原生 JS 页面 / 酒馆助手脚本

---

# F. Lottie / 动画素材

## LottieFiles
https://lottiefiles.com/

用途：现成 Lottie 动画、JSON 动画素材。
免费动画受 Lottie Simple License 约束，可免费使用、修改和商业使用；Premium 另算。

适合：
- 状态动画
- loading
- 空状态
- 较复杂但不想自己写 SVG path 的动画

注意：
- Free / Premium 混合，必须确认当前素材类别。
- 不要把大型 Lottie 用在几十条重复消息上。
- SVG 能解决时，状态栏小图标优先 SVG。

---

# G. Generative / Creative Coding

## css-doodle
https://css-doodle.com/

用途：用少量声明生成 grid / pattern / generative art。
可通过 ESM 直接注册 `<css-doodle>`。
适合：
- 程序化背景
- 几何 pattern
- 随机图案
- 实验性状态栏背景

注意：如果最终只需要一个固定图案，可以生成后固化成 SVG / CSS，避免长期引入运行时。

---

# AI 调用优先级

用户要一个普通功能 icon：
Lucide / Tabler / SVG Repo

用户要动态图标：
Sveegees → Line MD

用户要天气：
Meteocons

用户要背景 pattern：
Hero Patterns → fffuel → Haikei / BGJar

用户要简单 CSS 动画：
Animista

用户要复杂原生 JS / SVG 动画：
Anime.js

用户用 React / Vue 做复杂状态栏：
Motion

用户要现成复杂动画素材：
LottieFiles（优先 Free）

用户要生成式视觉：
css-doodle / SVG pattern / Canvas

---

# 收录新资源时记录

```text
Name:
URL:
Category:
Direct-use mode: inline SVG / download / CDN / NPM / copy CSS / generator
Free status:
License:
Good for:
Avoid when:
SillyTavern notes:
```

只收真正能提高实现效率或视觉可能性的资源。不要把纯灵感网站和“可直接调用资源”混为一类。


---

# H. Variable Font · 可变字体

## Google Fonts Variable Fonts
https://fonts.google.com/

用途：直接在网页里调用开源可变字体。
特点：
- Google Fonts 全部字体采用开源许可证，可用于商业与非商业项目。
- CSS API v2 支持 variable font axis range。
- 可直接通过 `<link>` / CSS API 引入，不需要会员。

示例：
```html
<link rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@200..900&display=swap">
```

然后可用：
```css
.title {
  font-family: "Crimson Pro", serif;
  font-weight: 420;
}
```

如果字体有自定义轴，可进一步用 `font-variation-settings`。

适合：
- 时间戳 hover 时字体“长胖 / 变窄 / 变斜”
- 标题随状态改变字重和宽度
- 不换字体文件也能做连续 morph 感
- 动态排版、响应式状态栏

注意：
- 只请求实际需要的轴与范围，避免加载过大的字体数据。
- 中文可变字体数量和轴范围通常比拉丁字体少，使用前检查字符覆盖。

## Refract Variable Font Playground
https://refracttools.com/variable-font-playground/

用途：拖入本地 TTF / OTF / WOFF / WOFF2，自动识别全部 axes，拖滑杆并直接复制 CSS。
特点：
- 浏览器本地处理
- 无账号
- 可直接 Copy CSS
- 自带 Animate 预览

适合：
- 已有字体但不知道 `wght` / `wdth` / 自定义轴怎么写
- 给 AI 确认实际 axis tag 与范围
- 先调出喜欢的状态，再把值写入主题

## openWorkstand Variable Font Tester
https://www.openworkstand.com/variable-font-tester

用途：上传 variable font，自动生成 sliders 和 CSS。
特点：
- 免费
- 无登录
- 浏览器本地处理
- 支持 WOFF2 / WOFF / TTF / OTF
- 标准轴优先转成 `font-weight`、`font-stretch` 等；自定义轴输出 `font-variation-settings`

## Axis-Praxis
https://www.axis-praxis.org/

用途：专门探索 variable font 的视觉可能性。
特点：
- 免费浏览器 playground
- 可拖本地 variable TTF
- 可实时 animate axes
- CSS 按钮可生成复现设置

Glowup 规则：
Variable Font 不只用于“选字体”，也可以被当作动画材料。优先把 axis 变化与信息状态绑定，而不是无意义循环。

---

# I. SVG Filter Generator · 可直接生成滤镜代码

## SVG Filter Effects Generator · IO Tools
https://iotools.cloud/tool/svg-filter-effects-generator/

用途：可视化构建 SVG `<filter>` 并复制成品代码。
可直接生成 / 调节：
- `feGaussianBlur`
- `feColorMatrix`
- hue rotate
- saturate
- luminance-to-alpha
- `feTurbulence`
- `feDisplacementMap`
- `feDropShadow`
- `feConvolveMatrix` emboss / engrave / sharpen / edge detect

特点：
- 在线实时预览
- 可直接复制 SVG filter definition 和 CSS `filter: url(#id)`
- 图片预览在本地浏览器处理
- 无需自己手写复杂 filter pipeline

适合：
- Gooey / distortion
- 手绘抖动
- 水波 / 热浪
- 玻璃折射原型
- emboss / engraving
- 噪声遮罩

注意：
生成器只解决“怎么写出滤镜”，不替代性能判断。尤其 `feTurbulence + feDisplacementMap` 不要大面积常驻。

## SVG Playground
https://webdevpuneet.com/svg-playground/

用途：直接编辑、预览、下载 SVG。
特点：
- 免费浏览器工具
- 可复制 / 下载 SVG
- 支持 filter、mask、clipPath、gradient、pattern、CSS animation、SMIL、textPath、stroke drawing 等
- 适合把生成器代码贴进去继续改

Glowup 规则：
AI 如果对 SVG filter 结构不确定，应先用生成器得到最小正确版本，再按目标视觉做精简，不要凭空堆 fe* primitives。

---

# J. Noise / Grain · 噪点、纸张、胶片纹理

## Refract Grain & Noise Generator
https://refracttools.com/noise-texture-generator/

用途：直接生成超小型 SVG noise + CSS。
特点：
- 免费
- 无注册
- Copy code
- 可调 grain size、detail、strength、blend mode、tile size
- 生成的 SVG filter 可以直接嵌入 CSS data URI

典型用途：
- 纸张
- 胶片
- 印刷感
- 磨砂背景
- 渐变防 banding

## Wensity Noise Texture Generator
https://ui.wensity.com/tools/noise-texture-generator

用途：生成 fine grain、soft grain、clouds、paper。
特点：
- 全部导出免费
- 无账号
- 无水印
- 可导出 PNG / JPG / WebP / SVG / CSS
- 可生成透明 overlay
- 支持 seamless tile
- Paper 模式可调 roughness、fibres、folds、wrinkles 等

特别适合：
- 更像“纸”的材质，而不是单纯灰色噪声
- 需要透明 grain 覆盖已有背景

## SVG Noise & Grain Generator · ALI Tools
https://alitools.online/svg-noise-texture/

用途：直接调 `feTurbulence` 参数并 Copy SVG。
特点：
- 100% free
- no sign-up
- no watermark
- 可调 baseFrequency / octaves / opacity / seed / stitch

适合：
AI 需要一个最小、干净、可读的 `feTurbulence` 示例时优先使用。

## NoiseGradient
https://noisegradient.com/

用途：渐变 + grain 一体生成。
特点：
- 无账号
- 可导出 PNG / SVG
- 可 Copy CSS
- 支持 organic / linear / radial / conic gradient
- grain 有 noise / film / scanlines
- royalty-free 导出

适合：
- 一步生成“有质感的渐变”，避免普通光滑渐变显得塑料

## MeshSVG Seamless Texture Generator
https://www.meshsvg.com/textures/

用途：无缝 SVG turbulence texture。
特点：
- 免费商用
- 无登录
- 无水印
- Copy CSS / 下载 tile
- 输出 data URI，可零额外图片请求

适合：
- 纸张、grain、surface texture
- 需要重复平铺且看不出接缝的背景

## Super Designer Noise / Texture
https://superdesigner.co/

用途：一站式生成 SVG noise / texture。
特点：
- 完全免费
- 无账号
- 可即时导出 SVG / CSS / PNG
- 同站还提供 clip-path、section divider、animated gradient、CSS background 等工具

Glowup 规则：
噪声纹理优先“静态小 tile / data URI / background layer”，不要默认让 `feTurbulence` 每帧动画。静态纹理往往能得到 80% 的质感，只付出很小的性能成本。

---

# 三类资源调用优先级

用户要动态字体 / 时间戳文字变化：
Google Fonts Variable Fonts → Refract Variable Font Playground → Axis-Praxis

用户要做 SVG 特殊滤镜：
IO Tools SVG Filter Generator → SVG Playground → 手工精简

用户要纸张 / 胶片 / grain：
Refract（最小 CSS） → Wensity（复杂纸张） → MeshSVG（无缝 tile）

用户要渐变 + grain 一次完成：
NoiseGradient
