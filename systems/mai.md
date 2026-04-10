# MAI Design System — Edge Mobile

> 提取自 SongClub/personal/projects/edge-mobile/context/Design/Design_Language.md + EdgeMobile_Design_Context.md
> 做 Edge Mobile / MAI 项目 UI 时，遵循这个文件。

## 设计哲学

基于 Fluent Design System：Light、Depth、Motion、Material、Scale。
强调柔和光影、微动效反馈、系统一致性、内容聚焦。
目标：高效、信任感、跨设备一致的浏览体验。

## Typography

### Font Families

| 平台 | 主字体 | Fallback |
|------|--------|----------|
| Cross-platform / Windows / Android | Segoe UI | "Helvetica Neue", Arial, sans-serif |
| iOS Titles | SF Pro Display | -apple-system |
| iOS Body | SF Pro Text | -apple-system |

### Type Scale (iOS)

| Token | Size | Weight | Line Height | Usage |
|-------|------|--------|-------------|-------|
| ios.largeTitle.bold | 34px | 700 | 41px | Screen title |
| ios.title1.bold | 28px | 700 | 34px | Major section header |
| ios.title2.semibold | 22px | 600 | 28px | Sub-header |
| ios.title3.semibold | 20px | 600 | 25px | Card/group header |
| ios.body1.regular | 17px | 400 | 22px | Primary paragraph |
| ios.body2.regular | 15px | 400 | 20px | Secondary text |
| ios.caption1.regular | 13px | 400 | 18px | Metadata |
| ios.caption2.regular | 12px | 400 | 16px | Micro-label |

### Spacing (vertical rhythm, 4px base)

| Style Group | Above | Below |
|-------------|-------|-------|
| Large Title / Title1 | 12-16px | 8-12px |
| Title2 / Title3 | 8-12px | 4-8px |
| Paragraph blocks | 8px | 8px |
| Caption under body | 4px | 8px |

## Color

### Core Tokens (confirmed from Figma)

| Semantic | Hex | Usage |
|----------|-----|-------|
| color.text.primary | #272320 | Primary text / icons |
| color.background.canvas | #f8f4f1 | App canvas / elevated card |
| color.border.subtle | #efeae7 | Light dividers |
| color.background.info.subtle | #d7deef | Info subtle background |
| color.background.info.medium | #c2cadf | Info medium background |
| Primary Blue (Microsoft) | #0078D4 | Primary action color |

### Color Rules

- 暗色模式自适应，不是简单反色
- 浅灰用于背景，深灰用于文本层次
- 图标线性、圆角一致（Fluent Icons）

## Layout

| 元素 | iOS | Android |
|------|-----|---------|
| 底部导航栏高度 | 50pt | 56dp |
| 触控目标最小尺寸 | 44pt | 48dp |
| 控件圆角 | 8dp | 8dp（底部模块 12dp） |

### 动效

| 交互 | 时长 | 曲线 |
|------|------|------|
| 标签切换 | 180-250ms | — |
| Bottom Sheet 弹出/收起 | 240ms | cubic-bezier(0.4, 0, 0.2, 1) |
| 页面切换 | 渐隐/平移 | 方向随导航方向 |

### 交互原则

- Thumb-first：主要操作在底部，拇指可达
- Progressive disclosure：不一次展示所有功能
- 手势支持：滑动切换、手势关闭
