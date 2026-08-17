# Style Notes — v0.1

这是一份视觉实验记录，不是正式 Design System。

## Color

- Neutral-first：浅色模式以暖象牙白 `#fffcf5` 为页面底色，并用 `#f5f1e8`、`#fffdfa` 建立层级；深色模式继续使用多层深灰。
- 默认 Brand 使用低饱和 blue-cyan：Light `#5086a1`，Dark `#76a9bc`。浅色 soft 层级由 `#e8f2f4` 加深为 `#d9eaee`，提高选中态辨识度。
- 四套主题命名为：霁青、陶朱、藕荷、麦金。陶朱以 `#ad4506` 为核心；麦金浅色模式以 `#b59a2a` 为核心，整条色阶向清透金黄校准，避免赭褐感。

## Typography Experiment

- **Sans First**：界面、正文和长阅读内容使用 Sans Serif；Maple Mono 仅用于代码、路径、版本、ID、数值型技术信息。
- **Maple Accent**：Sans Serif 承担阅读；Maple Mono 用于站点名、Dashboard KPI 与图表数值、技术元数据、日期、标签、编号和代码。
- **Maple Heavy**（当前确认方案）：将 Maple Mono 扩展至导航、按钮、Tabs、Badge、表格与短标题；长正文和长说明仍由 Sans Serif 承担。
- Maple Mono 仅注册并使用 Regular（400）、SemiBold（600）、Bold（700）；不用于 Light / ExtraBold。
- Blog 的长正文、说明文字与长描述在全部模式中保持 Sans Serif，避免中文阅读体验退化。
- 已确认：当前原型以 Maple Heavy 作为默认方案；仍保留另外两种模式供后续对照。
- Brand 只承担主操作、链接、选中状态和少量数据强调，不做大面积装饰。
- Dark Mode 使用 `#1b1c1f`、`#202226`、`#27292e` 的灰黑层级，不做颜色反转或纯黑 OLED 风格。

## Typography

- 使用系统 sans-serif 字体栈；代码与日期使用 system monospace。
- 标题靠字号、字重和紧凑字距建立层级，正文保持 1.5–1.82 行高。
- Blog 正文宽度约 720px；Dashboard 数字使用 tabular figures。

## Radius & Border

- Radius：`6 / 10 / 14px`，按钮和输入以 8px 为主。
- 默认分隔使用低对比、视觉更稳的 1px border；图标统一采用 2px 描边。
- Focus 与 selected 状态只保留一层清晰的 2px 品牌色边界，避免外套第二层描边或阴影。
- Badge 使用 pill，仅限短状态；普通 Tag 保持 6px 圆角。

## Shadow

- 常规 Card 无阴影。
- 阴影只用于 Dropdown、Toast、Dialog 和示意中的悬浮窗口。

## Spacing & Layout

- 采用 4 / 8px 节奏，常用间距为 `8 / 12 / 16 / 24 / 32 / 48 / 64px`。
- Dashboard 为中等密度；Blog 更舒展；Components 介于两者之间。
- 桌面端内容容器约 1040–1240px，移动端保留 14–20px gutter。

## Motion

- Hover / press 约 125–180ms；Dialog 约 200ms；使用强 ease-out。
- 日 / 月主题开关采用 220ms 的滑块与图标状态转换；减少动态效果时仅保留即时颜色反馈。
- 主题切换使用页面级颜色交叉过渡；浅转深以错峰星点进入并低幅漂浮，深转浅以云朵进入，减少动态效果时两者静止。
- 高频状态反馈只使用 120–140ms 的颜色、透明度或 1px 位移；不对列表、数据或页面内容做装饰性运动。
- 按钮按下使用 `scale(.97)`，Popover 从触发方向展开，Dialog 从中心出现。
- 动态 UI 使用可中断 transition；不使用 bounce、装饰性入场或整页 stagger。
- 支持 `prefers-reduced-motion`。

## Current Direction

**Clean / Soft / Neutral / Calm / Technical / Refined**

Plume 启发集中在轻边界、内容优先、青蓝强调、深灰 Dark Mode 与 Blog / Docs 气质；Dashboard 扩展了更紧凑的工具栏、KPI、图表、活动流和数据表格。
