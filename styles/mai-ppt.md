# MAI PPT 设计规范

> 提取自 MAI PPT Template C5.pptx（Rebecca Reese, 2025-12）
> 做 PPT / Slide Deck / 数据汇报时，遵循这个文件。

## 色板（Theme Colors — "Custom 16"）

### Primary
| Token | Hex | 用途 |
|-------|-----|------|
| **dk1** | `#5F4E41` | 主文字（暖棕，不是黑色） |
| **lt1** | `#FEF9ED` | 主背景（暖奶白） |
| **accent1** | `#3B230E` | 深棕（最深强调） |
| **accent2** | `#E1DBC6` | 暖沙（边框、分隔线） |
| **accent3** | `#71675B` | 暖灰棕（次要文字、caption） |
| **accent4** | `#EFE2D1` | 暖米（表头背景、卡片底） |
| **accent5** | `#E5B85C` | 金色（数字高亮、Dark 模式强调） |
| **accent6** | `#CC653C` | 橘红（强调、警告、negative 数据） |
| **hlink** | `#2E4D4D` | 深青（链接） |

### Secondary（扩展色）
| Hex | 用途 |
|-----|------|
| `#FFEECC` | 浅金（highlight 底色） |
| `#FDE095` | 中金 |
| `#FBCFB9` | 粉橙 |
| `#E68863` | 中橙 |
| `#E6CAD1` | 粉紫 |
| `#CCA3AD` | 中粉紫 |
| `#FFF2D1` | 暖黄白（深色模式文字） |
| `#FFF9EC` | 极浅暖白 |
| `#754C24` | 焦棕（次级强调） |

### 常用文字色
| 场景 | 色值 |
|------|------|
| 主文字 | `#5F4E41` |
| 次要文字 | `#72675B` |
| 深强调文字 | `#3B230E` |
| 焦棕文字 | `#754C24` |
| 浅底上的 caption | `#5D524B` |
| 深底上的主文字 | `#FFF2D1` |
| 深底上的次要文字 | `#FEF9ED` |
| Positive 数据 | `#434D46`（深绿灰） |
| Negative 数据 | `#CC653C`（橘红） |

## 字体

| 角色 | 字体 | 说明 |
|------|------|------|
| **标题（Major）** | **Georgia** | 衬线体，MAI 品牌标志性字体 |
| **正文（Minor）** | **Segoe UI Semilight** | 半细体，不是 Regular |
| **粗体正文** | **Segoe UI Semibold** | 需要加粗时用 |
| **辅助** | **Segoe UI** / **Segoe Sans** | 标注、footnote |

### 字号参考（从实际使用频率提取）

| 元素 | Georgia | Segoe UI Semilight |
|------|---------|-------------------|
| Hero 数字 | 110pt / 85pt / 75pt | — |
| Slide 主标题 | 65pt / 55pt / 45pt | — |
| 副标题 | 35pt / 30pt / 28pt | 25pt / 23pt |
| 正文 | 25pt / 22pt | 20pt / 18pt |
| 说明文字 | 17pt | 15pt / 14pt |
| Caption / Footnote | — | 12pt / 11pt |
| 极小标注 | — | 8pt |

## Slide Layouts（23 种）

### 封面页
- Title Slide v1 (Brown) — 深棕底
- Title Slide v3 (Oat) — 暖米底
- Title Slide v3 (Brown) — 深棕底变体
- Title Page v4 — 4 种渐变 + Dappled Light 动画（Orange / Orange-Pink / Plum-Orange / Dark Khaki）

### 内容页
- Title Only — 只有标题区域
- Title and Content — 标题 + 内容区
- Page Title Left/Right with Photo — 图文对半

### Section
- Section Header — 章节分隔页

### Blank（8 种底色）
- Brown / Oat / Khaki / Green / Blue / Rose / Orange / Yellow

## 表格样式（从截图提取）

```css
/* MAI PPT 表格 */
table {
  border: 1px solid #E1DBC6;          /* accent2 暖沙边框 */
  border-radius: 8px;
  overflow: hidden;
  border-collapse: collapse;
}
thead th {
  background: #EFE2D1;               /* accent4 暖米 */
  color: #5F4E41;                     /* dk1 主文字 */
  font-family: 'Segoe UI Semilight';
  font-size: 11px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  padding: 10px 16px;
  border-bottom: 2px solid #E1DBC6;
}
tbody td {
  background: #FEF9ED;               /* lt1 主背景 */
  color: #5F4E41;
  padding: 10px 16px;
  border-bottom: 1px solid #E1DBC6;
}
tbody tr:nth-child(even) td {
  background: #FAF5EA;               /* 略深交替行 */
}
tbody td:first-child {
  font-weight: 700;                  /* 第一列加粗 */
}
```

