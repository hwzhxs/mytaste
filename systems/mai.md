# Copilot Design System (MAI)

> 提取自 Figma: DS — UI Kit (yl0JWRJAe6Wyt6J0fL5muY)
> 版本: 2026.03.18
> 做 Copilot / Edge Mobile / MAI 项目 UI 时，遵循这个文件。

## 概览

两层 token 架构：
- **Copilot Static**（498 变量）— 原始色板，不随主题变化
- **Copilot Theme**（383 变量）— 语义化 token，Light/Dark 两个 mode，引用 Static

### 色系（18 系，每系 16 阶：100-900）

| 色系 | 色调 | 典型用途 |
|------|------|---------|
| **Stone** | 暖灰（#f8f4f1 → #14110e） | 背景、中性表面 |
| **Cocoa** | 暖棕（#fff3ea → #17100a） | 强调、品牌暖色 |
| **Caramel** | 焦糖橙（#fee6d4 → #18100a） | Accent 强调 |
| **Slate** | 冷蓝灰（#f1f5ff → #0f1119） | 信息、辅助 |
| **Midnight** | 深蓝（#f1f5ff → #0e111b） | 深色背景、Dark mode |
| **Neutral** | 纯灰（#fafafa → #0f0f0f） | 通用中性 |
| **Pink** | 粉（#fff1f4 → #1c0c11） | 状态/标签 |
| **Red** | 红（#fff2f0 → #1c0c0b） | 错误/危险 |
| **Orange** | 橙（#fff3ea → #1b0e05） | 警告 |
| **Yellow** | 黄（#fff4de → #171104） | 注意 |
| **Lime** | 黄绿（#f2f9e0 → #101305） | — |
| **Green** | 绿（#e7fce9 → #09150a） | 成功 |
| **Teal** | 青（#ddfcfe → #021517） | — |
| **Cyan** | 浅蓝（#ebf7ff → #05131c） | — |
| **Blue** | 蓝（#eff6ff → #09121e） | 链接、信息 |
| **Purple** | 紫（#f5f3fe → #120f1d） | — |
| **Alpha** | 透明度（52 个白色/黑色 alpha 值）| 叠加层 |

## 语义化 Theme Token（Light / Dark）

### Background

| Token | Light | Dark | 用途 |
|-------|-------|------|------|
| Background/100 | #fffbf8 | #0f1119 | 最浅背景 |
| Background/150 | #f8f4f1 | #171a25 | App 主背景 |
| Background/200 | #efeae7 | #1f2431 | 卡片/区块 |
| Background/250 | #e2ddd9 | #282d3e | 悬停态 |
| Background/300 | #cfc9c5 | #333a4e | 分隔区 |
| Background/800 | #272320 | #e5ebfa | 深色文字背景 |
| Background/900 | #14110e | #fbfcfe | 最深 |
| App/Sidebar | #efeae7 | #0e111b | 侧边栏 |

### Accent（Light: Caramel 暖橙 → Dark: Midnight 冷蓝）

| Token | Light | Dark | 用途 |
|-------|-------|------|------|
| Accent/450 | #a25a02 | #4458a0 | 主强调（Light 暖橙，Dark 冷蓝） |
| Accent/550 | #8a4b01 | #5369b6 | — |
| Accent/600 | #7f4400 | #798fd4 | — |
| Accent/700 | #582f03 | #b7c9fe | 反转强调 |

**关键特征：Light 用暖色 Accent（Caramel 焦糖），Dark 用冷色 Accent（Midnight 蓝）。这不是简单反色。**

### Stroke

| Token | Light | Dark | 用途 |
|-------|-------|------|------|
| Stroke/Default/200 | #f6e8dd | #232c49 | 默认边框（暖色调） |
| Stroke/Default/450 | #87674e | #5369b6 | 强边框 |
| Stroke/Muted/200 | #efeae7 | #282d3e | 柔和分隔线 |
| Stroke/Muted/300 | #cfc9c5 | #3e4760 | 中等分隔线 |

### Page 背景渐变

| 页面 | 渐变 Stop 0 → 1 → 2 (Light) |
|------|------|
| Home (Mobile) | #f8f4f1 → #fcf3ea → #fef3ea |
| Chat | #f8f4f1 → #f8f4f1 → #fef3ea |
| Intro | #f1f5ff → #f9fcff → #fff4de |
| Onboarding (Web) | #efeae7 → #f4f6f6 → #bbe5ff |

### Acrylic 效果

| 参数 | Light | Dark |
|------|-------|------|
| Default Tint Opacity | 70% | 80% |
| Default Luminosity | 50% | 80% |
| Default Saturation | 10% | 10% |
| Thin Tint Opacity | 60% | 50% |

## 设计特征

1. **暖色基调** — Stone 系暖灰作为主要背景，不是冷灰
2. **Light/Dark 不对称** — Light 用 Caramel（暖橙）Accent，Dark 用 Midnight（冷蓝）Accent
3. **Page 渐变** — 每个页面有 2-3 stop 渐变背景，不是纯色
4. **Acrylic 材质** — 使用毛玻璃效果，Light/Dark 参数不同
5. **16 阶色阶** — 100 到 900（跳过 500），比标准 10 阶更细腻

## 组件列表（从 Figma 页面）

Button, Card, Avatar, Badge, Banner, Chat Message, Composer, Chip, Checkbox, Radio, Toggle Switch, Input Field, Toast, Tooltip, Tabs, List Item, Menu, Dialog/Sheet, Side Nav, Side Pane, Page Header, Toolbar, Segmented Switch, Coachmark, Data Viz, Loading/Progress, Notification, Settings, Camera, Connectors, Citation Attribution, Chain of Thought (CoT), Account Control, Page Fade
