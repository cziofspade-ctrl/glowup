# Effect Atlas · 创意效果图谱

这不是“必选菜单”，而是用于发散的机制地图。不要一次性全部使用。

## 1. 程序化纹理

### Halftone / 半色调点阵
视觉：印刷网点、数字版画、像素密度变化。
技术：CSS `radial-gradient`、SVG `pattern`、mask、Canvas。
适用：天气状态栏、背景分区、加载状态、小型插画。
性能：CSS pattern 通常轻；大量独立 DOM 点阵重。

### Dithering / 抖动
视觉：复古像素、有限色阶下的颗粒过渡。
技术：预计算图案、SVG pattern、Canvas 图像处理。
适用：复古、电子、打印机、旧电脑主题。

### Cross / Grid Pattern
视觉：十字、点、网格、扫描线、工程图。
技术：CSS repeating-gradient、SVG pattern。

## 2. 纸张与墨水

### Paper Grain
技术：SVG `feTurbulence`、静态纹理、CSS blend。
建议：大面积持续动态噪声慎用；静态 / 低频更适合主题。

### Ink Bleed
视觉：墨水渗进纸纤维、边缘不规则扩散。
技术：mask + blur + turbulence/displacement，或预制 mask 序列。
适用：文字出现、菜单展开、章节切换。

## 3. 陶瓷 / 釉面 / 软触感
视觉：厚度、柔和高光、釉面反射、触觉感。
技术：多层 box-shadow、渐变高光、specular lighting、小范围动态 sheen。
适用：tab、开关、选中按钮。
注意：小面积效果更可信。

## 4. Holographic Foil / 全息薄膜
视觉：随角度变化的虹彩反射。
技术：多层 gradient、background-position、mix-blend-mode、pointer-driven CSS variables；高级版可用 WebGL shader。
适用：稀有状态、徽章、特殊卡片、选中态。
风险：不要大面积铺满整个聊天区。

## 5. Glass / Refraction

### 普通 Glassmorphism
`backdrop-filter: blur(...)`

### 真折射感
SVG `feDisplacementMap`、位移贴图、shader。
视觉：后方文字 / 图形真的发生光学扭曲。
风险：高。大面积、滚动内容、多层同时存在时容易卡。
策略：仅用于固定菜单 / 输入区 / 小组件；提供低性能模式。

## 6. Gooey / Liquid
视觉：元素靠近时像液体融合，文字像墨水融化切换。
技术：`feGaussianBlur` + `feColorMatrix` + composite；动画由 CSS/GSAP/JS 驱动。
适用：时间戳、菜单、按钮展开、状态切换。

### Gooey Text Morph
两层文字重叠，通过 blur、颜色矩阵和 opacity / position 交叉变化制造“字形融化成另一串文字”的错觉。
适合：时间 ↔ 日期、状态名 ↔ 数值。

## 7. SVG Path

### Draw-on
使用 `stroke-dasharray` + `stroke-dashoffset` 让路径被逐渐画出。
适用：月亮、天气图标、签名、分隔线。
性能：通常轻。

### Morph
路径之间变形。
适用：图标状态变化。
注意：路径点结构要兼容，或使用专门 morph 工具。

## 8. Mask / ClipPath
视觉：图像从不规则形状中显露、被侵蚀、被波纹扫过。
适用：面板展开、天气切换、图片揭示、墨水转场。
Mask 可有灰度 / 透明度；clipPath 更像硬裁剪。

## 9. Elastic / Squishy
视觉：边界被拉扯、按钮被压扁、菜单像橡胶回弹。
技术：SVG path、CSS transform、spring easing / GSAP。
适用：菜单、QR 折叠、按钮反馈。

## 10. Magnetic Interaction
视觉：鼠标靠近时按钮 / 文字轻微向光标偏移。
技术：pointermove + transform。
适用：桌面端关键按钮。
移动端：退化为 press / tap feedback。

## 11. Dynamic Text Material

### Animated Fill
让纹理 / 渐变 / 视频只存在于文字内部。
技术：`background-clip: text`、SVG mask。

### Path Text
SVG `textPath` 让文字沿曲线排布。
适用：圆形时间、仪表、装饰标签。

### Glitch / Displacement
短暂错位、切片、位移。
适用：错误、系统提示、电子主题。
不要持续播放。

## 12. Hand-drawn Motion
视觉：线条每一帧略有差异，像传统手绘动画。
技术：turbulence + displacement，或少量预设 path 轮换。
适用：草图、铅笔、童话、手帐主题。
风险：持续 SVG filter 中等偏高。

## 13. State-driven Illustration
重点不是“换图片”，而是同一视觉系统发生变化：
- 点阵密度
- mask 形状
- 路径轮廓
- 颜色变量
- 图层位置
- 高光方向

适合天气、昼夜、情绪、角色状态。