# 尺素 · 独立玻璃组件

来源：用户提供的已拆分玻璃组件，作为 Glowup 的参考实现。

## 为什么收录

这不是单一“毛玻璃样式”，而是三种不同性能层级与用途的玻璃材质，可用于以后设计 SillyTavern 消息、菜单、输入栏或固定浮层时做技术参考。

## 1. 原生 CSS 毛玻璃

核心：`backdrop-filter: blur(...) saturate(...)`，配合透明填色、边缘与 surface wash。

优点：
- 无 SVG / JS / 网络依赖
- 结构简单
- 适合多数主题和较多组件

注意：
- 大面积 backdrop-filter 在滚动与动态背景上仍可能触发昂贵重绘

## 2. SVG 用户消息玻璃

核心：
- SVG 位移图
- 折射 / displacement
- CSS fallback

适合：
- 少量局部卡片
- 需要明显液态玻璃质感的消息或重点组件

风险：
- 比普通毛玻璃重
- 长聊天中不应给每条消息无节制启用实时折射

原实现含较大的内嵌位移图，Glowup 不把该 base64 数据当知识主体；保留来源与机制说明即可，实际迁移时再按目标组件生成或引用合适位移图。

## 3. SVG 输入框玻璃

核心：
- `feDisplacementMap`
- 极轻 `feGaussianBlur`
- `feComponentTransfer`
- rim / edge highlight
- hover / focus-within 阴影过渡

适合：
- 输入栏
- 工具条
- 固定横向控件

优势：
- 折射只作用底层，输入文字保持清晰
- 支持 CSS fallback
- 可用 data 属性切换主题与引擎

## 值得复用的工程习惯

- 日间默认，`data-glass-theme="night"` 切夜间
- `data-glass-engine="css"` 明确切回 CSS fallback
- CSS 变量统一控制 radius / padding / fill / text / shadow / wash
- 玻璃底层放在 `::before`，正文保持清晰和可交互
- 不用容器整体 opacity 调透明度
- 组件不接管项目背景、字体、固定宽高和定位
- SVG 源文件与内嵌 CSS 分离，方便阅读和调试

## Glowup 使用规则

以后用户要求“做毛玻璃 / 液态玻璃”时：

1. 先判断是否真的需要折射。
2. 轻量需求优先原生 CSS。
3. 固定输入栏 / 菜单等小面积区域可考虑 SVG 折射。
4. 大量重复消息节点默认不用高成本折射。
5. 必须提供移动端 / 不支持 SVG 时的 fallback。
6. 保留原实现许可证与来源声明。
