---
title: "BSOS Production Package (BPP) Standard v1.0"
type: reference
version: 1.0
status: active
created: 2026-07-04
author: Cato (BSOS Guardian) — Directed by Creative Director (ChatGPT)
tags: [bsos, production, bpp, template, standard]
canon_level: core
---

# BSOS Production Package (BPP) Standard v1.0

> BPP 是 BSOS Episode 的唯一交付标准与唯一资料来源（Single Source of Truth）。
> 任何 AI 工具或制作团队，应能直接读取 BPP，完成约 80% 的内容生产。

---

## BPP 原则

1. **Single Source of Truth** — Storyboard、AI Video、Voice、Music、Sound Design、Editing 均不得建立独立版本。所有生产内容统一来源于同一份 BPP。
2. **AI-Ready** — 尽可能做到 Copy → Paste → Generate。减少人工整理。
3. **Human Review Layer** — BPP 覆盖 80% 的生产内容。剩余 20% 由制作团队进行艺术调整与最终审核。

---

## BPP 八模块

每集 BPP 包含以下 8 个模块：

| # | 模块 | 用途 | 目标工具/角色 |
|---|------|------|-------------|
| 1 | Episode Function | 为什么这一集存在？ | 编剧、导演 |
| 2 | Character Language | 本集强化哪些角色语言？ | 演员、AI Character Agent |
| 3 | Director's Cut | 正式剧情版本（Master Script） | 导演、制片 |
| 4 | Cinematography Notes | 摄影指导 | AI Camera Agent、摄影师 |
| 5 | Editing Notes | 剪辑节奏 | AI Editor、剪辑师 |
| 6 | Audio Design | 声音设计 | AI Audio Agent、音效师 |
| 7 | AI Production Notes | AI 生成所需资讯 | AI Video/Image Gen |
| 8 | AI Prompt Pack | 各 AI 工具可直接使用的 Prompt | AI Tools |

---

## BPP Validation Checklist

所有 Episode 必须通过以下检查方可标记为 APPROVED：

```markdown
- ✅ BPP Module 1: Episode Function
- ✅ BPP Module 2: Character Language
- ✅ BPP Module 3: Director's Cut
- ✅ BPP Module 4: Cinematography Notes
- ✅ BPP Module 5: Editing Notes
- ✅ BPP Module 6: Audio Design
- ✅ BPP Module 7: AI Production Notes
- ✅ BPP Module 8: AI Prompt Pack
- ✅ Single Source of Truth（无独立版本）
- ✅ AI Production Ready（Copy → Paste → Generate）
```

---

## 与现有 Episode 的关系

现有 EP-001~EP-012 使用旧版 Episode 格式（仅含剧本 + QA 检查）。这些集数为 Episode 格式 v1.0。

从 **EP-013** 开始，所有新 Episode 必须使用 **BPP 格式 v2.0**。

现有 Episode 不强制回填，但建议在进入 Act 2 前完成 retroactive BPP 升级。

---

## 文件位置

```
03_STORIES/SEASON_01/ACT_01/
├── EP_001.md  ← 旧格式（剧本 + QA）
├── EP_012.md  ← 旧格式
├── EP_013.md  ← BPP 格式 ✅（从这集开始）
└── ...
```

Template: `00_KERNEL/TEMPLATES/TEMPLATE_BPP.md`
