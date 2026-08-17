# Northstar UI Style

一组用于探索和沉淀个人前端 UI 风格的原生 HTML 视觉原型。项目关注清爽、克制、偏技术工具的界面体验：以中性色为主，以低饱和强调色建立层级，并在 Blog、Dashboard、组件库和移动端之间验证同一套视觉语言。

## 特征

- 暖象牙白浅色模式（`#fffcf5`）与多层深灰深色模式，避免纯白与纯黑。
- 四套可切换主题色：霁青、陶朱、藕荷、麦金。
- Maple Mono 与系统 Sans Serif 的三档字体实验；当前默认方案为 Maple Heavy，长正文仍优先 Sans Serif。
- 统一的 2px 选中态边界、2px 图标描边、圆端点与清晰的 SVG 点状细节。
- 页面级主题过渡，以及星点 / 云朵主题切换动效；支持 `prefers-reduced-motion`。
- 原生 HTML、CSS 与少量 JavaScript，无构建工具依赖。

## 页面

| 文件 | 用途 |
| --- | --- |
| [examples/dashboard.html](examples/dashboard.html) | 验证 Sidebar、工具栏、KPI、图表、活动流与数据表格的信息密度。 |
| [examples/blog.html](examples/blog.html) | 验证 Blog / Docs 的阅读节奏、文章元数据、代码块与内容层级。 |
| [examples/components.html](examples/components.html) | 集中展示组件、关键状态、主题和字体实验。 |
| [examples/mobile.html](examples/mobile.html) | 验证同一视觉语言在移动端任务应用中的适配。 |

## 本地预览

这些页面均可直接在浏览器打开。若需要从同源路径加载本地字体，建议在项目根目录启动静态服务器：

```powershell
python -m http.server 8000
```

随后访问：

```text
http://127.0.0.1:8000/examples/dashboard.html
```

其他示例只需替换 URL 中的文件名。

## 项目结构

```text
.
├── examples/                         # 四个独立可预览的 HTML 原型
├── assets/font/maple-mono/           # 本地 Maple Mono WOFF2 字体
├── .agents/skills/northstar-ui-prototype/
│   └── SKILL.md                       # 可复用的 Northstar UI 风格工作指南
├── Prompt.md                         # 第一轮视觉探索要求
├── Font-Promet.md                    # 字体实验要求
└── STYLE_NOTES.md                    # 当前视觉决策与实验笔记
```

## 使用约定

- 这是视觉原型项目，不是组件库、npm 包或正式设计系统。
- 页面优先保持单文件结构，便于快速预览、反馈与修改。
- 修改视觉与交互时，请参考 [STYLE_NOTES.md](STYLE_NOTES.md)；需要延续当前风格时，使用项目内的 `northstar-ui-prototype` Skill。
- 主题和字体偏好会保存在浏览器 localStorage 中，可在浏览器开发者工具中清除站点数据以恢复默认状态。

## 当前方向

**Clean / Soft / Neutral / Calm / Technical / Refined**

灵感来自轻边界、内容优先和低饱和青蓝的 Blog / Docs 气质，并扩展为适用于 Dashboard、通用 Web App 与移动端的统一原型语言。
