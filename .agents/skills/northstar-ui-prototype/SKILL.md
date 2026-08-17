---
name: northstar-ui-prototype
description: 维护或扩展 Northstar 个人 UI 风格的原生单文件 HTML 原型。用于 Blog、Docs、Dashboard、组件库或移动 Web 示例的视觉调整、主题色、深浅模式、Maple Mono 字体、微交互与可访问性细节；在需要保持暖浅色、深灰、克制技术感和统一状态反馈时使用。
---

# Northstar UI 原型

将此风格用于快速视觉验证的原生 HTML 原型，而不是组件库或最终设计系统。以下规范是自包含的固定基线；先检查目标页面已有的 CSS 变量、结构和脚本，再以最小改动延续其交互。

## 视觉基线

- 使用 **Clean / Soft / Neutral / Calm / Technical / Refined** 的方向：内容优先、低饱和、边界轻、阴影少。
- 浅色页面以暖象牙白 `#fffcf5` 为基底，禁止用醒目的纯白大面积铺底；深色页面使用 `#1b1c1f`、`#202226`、`#27292e` 的灰阶，不使用纯黑或简单反色。
- 默认强调色为霁青（Light `#5086a1`、Dark `#76a9bc`）。可选主题为陶朱（核心 `#ad4506`）、藕荷（`#b06d88`）、麦金（`#b59a2a`）；浅色麦金应保持清透金黄，避免赭褐。
- 用背景、文字层级和细边界组织内容。常规卡片不加阴影；仅 Dropdown、Toast、Dialog 等浮层使用柔和阴影。
- 使用 `6 / 10 / 14px` 圆角节奏；按钮与输入通常为 `8px`。不要把所有元素做成大圆角或 Bento 卡片。

## 固定 Token 与排版规范

### 色彩

- Light 基础层级：`--bg: #fffcf5`、`--bg-soft: #f5f1e8`、`--surface: #fffdfa`、`--surface-raised: #fffefb`。
- Light 默认文字层级：`--text: #34363b`、`--text-2: #62656c`、`--text-3: #8a8e95`。默认品牌色：`--brand: #5086a1`、`--brand-hover: #3d6f87`、`--brand-active: #315d72`、`--brand-soft: #d9eaee`、`--brand-soft-strong: #c6e0e6`、`--brand-ink: #285a70`。
- Dark 基础层级：`--bg: #1b1c1f`、`--bg-soft: #17181a`、`--surface: #202226`、`--surface-raised: #27292e`、`--text: #e6e8e9`、`--text-2: #b5b8bd`、`--text-3: #868b92`。默认品牌色：`--brand: #76a9bc`、`--brand-hover: #8db9c9`、`--brand-active: #9cc6d3`。
- Light 主题核心：霁青 `#5086a1`、陶朱 `#ad4506`、藕荷 `#b06d88`、麦金 `#b59a2a`。让陶朱醒目但内敛；让藕荷与麦金在浅色态保持中等深度，不让麦金偏棕。
- 品牌色只用于主操作、链接、选择态与少量数据强调，不能大面积装饰。

### 字体

- 使用 Sans Serif 负责界面阅读与长文本：`Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif`。
- 使用 Maple Mono 作为技术性格：`"Maple Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace`。仅使用 400 / 600 / 700 三档，不使用 Light 或 ExtraBold。
- 保留三种可切换模式：**Sans First**（Mono 只用于代码、路径、版本、ID、数值）、**Maple Accent**（Mono 还用于站点名、KPI、技术元数据、日期和短标签）、**Maple Heavy**（当前默认；Mono 扩展至导航、按钮、Tabs、Badge、表格和短标题）。
- 无论模式如何，Blog / Docs 长正文、中文长段落和长说明均保持 Sans Serif。正文行高保持约 `1.5–1.82`；Blog 正文宽度约 `720px`；Dashboard 数字使用 tabular figures。

### 边界、阴影与布局

- 使用 4 / 8px 间距节奏，优先取 `8 / 12 / 16 / 24 / 32 / 48 / 64px`。
- 桌面内容容器约 `1040–1240px`；移动端 gutter 约 `14–20px`。Dashboard 中等密度，Blog 更舒展，组件页介于两者之间。
- 默认分隔使用低对比 1px border；普通 Tag 保持 6px 圆角，短状态 Badge 才可使用 pill。
- 常规 Card 无阴影。阴影只用于 Dropdown、Toast、Dialog 与必要浮层。

## 实现规则

1. 将主题差异放入 CSS 自定义属性。保持变量命名和 Light / Dark 配套完整，避免在组件规则中散落硬编码色值。
2. 使用 `data-theme`、`data-accent` 与 `data-typography` 驱动状态；主题色选择器应同步 `aria-checked` 和 localStorage。
3. 默认保留 Maple Heavy 实验模式：短标题、导航、按钮、Tabs、Badge、表格与技术标签可使用 Maple Mono；正文、长说明和中文长文本始终使用 Sans Serif。
4. 常规分隔可为 1px；可选择、聚焦或激活的带边框控件使用单层 2px 品牌色边框，不叠加第二圈 outline 或 shadow。
5. 图标统一使用约 2px 描边、圆端点和圆连接；图标中的点应使用实心圆或可见的圆端点，不能用不可见的极短平口路径。
6. 链接在精确指针设备上保持颜色高亮，并以 120–140ms、约 `scale(1.015)` 提供轻微反馈；触摸设备和 `prefers-reduced-motion` 不使用该缩放。

## 主题切换与动效

- 主题切换使用短暂的页面色彩交叉过渡，不能突变；在 `prefers-reduced-motion` 下退化为即时且静态的状态变化。
- 浅转深：星点错峰进入，随后以低幅、不同周期漂浮。
- 深转浅：云朵错峰进入，随后低幅漂浮；浅色态月亮应淡化并位于云层后方，深色态太阳亦应淡化并位于星点后方。
- 高频 hover / press 只使用 `transform`、`opacity`、颜色或边框，持续约 125–180ms。避免 bounce、无意义 stagger 和整页装饰性入场。

## 页面级取舍

- **Dashboard**：保持中等信息密度。用 Maple Mono 强化 KPI、ID、版本和技术数值，但不要变成终端界面。
- **Blog / Docs**：优先阅读体验；正文宽度约 720px，正文不使用 Mono。将强调色限于链接、Callout、代码与少量元数据。
- **Components**：展示 default、hover、active、disabled、focus。目录或标签跳转必须用 `aria-current="location"` 等真实状态驱动高亮，禁止用 `:first-child` 固定当前项。
- **Mobile**：保持桌面同一语义与主题规则，缩小留白而非缩小可点击区域。

## 验证清单

- 在四套主题色与深浅模式下检查对比度、边框和强调色是否一致。
- 切换字体模式，确认长正文仍为 Sans Serif，短技术信息才使用 Mono。
- 键盘聚焦、选择态和目录锚点只呈现一层清晰状态。
- 检查 SVG 中的问号、感叹号、省略号等点状细节。
- 检查 `prefers-reduced-motion`，并在浏览器中实际点击主题切换、主题色、目录锚点和主要浮层。
