# 🎨 Taste — 小松的设计品味库

跨设备、跨 Agent 共享的个人审美偏好系统。

## 这是什么？

这个仓库存储了我的设计品味 — 喜欢什么风格、讨厌什么模式、字体配色偏好、参考图库等。任何 AI Agent（Claude Code、Cursor、Copilot）在做设计时都可以读取这里的内容，做出符合我审美的作品。

## 快速开始

**Agent 读这个文件**：[TASTE.md](./TASTE.md) — 核心偏好浓缩版

**人类浏览目录**：
- `principles/` — 设计原则（字体、配色、布局等）
- `styles/` — 可复用的风格包
- `references/` — 参考图库（截图 + 描述）
- `components/` — 组件级偏好
- `anti-patterns.md` — 明确不要的东西
- `projects/` — 项目特定的 taste 覆盖

## 使用方式

### 在 Claude Code 中
taste-apply skill 会在设计任务时自动触发，读取 TASTE.md。

### 在其他 AI 工具中
在 prompt 或 rules 文件中添加：
```
设计时请参考 ~/taste/TASTE.md 中的偏好
```

### 在新电脑上
```bash
cd ~ && git clone git@github.com:hwzhxs/mytaste.git taste
```

## 演进方式

这个库是**渐进式积累**的 — 不是一次写好，而是每次做完设计项目，把喜欢的决策沉淀进来。

1. 做项目时 Agent 读 taste → 应用偏好
2. 做完后 review → 新的好偏好存入 taste
3. 踩坑的 → 加到 anti-patterns
4. 完整的风格 → 提炼为 style pack