## Layout 设计原理（从 73 页模板深度分析）

### 核心设计哲学

MAI PPT 不是一个"颜色+字体"的皮肤。它是一套**空间关系系统**：
- **Georgia 衬线体**负责"重量感"——标题、数字、锚点
- **Segoe UI Semilight 半细体**负责"轻盈感"——正文、说明、细节
- **暖色调**负责"人文感"——没有冷色，没有纯黑纯白
- **圆角矩形（RoundedRectangle）**是核心组件——不是装饰，是信息容器
- **Connector 分隔线**定义信息分组——永远不在 Page Title 下方

### 基础尺寸
- **Slide 尺寸**: 13.3" × 7.5"（16:9 宽屏）
- **左 margin**: 0.6"–0.7"（统一）
- **右 margin**: 到 12.7"（= 13.3" - 0.6"）
- **内容宽度**: 12.1"（0.6" 到 12.7"）

### 封面页（Title Slide）
```
┌──────────────────────────────────────────────┐
│  Logo (0.7", 0.7")  1.3" × 0.6"             │
│                                              │
│                                              │
│  Title (0.7", 2.5")  11.5" × 2.3"           │
│  Georgia 45-55pt, #5F4E41 or #FFF2D1         │
│                                              │
│                                              │
│  Date (0.7", 6.3")  5.1" × 0.5"             │
│  Segoe UI Semilight 12pt                     │
└──────────────────────────────────────────────┘
```

### 内容页（Page Title + Content）
```
┌──────────────────────────────────────────────┐
│  Page Title (0.6", 0.6")  12.1" × 1.1"      │
│  Georgia 25pt, #5F4E41, 圆角矩形底色         │
│                                              │
│  Content (0.6", 2.3")  12.1" × 4.5"         │
│  Segoe UI Semilight 15-18pt                  │
│                                              │
│                                              │
└──────────────────────────────────────────────┘
```

关键特征：
- **Page Title 在圆角矩形里**（RoundedRectangle），0.6" top，12.1" 宽，1.1" 高
- **Content 从 2.3" 开始**，高 4.5"
- **Title 和 Content 之间间距 ~0.6"**

### 两栏内容页
```
┌──────────────────────────────────────────────┐
│  Page Title (0.6", 0.6")  12.1" × 1.1"      │
│  Section A (0.6", 1.9")    Section B (6.8")  │
│  ──────────────             ──────────────    │
│  Content A (0.6", 2.7")   Content B (6.8")   │
│  6.0" × 4.3"              6.0" × 4.3"       │
│                                              │
└──────────────────────────────────────────────┘
```
- 左栏: 0.6" → 6.6"（宽 6.0"）
- 右栏: 6.8" → 12.8"（宽 6.0"）
- Section Title + 分隔线在 content 上方

### 三栏内容页
```
┌──────────────────────────────────────────────┐
│  Page Title (0.6", 0.6")  12.1" × 1.1"      │
│  Sec A (0.6")    Sec B (4.7")    Sec C (8.8")│
│  ────────        ────────        ────────     │
│  4.0" × 4.3"    4.0" × 4.3"    4.0" × 4.3"  │
│                                              │
└──────────────────────────────────────────────┘
```
- 三栏: 0.6" / 4.7" / 8.8"，每栏宽 4.0"
- Section Title 上方有分隔线

### 四栏卡片页（01/02/03/04 格式）
```
┌──────────────────────────────────────────────┐
│  Page Title (0.4", 0.6")  12.1" × 1.1"      │
│  01 (0.6")    02 (3.7")   03 (6.8")  04(10") │
│  ────────     ────────    ────────   ──────   │
│  Title        Title       Title      Title    │
│  ┌──────┐   ┌──────┐   ┌──────┐  ┌──────┐   │
│  │Card  │   │Card  │   │Card  │  │Card  │   │
│  │2.8"w │   │2.8"w │   │2.8"w │  │2.8"w │   │
│  └──────┘   └──────┘   └──────┘  └──────┘   │
└──────────────────────────────────────────────┘
```
- 序号: Georgia 大号（如 50pt）
- 标题: Georgia 中号 + 分隔线
- 卡片: 圆角矩形, 2.8" × 3.0"

