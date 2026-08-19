# Northstar 设计系统参考

仅在处理 Token、色彩、字体、状态、图标或动效时读取。用户品牌、已有设计系统和可访问性要求优先于本参考。

## 视觉方向

**Clean / Soft / Neutral / Calm / Technical / Refined**。以内容、阅读和操作效率优先；用背景、文字层级和细边界建立层次，不以大面积品牌色、重阴影或装饰性卡片制造层次。

## 默认色彩 Token

```css
/* Light */
--bg: #fffcf5;
--bg-soft: #f5f1e8;
--surface: #fffdfa;
--surface-raised: #fffefb;
--text: #34363b;
--text-2: #62656c;
--text-3: #8a8e95;
--brand: #5086a1;
--brand-hover: #3d6f87;
--brand-active: #315d72;
--brand-soft: #d9eaee;
--brand-soft-strong: #c6e0e6;
--brand-ink: #285a70;

/* Dark */
--bg: #1b1c1f;
--bg-soft: #17181a;
--surface: #202226;
--surface-raised: #27292e;
--text: #e6e8e9;
--text-2: #b5b8bd;
--text-3: #868b92;
--brand: #76a9bc;
--brand-hover: #8db9c9;
--brand-active: #9cc6d3;
```

- 默认主题为霁青：Light `#5086a1`、Dark `#76a9bc`。
- 可选主题的浅色核心：陶朱 `#ad4506`、藕荷 `#b06d88`、麦金 `#b59a2a`。陶朱应醒目而不侵略；藕荷与麦金不要在浅色态加深至棕色或沉闷灰褐。
- 让品牌色表达主操作、链接、选择态和少量数据强调。成功、警告、危险和信息必须保持独立语义，不能随品牌主题失去可区分性。

## 语义状态

- 每个状态均提供前景、柔和背景与边框表达，并在 Light / Dark 分别校准。
- `focus-visible` 使用明确边界或外圈；`selected` 是持久状态，可使用品牌边界与柔和背景；`hover` 仅是短暂反馈，不能伪装为 selected。
- `disabled` 同时降低可操作性与对比，但保留文字可读性；`loading` 保持尺寸稳定，并避免用持续动画表达已选中状态。
- 成功、警告、危险、信息、空状态与错误状态结合图标、文字、边界或形状变化；图标和文字使用同一语义色。

## 字体

```css
--font-ui: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
  "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif;
--font-mono: "Maple Mono", ui-monospace, SFMono-Regular, Menlo, Monaco,
  Consolas, "Liberation Mono", monospace;
```

- Maple Mono 只使用 400 / 600 / 700；验证字体资源、实际渲染器、字重、中英文回退和等宽对齐，而非只检查 CSS 声明。
- **Sans First**：Mono 只用于代码、路径、版本、ID、数值技术信息。
- **Maple Accent**：额外用于站点名、KPI、技术元数据、日期、短标签和技术标题。
- **Maple Heavy**（默认实验方案）：额外用于导航、按钮、Tabs、Badge、表格与短标题。
- 所有模式下，Blog / Docs 正文、中文长段落和长说明保持 Sans。正文行高约 `1.5–1.82`；数字指标使用 tabular figures。

## 形状、边界与密度

- 圆角节奏为 `6 / 10 / 14px`；按钮与输入通常 `8px`。Badge 可用 pill，但普通 Tag 保持 `6px` 圆角。
- 默认分隔为低对比 1px。所有可选择、聚焦或选中的带边框元素使用单层 2px 品牌边界；不要叠加第二层边框、outline 或 shadow。
- 图标约为 2px 描边、圆端点、圆连接。问号、感叹号、省略号等点状细节应使用实心圆或可见圆端点。
- 常规 Card 无阴影；阴影只用于 Dropdown、Toast、Dialog 与必要浮层。
- 使用 4 / 8px 间距节奏，优先取 `8 / 12 / 16 / 24 / 32 / 48 / 64px`。

## 动效

- Hover / press 约 125–180ms，Dialog 约 200ms，采用可中断的强 ease-out；按钮按下可使用 `scale(.97)`。
- 精确指针设备上的链接可在 120–140ms 内轻微 `scale(1.015)` 并高亮；触摸设备和减少动态效果时不缩放。
- 主题切换使用短暂的页面色彩交叉过渡，页面内容保持可见。可选表现：浅转深时星点错峰进入后低幅漂浮；深转浅时云朵进入后低幅漂浮。
- 主题开关的非激活太阳或月亮应弱化并位于装饰元素之后；不要让其遮挡星点或云朵。
- 不使用 bounce、无意义整页 stagger 或持续装饰性入场。所有关键动效在 `prefers-reduced-motion` 下静态退化。
