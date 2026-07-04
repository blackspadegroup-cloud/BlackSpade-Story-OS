---
title: "角色 Frontmatter 字段参考"
type: reference
ip: bsos
version: 1.0
status: active
created: 2026-07-04
tags: [bsos, template, character, frontmatter, dataview]
canon_level: immutable
---

# 角色 Frontmatter 字段参考

## 用途

本文档定义 BSOS 中**所有角色文件**的 YAML frontmatter 字段标准。  
统一 frontmatter 是 Dataview 自动索引的基础——只有文件填写了正确的字段，`CHARACTER_INDEX.md` 中的 Dataview 查询才能自动发现并展示该角色。

---

## 标准 Frontmatter 模板

```yaml
---
# Required for Dataview auto-indexing
type: snapshot | bible | dna | psychology | relationships | growth | dialogue | prompt
ch_code: "CH-NNN"       # Character code (must match folder name)
name: "角色姓名"          # Display name
role: "女主角"           # 女主角/男主角/主要配角/次要角色
status: concept | draft | active | archived
canon_level: immutable | core | flexible | experimental
ip: "IP-001"            # IP code

# Optional but recommended for filtering
archetype: "ヒーロー"     # Archetype name
tags: [bsos, ip-001, character]
---
```

---

## 字段详解

### 必需字段（Required）

#### `type` — 文件类型

| 取值 | 含义 | 适用文件 |
|------|------|----------|
| `snapshot` | 角色速查卡片 | `Character_Snapshot.md` |
| `bible` | 角色圣经 | `BIBLE.md` |
| `dna` | 不可变角色核心 | `DNA.md` |
| `psychology` | 心理分析 | `PSYCHOLOGY.md` |
| `relationships` | 关系档案 | `RELATIONSHIPS.md` |
| `growth` | 成长弧 | `GROWTH.md` |
| `dialogue` | 语言风格 | `DIALOGUE.md` |
| `prompt` | AI 模拟提示词 | `PROMPT.md` |

**Dataview 用法：** `WHERE type = "snapshot"` 仅筛选角色速查文件，避免重复匹配同一角色的其他子文件。

#### `ch_code` — 角色编号

格式：`CH-NNN`（如 `CH-001`、`CH-002`），必须与所在文件夹名称的前缀一致。

**Dataview 用法：** 作为唯一标识符，用于排序（`SORT ch_code ASC`）和跨文件关联。

#### `name` — 角色姓名

角色的中文显示名称（如 `林雨萱`、`顾穆一`）。

**Dataview 用法：** 在表格中显示为"姓名"列，便于人眼阅读。

#### `role` — 角色定位

| 取值 | 说明 |
|------|------|
| `女主角` | 故事核心女性角色 |
| `男主角` | 故事核心男性角色 |
| `主要配角` | 重要配角，影响主线 |
| `次要角色` | 功能性角色 |
| `背景角色` | 场景填充角色 |

**Dataview 用法：** `TABLE role AS "定位"` 展示角色定位，也可用 `WHERE role = "女主角"` 筛选特定类型。

#### `status` — 状态

| 取值 | 含义 |
|------|------|
| `concept` | 概念阶段，尚未定稿 |
| `draft` | 草稿阶段，正在迭代 |
| `active` | 已完成并活跃使用 |
| `archived` | 已归档，不再使用 |

**Dataview 用法：** 过滤活跃角色（`WHERE status != "archived"`），或在表格中展示状态列。

#### `canon_level` — 正典等级

| 取值 | 含义 |
|------|------|
| `immutable` | 不可变更（如 DNA 文件） |
| `core` | 核心设定，变更需审核 |
| `flexible` | 可根据创作需要调整 |
| `experimental` | 实验性设定，随时可能改动 |

**Dataview 用法：** 按正典等级筛选（`WHERE canon_level = "immutable"`），或排序展示。

#### `ip` — 所属 IP

格式：`IP-NNN`（如 `IP-001`），标识该角色属于哪个 IP。

**Dataview 用法：** 在跨 IP 查询中区分角色归属（`WHERE ip = "IP-001"`）。

---

### 可选字段（Optional）

#### `archetype` — 原型/类型标签

角色的原型名称（如 `ヒーロー`、`メンター`、`トリックスター`），来自 IP 的原型体系。

**Dataview 用法：** 在表格中展示为"原型"列，便于按原型的分类筛选。

#### `tags` — 标签

推荐标签：`[bsos, ip-001, character]`，可根据需要添加更多分类标签。

**Dataview 用法：** `WHERE contains(tags, "character")` 进行多维度筛选。

---

## Dataview 查询示例

### 基本角色列表（用于 CHARACTER_INDEX.md）

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

### 仅显示活跃角色

```dataview
TABLE 
  ch_code AS "编号",
  name AS "姓名",
  role AS "定位"
FROM "20_IPS/IP-001_MINGYUN/02_CHARACTERS"
WHERE type = "snapshot" AND status = "active"
SORT ch_code ASC
```

### 按定位分组统计

```dataview
TABLE 
  rows.name AS "角色",
  length(rows) AS "数量"
FROM "20_IPS/IP-001_MINGYUN/02_CHARACTERS"
WHERE type = "snapshot"
GROUP BY role
SORT role ASC
```

---

## 创建新角色的步骤

1. 在 `20_IPS/IP-001_MINGYUN/02_CHARACTERS/` 下创建文件夹 `CH-NNN_NAME/`
2. 创建文件 `Character_Snapshot.md`，填入以上 frontmatter
3. 填写 `type: snapshot` 使其被 Dataview 自动发现
4. `CHARACTER_INDEX.md` 将**自动更新**，无需手动编辑索引

---

*此参考文档位于 `00_KERNEL/TEMPLATES/`，请勿删除。*
