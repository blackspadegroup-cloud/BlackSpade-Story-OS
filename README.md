# Story OS — 故事操作系统

## 项目定位

一套可以持续生产高质量中文 AI 短剧的创作操作系统。

不是写一部短剧。而是建立一个可以不断复制、扩展、维护的 IP Universe。

未来所有故事都会基于 Story OS 运作。

---

## 当前项目

《命运早已写好答案》

- **类型**：现代都市 / 办公室 / 爱情 / 命运 / 成长
- **目标受众**：中国短剧观众（红果、抖音、快手等平台）
- **语言**：所有正式文档全部使用简体中文

---

## AI 团队架构

| 角色 | 负责人 | 职责 |
|------|--------|------|
| Executive Producer | Steve | 最终决策 |
| Creative Director | ChatGPT | 世界观、人物、剧情、Hook、创意审查 |
| Project Orchestrator | Cato（你） | 维护 Story OS、更新 Obsidian、管理 Git、一致性检查 |
| Builder | Claude Code | 创建/修改 Markdown、更新 Repository、自动化任务 |

---

## 工作原则

1. **Creative Discussion ≠ Repository** — 聊天只是讨论，只有 Creative Spec 才进入 Story OS
2. **任何修改必须同步** — 修改一个文件必须检查所有相关文件是否需要同步更新
3. **冲突不自行修改** — 记录冲突，等待 Steve 决策

|---

## 文件结构

完整的结构定义请参见架构文档：[[00_KERNEL/003_ARCHITECTURE.md|BSOS Repository Architecture]]

> **核心原则**：BSOS 采用六层架构 — Kernel → Foundations → IP Universe → Production → Assets → Archive。
> 每个 IP 完全独立（水平扩展），不可变核心与可变内容分离。

---



## Single Source of Truth

**Obsidian Vault** 是项目唯一真相。

聊天记录不是最终版本。任何正式内容都必须同步进入 Obsidian。

---

## 创作宪法（Canon）核心原则

- Never Explain. Always Reveal.
- 人物创造剧情，不是剧情创造人物
- 爱情只是表层，成长才是真正主线
- 命运（Fate）必须贯穿整个故事
- 所有伏笔都必须有回收
- 没有工具人角色，所有角色都必须有目标
- 每一集必须有 Hook，每三集必须有一次高潮
- 每一个谜团最终必须有答案
- 不要为了反转而反转，所有反转必须符合人物性格
- 所有人物行为必须符合 Character DNA

---

> Story OS 才是整个项目最重要的资产。任何 AI 都可以替换，Story OS 不可以。
