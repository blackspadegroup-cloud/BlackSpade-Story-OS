---
title: "BSOS 名词词典（Glossary）"
work_order: BSOS-0-004
type: glossary
version: 1.0
status: active
created: 2026-07-04
author: Cato (BSOS Guardian)
tags: [bsos, foundation, glossary, reference]
canon_level: immutable
---

# BSOS 名词词典

## 如何使用本词典

本词典是 BSOS 的**统一语言规范**。

- 所有 BSOS 文件必须使用本词典定义的术语
- 未来新增术语必须先加入本词典，方可正式使用
- 任何 AI 进入 BSOS 前，应优先阅读本词典

---

## 核心概念

### Story OS（故事操作系统）
一个可以持续生产高质量中文 AI 短剧的创作操作系统。不是写一部短剧，而是建立可以不断复制、扩展、维护的 IP Universe。
> 参见：[[000_BSOS_PROTOCOL.md|BSOS Protocol]]

### BSOS（BlackSpade Story OS）
BlackSpade 故事操作系统的正式缩写。整个公司的核心创作基础设施。
> 不可替换的核心资产。

### BlackSpade Foundation（黑桃基石）
BSOS 的第一层。包含 Protocol、黑桃之道、创作宪法、名词词典四份核心文件。是所有上层建筑的基础。
> 参见：[[001_THE_BLACKSPADE_WAY.md|黑桃之道]]、[[002_CREATION_CONSTITUTION.md|创作宪法]]

### BSOS Guardian（BSOS 守护者）
负责维护 BSOS 完整性、一致性与长期可持续发展的人（AI 角色）。不是创作者，是系统维护者。
> 职责：Repository Architecture、Knowledge Management、Canon Consistency、Workflow Enforcement、Version Management

---

## 工作系统