### 图文页（Left with Photo）
```
┌──────────────────────────────────────────────┐
│  Title (0.5", 0.6")  5.5" × 2.0"            │
│                           ┌─────────────┐    │
│  Body (0.6", 3.5")        │ Photo       │    │
│  5.4" × 3.7"              │ (6.7", 0.4")│    │
│                           │ 6.2" × 6.7" │    │
│                           └─────────────┘    │
└──────────────────────────────────────────────┘
```

### 通用规则
1. **Page Title 始终在 (0.6", 0.6") 位置**，12.1" 宽，1.1" 高，用圆角矩形
2. **内容区从 Y=2.3" 开始**（Title 下方 ~0.6" 间距）
3. **底部安全区**: 内容不超过 Y=7.1"（底部留 0.4" margin）
4. **Section Title 用分隔线**（Straight Connector）与内容分开
5. **日期/footnote 在 (0.7", 6.3")**

## 页面类型体系（从 73 页归纳出 12 种）

### A. 封面类（3 种）

#### A1. 标准封面
```
Logo 区 (0.7", 0.7")      ← MAI logo 或品牌标识
Title 区 (0.7", 2.5")     ← Georgia 75pt，占据视觉中心
Date 区 (0.7", 6.3")      ← Segoe UI Semilight 25pt
```
- 整页只有 3 个元素，大量留白
- Title 垂直居中偏上（33% 位置）
- 两种底色：Oat（暖白 #FEF9ED）/ Brown（深棕 #3B230E）
- **何时用：** Deck 的第一页

#### A2. 动画封面
- 全屏背景图/动画 + 叠加 Title
- **何时用：** 需要视觉冲击力的开场

#### A3. 章节分隔页（Section Header）
```
左上：大标题 Georgia 85pt (0.8", 0.4")  ← 一个词或短语
右侧：列表 Segoe UI 18pt (8.5", 2.9")  ← 每行一个话题，行间 Connector 分隔
```
- 标题超大（85pt），占左侧 40%
- **何时用：** 章节之间的过渡

### B. 内容类（9 种）

#### B1. 全宽内容页 ⭐ 最常用
```
┌──────────────────────────────────────┐
│ [Page Title] Georgia 45pt           │  圆角矩形，暖米底
│  (0.6", 0.6") 12.1" × 1.1"         │
├──────────────────────────────────────┤
│  Content 区  Segoe UI 16pt          │  圆角矩形容器
│  (0.6", 2.3") 12.1" × 4.5"         │
└──────────────────────────────────────┘
```
- **何时用：** 纯文字、bullet points、单个表格

#### B2. 两栏内容页
```
┌──────────────────────────────────────┐
│ [Page Title]  12.1" × 1.1"          │
├──────────┬───────────────────────────┤
│ Section A │ Section B                │
│ 6.0"×4.3"│ 6.0"×4.3"               │
└──────────┴───────────────────────────┘
```
- Section Title: Georgia 25pt #72675B + 分隔线
- **何时用：** 对比两组数据、两个维度

#### B3. 三栏内容页
- 三等分，每栏 4.0" 宽
- **何时用：** 三个并列的发现/指标

#### B4. 四栏内容页
- 四等分，每栏 3.0" 宽，字号缩至 14pt
- **何时用：** 四个并列指标

#### B5. 四栏卡片页
```
序号 Georgia 45pt → Connector → 标题 Georgia 20pt → 卡片 2.8"×3.0" Segoe UI 14pt
```
- **何时用：** 列举 3-4 个核心发现/原则/步骤

#### B6. 状态报告页
```
三行：going well / not going well / what's next
左 label Georgia 28pt (3.7" 宽) + 右 content Segoe UI 15pt (8.0" 宽)
全宽 Connector 分隔各行
```
- **何时用：** 项目状态更新、回顾总结

#### B7. 数据展示页
```
标题缩小为 Georgia 35pt（让位给数字）
巨型数字 Georgia 115pt 横排 2-3 个
说明 Segoe UI 23pt
```
- **何时用：** 展示 2-3 个核心 hero 数字

#### B8. 表格+分区页
```
左侧 Section Title Georgia 30pt（圆角矩形里）
右侧 Table，Connector 分隔上下两组
```
- **何时用：** 分组数据表、对比两个 cohort

