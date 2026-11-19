# Glowup

一个面向 SillyTavern 主题、状态栏与交互组件的 Creative Coding Skill。

Glowup 的目标不是堆特效，而是让 AI 主动研究 CSS / SVG / JavaScript / React / Canvas / WebGL 等视觉机制，在性能和可维护性约束下找到真正有记忆点的 UI 设计。

## 入口

- `SKILL.md`：AI 的核心工作流与硬规则
- `references/effect-atlas.md`：视觉机制图谱
- `references/performance-budget.md`：性能预算
- `references/research-playbook.md`：如何做视觉侦察
- `cases/`：经过分析的真实案例
- `assets/`：原始参考实现与素材
- `examples/design-brief.md`：设计简报模板

## 维护原则

发现漂亮效果时，不直接把代码堆进 Skill。先判断它是新的视觉机制，还是已有机制的优秀实现。机制进入 references，案例进入 cases，可复用的原始实现进入 assets。

当前首个本地参考实现：`尺素-独立玻璃组件`，包含原生 CSS 毛玻璃、SVG 用户消息折射玻璃与 SVG 输入栏折射玻璃。