### Work Order（工作指令）
BSOS 的正式工作任务。每个 Work Order 拥有唯一编号（BSOS-[category]-[NNN]），一经建立即成为系统生命周期的一部分。
> 格式：`BSOS-0-001`、`BSOS-3-018`
> 参见：[[000_BSOS_PROTOCOL.md#work-order-protocol|Work Order Protocol]]

### PCB（Project Context Brief，项目上下文简报）
每次新工作开始前，由 BSOS Guardian 自动准备的项目上下文。包含当前项目、版本、Work Order、近况、潜在冲突、建议阅读文件。所有 AI 在开始工作前应优先阅读 PCB。
> 未来所有 AI 的长期记忆来自 Obsidian Repository，而不是对话历史。

### Creative Spec（创意规格）
ChatGPT 产出的正式创意内容。区别于日常讨论。只有 Creative Spec 才能进入 BSOS Repository。

### Creative Discussion（创意讨论）
ChatGPT 与 Steve 之间的日常讨论。有价值但不正式。**不得**直接写入 Repository。只有经过整理、审核的 Creative Spec 才可进入。

### Canon（正典 / 宪法）
BSOS 的最高创作法律。任何角色、剧情、对白、世界观均不得违反。一旦 LOCKED，修改必须通过正式 Work Order。
> 参见：[[002_CREATION_CONSTITUTION.md|创作宪法]]

---

## 角色系统（Character OS）

### Character OS（角色操作系统）
每位角色的完整知识体系。包含 Bible、DNA、Psychology、Relationships、Growth、Dialogue、Prompt。

### Character Bible（角色圣经）
角色的完整档案。包含外观、性格、背景、动机、目标、恐惧、秘密等所有维度。

### Character DNA（角色基因）
角色的核心本质。**不可变**。所有人物行为必须符合 Character DNA。一旦建立，任何修改必须通过 Work Order。

### Character Brain（角色大脑）
角色的思维方式、决策逻辑、情感模式。是 Character DNA 的行为化表达。

### OOC（Out of Character，角色崩坏）
角色行为偏离其 Character DNA 的现象。属于 Canon 违反。如果角色似乎做出不符合 DNA 的行为，故事必须展示**原因**。

---

## 世界观系统（Universe OS）

### Universe OS（世界观系统）
每个 IP 的世界观知识体系。包含 Universe Bible、World Rules、Locations、Organizations、Timeline、History。

### Universe Bible（世界观圣经）
世界观的总纲文件。定义该世界的基础设定、规则体系、核心矛盾。

---

## 故事系统（Story Engine）

### Story Engine（故事引擎）
故事创作的核心系统。包含 Season、Arc、Episode、Hook Map、Foreshadow Map、Payoff Map。

### Hook（钩子）
每一集结尾的悬念/情感/反转/信息。结构法则：**每一集必须有 Hook**。

### Cliffhanger（悬念钩）
一种特定类型的 Hook。在关键处中断，迫使观众追看下一集。

### Cold Open（冷开场）
在片头/标题出现之前直接进入剧情。通常用于快速建立氛围或悬念。

### Foreshadow（伏笔）
预先埋设的线索。所有伏笔都**必须**有回收。

### Payoff（回收 / 呼应）
伏笔的兑现。每一个谜团最终必须有答案。

### Story Arc（剧情弧）
一个完整的故事段落。通常包含多条 Episode，具有独立的起承转合。

### Romance Engine（爱情引擎）
情感线的驱动系统。爱情是表层，成长才是真正主线。

---

## 制作系统（Production OS）

### Production OS（制作系统）
将剧本转化为成品短剧的制作体系。包含 Storyboard、Camera Language、Image Prompt、Video Prompt、Voice、Subtitle、Editing Notes。

### Storyboard（分镜图）
以图像或文字描述每一镜头的画面构成、运镜方式、人物位置。

### Shot List（镜头清单）
每一集的完整镜头列表。包含镜头编号、场景编号、镜头类型、描述、对白、时长。

---

## 工作流相关

### Guardian Protocol（守护者协议）
BSOS Guardian 的检查清单：收到 Work Order 后，检查是否违反 Canon、影响 Character OS、影响 Universe OS、影响 Story Engine。如果发现冲突，建立 Conflict Report 等待 Steve 决策。

### Conflict Report（冲突报告）
当 Guardian 发现 Canon 冲突时建立的正式报告。包含冲突描述、影响范围、建议方案。等待 Executive Producer 决策。

### Change Request（变更请求）
修改 LOCKED 内容的正式流程。必须说明：修改原因、影响范围、Version Upgrade、审批记录。

### Version Bump（版本升级）
当内容发生变更时，对应的版本号提升。遵循 semver 语义化版本规范。

---

## 创意法则

### Never Explain. Always Reveal.（永不解释。永远揭露。）
BSOS 第一创作法则。通过事件揭露人物和真相，而不是通过旁白或对话解释。

### 人物创造剧情（Characters Drive Plot）
BSOS 第二创作法则。Plot is the natural result of characters making choices.

### 命运（Fate）
必须贯穿整个故事的底层脉络。所有伏笔都必须有回收。

### Character DNA（角色基因不可违）
所有人物行为必须符合其 Character DNA。参见 OOC。

---

## 技术术语

### Repository（仓库）
BSOS 的完整文件系统。存储在 Obsidian Vault 中，通过 Git 进行版本管理。

### Obsidian Vault（Obsidian 仓库）
BSOS 的物理存储位置。**Single Source of Truth**。聊天记录不是最终版本。

### SSOT（Single Source of Truth，唯一真相）
BSOS 的最高信息原则。所有正式内容以 Obsidian Repository 为准。

### Frontmatter（前页元数据）
每个 Markdown 文件顶部的 YAML 元数据块。包含 title、type、version、status、canon_level 等字段。

### Canon Level（正典等级）
文件的权威等级：`immutable`（不可修改）、`core`（稳定）、`flexible`（可演化）、`experimental`（实验性，可能废弃）。

---

## 角色与职责

| 角色 | 英文名称 | 职责 |
|------|---------|------|
| 执行制片人 | Executive Producer (Steve) | 最终决策 |
| 创意总监 | Creative Director (ChatGPT) | 世界观、人物、剧情、创意审查 |
| BSOS 守护者 | BSOS Guardian (Cato) | 维护系统完整性、一致性、版本管理 |
| 构建者 | Builder (Claude Code) | 创建文件、修改 Markdown、自动化 |

---

## 如何新增术语

1. 确认该术语尚未存在于本词典
2. 按照以下格式添加：

```markdown
### 术语名称（English Term）
清晰的定义。说明用途和上下文。
> 参见：关联文件
```

3. 在相关文件中开始使用该术语
4. 术语进入 BSOS 后，所有文件必须统一使用，不得混用别名

---

*本词典是 BSOS Foundation 的一部分。新增术语须经 BSOS Guardian 确认。*
*最后更新：2026-07-04*
