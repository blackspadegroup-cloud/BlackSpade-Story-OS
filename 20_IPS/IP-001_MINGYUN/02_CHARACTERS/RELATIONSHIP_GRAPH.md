---
title: "命运早已写好答案 — 关系图谱"
type: relationship_graph
ip: IP-001
version: 1.0
status: draft
created: 2026-07-04
author: Cato (BSOS Guardian)
tags: [bsos, ip-001, character, relationship]
canon_level: core
---

# 命运早已写好答案 — 关系图谱

> **本文件是 IP-001 MINGYUN 所有角色关系图谱的单一真相源（Single Source of Truth）。**
>
> 所有角色文件中的 `RELATIONSHIPS.md` 均以此图谱为权威引用。

---

## 1. 图谱目的

| 维度 | 说明 |
|------|------|
| **一致性** | 确保所有角色关系在整个 IP 中保持一致，避免矛盾 |
| **可视化** | 通过 Obsidian [[双向链接]] 实现完整的关系图谱（Graph View）和画布（Canvas） |
| **可追溯** | 记录每段关系的引入季节、强度变化和当前状态 |
| **可查询** | 通过 Dataview 插件将表格数据转化为动态查询，支持跨文件筛选 |
| **可扩展** | 扁平表格结构支持 300+ 角色的关系网络，不会因规模增长而崩溃 |

---

## 2. 关系类型分类（Taxonomy）

| 类型 | 代号 | 说明 |
|------|------|------|
| **浪漫关系** | `romantic` | 恋爱、爱情、婚姻关系（含暗恋、暧昧、前任） |
| **家庭关系** | `familial` | 血缘、收养、寄养等家庭纽带 |
| **敌对关系** | `antagonistic` | 敌人、对手、仇人、理念冲突导致的对抗 |
| **师徒关系** | `mentor` | 师徒、师生、指导与被指导 |
| **友谊关系** | `friend` | 朋友、挚友、知己、战友 |
| **竞争关系** | `rival` | 良性/恶性竞争、宿命对手 |
| **职业关系** | `professional` | 同事、上下级、合作伙伴、雇佣关系 |
| **复杂关系** | `complex` | 无法简单归类的多维关系（如亦敌亦友、相爱相杀） |

> **注意：** 每段关系应选择**最接近**的一种类型。若关系具有多重性质，在「演化记录」栏说明其他维度，Type 栏保留主类型以保持查询一致性。

---

## 3. 主关系表

| 关系 ID | 角色 A | 关系类型 | 角色 B | 强度 | 引入季节 | 当前状态 | 演化记录 | 关键剧情引用 |
|---------|--------|----------|--------|:----:|:--------:|:---------:|----------|--------------|
| REL-001 | [[CH-001_LINYUXUAN]] | `romantic` | [[CH-002_GUMUYI]] | 8 | S1 | evolving | S1: 初遇 — 命运般的邂逅，互相吸引但未表白<br>S2: 确认关系 — 经历考验后正式在一起<br>S3: 危机 — 外部压力导致关系紧张 | S1E05, S1E12, S2E01, S2E08 |
| REL-002 | [[CH-001_LINYUXUAN]] | `familial` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-003 | [[CH-002_GUMUYI]] | `familial` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-004 | [[CH-001_LINYUXUAN]] | `friend` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-005 | [[CH-002_GUMUYI]] | `friend` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-006 | [[CH-001_LINYUXUAN]] | `antagonistic` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-007 | [[CH-002_GUMUYI]] | `antagonistic` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-008 | [[CH-001_LINYUXUAN]] | `mentor` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-009 | [[CH-002_GUMUYI]] | `mentor` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-010 | [[CH-001_LINYUXUAN]] | `professional` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-011 | [[CH-002_GUMUYI]] | `professional` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-012 | [[CH-001_LINYUXUAN]] | `rival` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-013 | [[CH-002_GUMUYI]] | `rival` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-014 | [[CH-001_LINYUXUAN]] | `complex` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-015 | [[CH-002_GUMUYI]] | `complex` | [[CH-NNN_NAME]] | — | — | planned | — | — |

> **表注：**
> - 「强度」列：1–10 分制（1 = 微弱联系，10 = 命运羁绊）
> - 「引入季节」列：S1 / S2 / S3 … 表示关系首次出现的季节
> - 「当前状态」列：`active`（活跃）/ `resolved`（已解决）/ `dormant`（休眠）/ `evolving`（演化中）/ `planned`（待创建）
> - 「演化记录」列：按季节记录变化，格式为 `S<数字>: <描述>`
> - 「关键剧情引用」列：引用具体集数或章节，格式为 `S<季>E<集>`

### 列说明

| 字段 | 格式/规范 |
|------|-----------|
| **关系 ID** | `REL-NNN`（三位数字，从 001 开始） |
| **角色 A / 角色 B** | `[[CH-NNN_CODE]]` — 使用 Obsidian 内链，必须指向已存在的角色文档 |
| **关系类型** | 使用下方「关系类型分类」中的代号（如 `romantic`） |
| **强度** | `1-10` 整数，仅填写已确认的关系 |
| **引入季节** | `S1`, `S2`, `S3` ... |
| **当前状态** | `active` / `resolved` / `dormant` / `evolving` / `planned` |
| **演化记录** | 多行文本，每行 `S<数字>: <内容>` |
| **关键剧情引用** | 逗号分隔的引用，如 `S1E05, S2E01` |

