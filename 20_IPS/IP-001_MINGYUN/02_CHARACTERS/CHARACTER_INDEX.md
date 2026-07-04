---
title: "命运早已写好答案 — 角色索引"
ip: IP-001
code: MINGYUN
type: index
version: 2.0
status: active
created: 2026-07-04
updated: 2026-07-04
author: Cato (Project Orchestrator)
tags: [bsos, ip-001, character, index, dataview]
canon_level: core
---

# 角色索引

---

## 用途

本文档为 IP-001「命运早已写好答案」的角色索引。所有角色信息**自动生成**自各角色的 `Character_Snapshot.md` 文件。

> 本索引基于 Obsidian Dataview 插件自动生成。如需查看最新角色列表，请在 Obsidian 中打开本文档并确保 Dataview 插件已启用。

---

## Dataview 自动索引

```dataview
TABLE 
  ch_code AS "编号",
  name AS "姓名",
  role AS "定位",
  archetype AS "原型",
  status AS "状态"
FROM "20_IPS/IP-001_MINGYUN/02_CHARACTERS"
WHERE type = "snapshot"
SORT ch_code ASC
```

---

## 角色类型说明

| 类型 | 描述 |
|------|------|
| **女主角（Main）** | 故事核心女性角色，拥有完整角色弧 |
| **男主角（Main）** | 故事核心男性角色，拥有完整角色弧 |
| **主要配角（Supporting）** | 重要配角，影响主线发展 |
| **次要角色（Minor）** | 功能性角色，推动特定情节 |
| **背景角色（Background）** | 场景填充角色，无需完整档案 |

---

## 角色文档结构

每位角色的文档结构：

```
CH-NNN_NAME/
├── Character_Snapshot.md      ← 角色速查（AI 优先读取）
├── Identity.md                ← Layer 01：身份
├── History.md                 ← Layer 02：历史
├── Core.md                    ← Layer 03：核心（DNA、价值观、原则）
├── Mind.md                    ← Layer 04：思维模式
├── Emotion.md                 ← Layer 05：情感世界
├── Shadow.md                  ← Layer 06：阴影（创伤、恐惧、谎言）
├── Decision_Engine.md         ← Layer 07：决策引擎
├── Behaviour.md               ← Layer 08：行为模式
├── Voice_Engine.md            ← Layer 09：语言引擎
├── Relationship_Engine.md     ← Layer 10：关系引擎
├── Growth_Engine.md           ← Layer 11：成长引擎
├── Performance.md             ← Layer 12：演绎
├── Prompt.md                  ← Output：AI 生成 Prompt
├── Dialogue_Samples.md        ← Output：经典对白样本
└── BIBLE.md                   ← 完整角色圣经
```

详细标准参见 [[00_KERNEL/TEMPLATES/CHARACTER_OS_STANDARD.md|Character OS Standard]]。

---

## 角色关系图

详见 [RELATIONSHIP_GRAPH.md](RELATIONSHIP_GRAPH.md) — 角色关系统览与可视化说明。

---

## 使用说明

> **新角色建立后，只需创建 `CH-NNN_NAME/Character_Snapshot.md` 并填写 frontmatter，本索引将自动更新。**

所有 `Character_Snapshot.md` 必须包含符合标准的 frontmatter 字段。  
字段定义详见 `00_KERNEL/TEMPLATES/REFERENCE_CHARACTER_FRONTMATTER.md`。

---

*角色创建由 Creative Director (ChatGPT) 输出创意规格后，按照 `TEMPLATE_CHARACTER_BIBLE.md` 生成。*
