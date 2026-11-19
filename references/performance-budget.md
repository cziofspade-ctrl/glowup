# Performance Budget · 性能预算

## 目标
创意效果必须在 SillyTavern 的真实使用场景中成立，而不是只在单独 Demo 页面里好看。

真实场景包括：
- 长聊天记录
- 手机 WebView / 浏览器
- 多插件同时存在
- 输入框频繁变化
- 滚动
- 多消息节点

## 风险分级

### 轻量
- transform
- opacity
- CSS gradient / repeating-gradient
- SVG path 静态图形
- SVG pattern
- 小范围 stroke animation
- CSS variable 状态切换

### 中等
- 小范围 mask animation
- clipPath morph
- 多层 shadow
- pointer-driven parallax
- 小范围 blur
- 少量 SVG filter
- GSAP timeline

### 高风险
- backdrop-filter 大面积覆盖滚动内容
- 多个实时 SVG turbulence
- feDisplacementMap 大面积持续动画
- mix-blend-mode 多层叠加
- Canvas 高粒子数量
- WebGL shader 全屏长期运行
- 每条聊天消息都附加实时滤镜

## 规则
1. **动局部，不动整屏**。
2. **事件触发优先于永久循环**。
3. **重复图案优先于重复节点**。
4. **共享 `<defs>` 优先于每个组件复制滤镜**。
5. **transform/opacity 优先于 layout 属性动画**。
6. **元素离屏后暂停**。
7. **document hidden 时暂停**。
8. **移动端自动降级**。
9. **支持 prefers-reduced-motion**。
10. **高成本滤镜结束后移除**。

## DOM 数量
禁止为了点阵 / 雨滴 / 星星创建几百上千个 `<div>` 并逐个动画，除非经过明确性能测试且确有必要。
优先：background pattern、SVG pattern、sprite、Canvas。

## SVG Filters
SVG filter 的成本和“代码行数”无关，更取决于：
- filter region 面积
- 每帧是否变化
- 是否作用在滚动内容上
- 是否同时存在多个实例

同一个滤镜定义尽量复用。

## Glass
`backdrop-filter` / 折射类效果尤其注意：后方内容滚动或变化时可能触发昂贵重绘。
建议：
- 只用于固定菜单 / 输入栏
- 控制面积
- 减少层数
- 手机关闭真实折射，保留透明度 + 边框 + 静态高光

## JS
避免：
- 高频 MutationObserver 全页面扫描
- 每个消息单独创建 Observer
- requestAnimationFrame 永久跑但实际没有变化
- pointermove 每次都读写 layout

建议：
- event delegation
- observer 复用
- throttle / requestAnimationFrame 合并更新
- 数据变化时才更新

## 验收
至少测试：
- 50+ 消息
- 快速滚动
- 输入框展开/收起
- 菜单开关
- 手机宽度
- 动画连续触发 10 次

出现明显掉帧时，优先减少滤镜面积与并发，而不是先缩短动画时间。