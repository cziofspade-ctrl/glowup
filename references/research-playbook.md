# Research Playbook · 视觉侦察指南

当需要“更有创意”的方案时，AI 应主动研究，而不是只依赖自己最熟悉的 UI 模板。

## 优先来源

### Codrops / Tympanus
Creative Coding、SVG、交互文字、WebGL、页面转场、实验性 UI。

入口：
- https://tympanus.net/codrops/hub/all/
- https://tympanus.net/codrops/hub/tag/svg/

代表性方向：
- Gooey Text Hover Effect
  https://github.com/codrops/GooeyTextHoverEffect
- Magnetic Buttons
- Elastic SVG Elements
- Animated Text Fills
- Dynamic Shape Overlays
- Organic Shape Animations

研究 Codrops 时优先：Demo → Article → GitHub source。

### CodePen
适合发现单一效果、实验原型、小型 CSS/SVG 技巧。

搜索词不要只用“beautiful UI”，而应使用机制词：
- svg filter text
- gooey text
- displacement map
- halftone css
- dithering css
- holographic foil css
- ink bleed svg
- elastic svg menu
- magnetic button
- text mask animation
- ceramic css
- shader ui

### GitHub
用于读取源码、依赖与许可证。
如果 Demo 有仓库：
- 先看 `src/`
- 再看 package.json
- 不要优先读打包后的 dist 巨型文件

### MDN
用于确认标准 API、浏览器支持、SVG/CSS 语义。

## 研究方法
每次最多选择 2~5 个高相关参考，不要陷入无限收藏。

对每个案例记录：

```text
Reference:
Visual mechanism:
Trigger:
Core technology:
Dependencies:
Performance risk:
Portable idea:
Do not copy:
```

最后必须回答：
> 哪个机制最适合当前界面，而不是哪个 Demo 最炫？

## 许可证
开源不等于可以随意复制。
检查：
- MIT / Apache / BSD 等
- attribution 要求
- 商用限制
- 素材 / 字体是否另有许可证

如果许可证不清楚，只借鉴原理，不直接复制实现。