---

## 4. 初始数据行（CH-001 & CH-002）

以下行为 CH-001（林雨萱）和 CH-002（顾穆一）的预留关系数据行，随角色文档创建后填充：

| 关系 ID | 角色 A | 关系类型 | 角色 B | 强度 | 引入季节 | 当前状态 | 演化记录 | 关键剧情引用 |
|---------|--------|----------|--------|:----:|:--------:|:---------:|----------|--------------|
| REL-001 | [[CH-001_LINYUXUAN]] | `romantic` | [[CH-002_GUMUYI]] | 8 | S1 | evolving | S1: 初遇 — 命运般的邂逅，互相吸引但未表白<br>S2: 确认关系 — 经历考验后正式在一起<br>S3: 危机 — 外部压力导致关系紧张 | S1E05, S1E12, S2E01, S2E08 |
| REL-016 | [[CH-001_LINYUXUAN]] | — | 待填充 | — | — | planned | — | — |
| REL-017 | [[CH-001_LINYUXUAN]] | — | 待填充 | — | — | planned | — | — |
| REL-018 | [[CH-001_LINYUXUAN]] | — | 待填充 | — | — | planned | — | — |
| REL-019 | [[CH-002_GUMUYI]] | — | 待填充 | — | — | planned | — | — |
| REL-020 | [[CH-002_GUMUYI]] | — | 待填充 | — | — | planned | — | — |
| REL-021 | [[CH-002_GUMUYI]] | — | 待填充 | — | — | planned | — | — |

---

## 5. 图谱维护指南

### 5.1 添加新关系

1. 分配唯一 `REL-NNN` ID（取当前最大 NNN + 1）
2. 在表格中添加一行
3. 确保角色 A 和角色 B 的 [[链接]] 指向正确的角色文档（若角色尚未创建，使用 `[[CH-NNN_NAME]]` 占位）
4. 填写关系类型、强度、引入季节
5. 在相关角色的 `RELATIONSHIPS.md` 中添加对应条目

### 5.2 更新已有关系

1. 找到对应 `REL-NNN` 行
2. 更新「演化记录」列 — 在末尾追加新季节记录，不删除历史
3. 更新「当前状态」列（如 `active` → `evolving` → `resolved`）
4. 更新「强度」列（若关系亲密度变化）
5. 在「关键剧情引用」中添加新集数

### 5.3 删除/归档关系

- **不删除行。** 将「当前状态」改为 `resolved` 或 `dormant`
- 在「演化记录」中标注结束原因和季节

### 5.4 Dataview 查询示例

将此文件与 Dataview 插件配合使用，示例查询：

```dataview
TABLE
  rows.强度 as "强度",
  rows.关系类型 as "类型",
  rows.当前状态 as "状态",
  rows.引入季节 as "引入"
FROM "20_IPS/IP-001_MINGYUN/02_CHARACTERS/RELATIONSHIP_GRAPH"
WHERE 关系类型 = "romantic" AND 当前状态 = "active"
SORT 强度 DESC
```

```dataview
TABLE
  rows.演化记录 as "演化记录",
  rows.关键剧情引用 as "关键剧情"
FROM "20_IPS/IP-001_MINGYUN/02_CHARACTERS/RELATIONSHIP_GRAPH"
WHERE contains(角色A, "CH-001") OR contains(角色B, "CH-001")
```

### 5.5 与角色 RELATIONSHIPS.md 的关系

```
RELATIONSHIP_GRAPH.md (单一真相源)
        ↑ 引用        ↓ 同步
每个角色的 RELATIONSHIPS.md (角色视角的视图)
```

- `RELATIONSHIP_GRAPH.md` 是完整的关系图谱，包含所有关系
- 各个角色 `CH-NNN_NAME/RELATIONSHIPS.md` 是该角色视角的关系摘要
- 当添加新关系时，**先在 `RELATIONSHIP_GRAPH.md` 中添加**，再到各个角色文件中补充细节
- 当关系因故事发展而演化时，**只更新 `RELATIONSHIP_GRAPH.md`**，角色文件保持概要

### 5.6 Obsidian Graph View 说明

- 每个 `[[CH-NNN_CODE]]` 链接自动被 Obsidian 的 Graph View 识别
- 关系类型（`romantic`, `familial` 等）可通过 Dataview 为链接添加颜色编码标记
- 建议在 Graph View 中使用查询配置，按关系类型高亮显示不同颜色的边
- 画布（Canvas）中可通过嵌入此图谱表格来生成动态展示

---

## 6. 关系 ID 索引（预留）

| ID 范围 | 预留用途 |
|---------|----------|
| REL-001 → REL-050 | 主要角色之间的关系（CH-001 ~ CH-010） |
| REL-051 → REL-150 | 主要角色与次要角色的关系 |
| REL-151 → REL-300 | 次要角色之间的关系 |
| REL-301 → REL-500 | 背景角色及跨 IP 关系 |

---

*本图谱是 IP-001 MINGYUN 角色系统的核心组件。更新需遵循 BSOS 协议。*