#### B9. 图表+数字页
```
左侧色块（1/3 宽）+ 大数字 Georgia 75pt
右侧图表（2/3 宽）
```
- **何时用：** 趋势图 + 核心指标

### C. 图文类（4 种）
- **Left with Photo**: 左文右图，图占 47%
- **Right with Photo**: 右文左图，图全出血
- **Multi Photo**: 左文 + 右侧多图拼贴
- **Bottom Photo**: 顶部文字 + 底部全宽横图

## 关键设计规则

### 圆角矩形的使用规则
- **Page Title** 永远在圆角矩形里（暖米底 #EFE2D1）
- **Content 区**也在圆角矩形里（可能无底色，只是容器）
- **Section Title** 有时在圆角矩形里（Georgia 30pt）
- 圆角矩形不是装饰，是**信息容器**——定义信息边界

### 分隔线的使用规则
- Section Title 下方、行与行之间
- **从不在 Page Title 下方**——靠圆角矩形自身边界分隔
- 颜色: #E1DBC6

### 字号层级
```
115pt → 巨型数字（ATH, 20B）
85pt  → 章节封面标题
75pt  → 封面主标题 / 图表数字
55pt  → 内容页大标题（特殊强调）
45pt  → Page Title（标准）/ 卡片序号
35pt  → Page Title（数据展示页，让位给数字）
30pt  → Section Title（圆角矩形里）
28pt  → 状态报告标签
25pt  → Section Title（分隔线上方）
23pt  → 数字说明文字
20pt  → Subtitle
18pt  → 正文（Agenda 列表）
16pt  → 正文（内容页）
15pt  → 正文（bullet points）
14pt  → 正文（四栏，空间紧凑时）
12pt  → Caption
```

## 设计原则

1. **Georgia 做标题，Segoe UI Semilight 做正文** — 衬线 + 无衬线的经典搭配
2. **暖色调贯穿** — 没有纯黑（用 `#5F4E41`），没有纯白（用 `#FEF9ED`）
3. **金色 `#E5B85C` 做数字高亮** — 不用蓝色或红色
4. **Left-aligned 为主** — 标题左对齐，居中只用于封面和 Section Header
5. **表格用交替行底色** — 不用 zebra stripe 的灰色，用暖白交替
6. **深色页用 `#3B230E` 底** — 深棕，不是纯黑
7. **深色页上的文字用 `#FFF2D1`** — 暖黄白，不是纯白
8. **一页一个焦点** — Hero 数字独占一页，不混搭其他内容
9. **Page Title 用圆角矩形包裹** — 不是裸文字，是有底色的 banner
10. **Section Title 下方有分隔线** — 用 Straight Connector 而非边框

## 页面类型速查（12 种）

### 封面类
| 类型 | 何时用 | 标题字号 |
|------|--------|---------|
| 标准封面 | Deck 第一页 | Georgia 75pt |
| 动画封面 | 需要视觉冲击力 | Georgia 75pt |
| 章节分隔 | Act 之间过渡 | Georgia 85pt |

### 内容类
| 类型 | 何时用 | 结构 |
|------|--------|------|
| 全宽内容 | 单个表格、bullet points | Page Title banner + 全宽 Content |
| 两栏 | 对比两组数据/维度 | Page Title + 左右各 6.0" |
| 三栏 | 三个并列发现 | Page Title + 三个 4.0" |
| 四栏 | 四个并列指标 | Page Title + 四个 3.0"（字号缩至 14pt） |
| 四栏卡片 | 列举核心原则/步骤 | 序号(45pt) + 标题 + 卡片 |
| 数据展示 | 2-3 个 hero 数字 | 标题缩小(35pt)，数字放大(115pt) |
| 表格+分区 | 分组数据对比 | 左标签(30pt) + 右表格 |
| 图表+数字 | 趋势 + 核心指标 | 左色块(1/3)+数字，右图表(2/3) |
| 状态报告 | 回顾/总结 | 三行：well / not well / next |

### 选择逻辑
```
内容是什么？
├─ 1-2 个大数字 → B7 数据展示页
├─ 一张表格 → B1 全宽 或 B8 表格+分区
├─ 对比两组 → B2 两栏
├─ 3-4 个并列 → B3/B4/B5 三栏/四栏/卡片
├─ 引述/quote → B1 改居中，大量留白
├─ 趋势图+数字 → B9 图表+数字
└─ 章节过渡 → A3 Section Header
```
