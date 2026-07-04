---
title: "BSOS 元数据标准"
type: standard
version: 1.0.0
status: ratified
created: 2025-07-04
author: BSOS Core
tags: [kernel, standard, metadata, frontmatter]
canon_level: core
---

# BSOS 元数据标准

> 本文档定义 BSOS Vault 中所有 Markdown 文件的 YAML frontmatter 规范。
>
> 每个文件必须包含合规的 YAML frontmatter，否则验证不通过。

---

## 1. 必填字段

每个文件的 YAML frontmatter 必须包含以下字段：

| 字段 | 类型 | 必填 | 示例 |
|------|------|------|------|
| `title` | string | ✅ | `"BSOS 创作宪法"` |
| `type` | string | ✅ | `"kernel"` |
| `version` | string | ✅ | `"1.0.0"` |
| `status` | string | ✅ | `"ratified"` |
| `created` | date | ✅ | `"2025-07-04"` |
| `author` | string | ✅ | `"BSOS Core"` |
| `tags` | array | ✅ | `[kernel, constitution, canon]` |
| `canon_level` | string | ✅ | `"immutable"` |

---

## 2. 可选字段

| 字段 | 类型 | 说明 | 示例 |
|------|------|------|------|
| `updated` | date | 最后修改日期 | `"2025-07-05"` |
| `review_by` | date | 计划审核日期 | `"2025-08-01"` |
| `deprecated` | boolean | 是否已废弃 | `true` |
| `superseded_by` | string | 替代文件路径 | `"01_WORLD/LOCATIONS/LOC-003_NEW_LOCATION"` |
| `parent` | string | 父级文件引用 | `"03_PLOT/ARC-001_MAIN_ARC"` |
| `children` | array | 子级文件列表 | `["C-001", "C-002", "C-003"]` |
| `related` | array | 关联文件列表 | `["02_CHARACTERS/CH-001_PROTAGONIST"]` |
| `ip` | string | 关联的创意提案编号 | `"IP-042"` |

---

## 3. type 字段定义

| type 值 | 适用范围 |
|---------|---------|
| `kernel` | 核心系统文件（宪法、原则、工作流） |
| `standard` | 规范/标准文件 |
| `world` | 世界观设定 |
| `character` | 角色档案 |
| `plot` | 剧情弧线和伏笔 |
| `episode` | 章节/剧集/场景 |
| `style` | 文风指南 |
| `template` | 模板文件 |
| `archive` | 归档/讨论/废弃 |
| `meta` | 系统元数据（如 CHANGELOG） |
| `index` | 索引文件 |

---

## 4. status 字段定义

| status 值 | 含义 |
|-----------|------|
| `draft` | 草稿，未完成，不可用于创作参考 |
| `review` | 待审核，供 Steve 审核 |
| `ratified` | 已批准，正式生效 |
| `active` | 活跃使用中（适用于持续更新的文件） |
| `deprecated` | 已废弃，不应再引用 |
| `archived` | 已归档，历史记录 |

---

## 5. canon_level 语义

### 5.1 层级定义

| 层级 | 值 | 含义 | 修改条件 |
|------|-----|------|---------|
| L0 | `immutable` | 不可修改 | 仅 BSOS Core 全员同意方可修改 |
| L1 | `core` | 核心层，系统稳定 | 核心团队讨论修改 |
| L2 | `stable` | 稳定层，内容成熟 | 提案 + 审核通过 |
| L3 | `draft` | 草稿层，可变更 | 自由修改 |
| L4 | `deprecated` | 废弃层 | 仅标记，不修改 |

### 5.2 层级继承

- 父级文件 canon_level 影响所有子级文件
- 子级不能有高于父级的 canon_level 约束
- 示例：如果宪法是 `immutable`，则所有引用宪法的原则文件至少为 `core`

### 5.3 各类型文件的默认 canon_level

| 文件类型 | 默认 canon_level |
|---------|----------------|
| 宪法（000_CONSTITUTION） | `immutable` |
| 原则（001_PRINCIPLES） | `core` |
| 标准（STANDARDS/*） | `core` |
| 工作流程 | `core` |
| 世界观设定 | `stable` |
| 角色 DNA | `stable` |
| 剧情弧线 | `draft` |
| 章节/场景 | `draft` |
| 文风指南 | `stable` |
| CHANGELOG | `mutable`（等同 `draft`） |
| 模板 | `stable` |

---

## 6. 标签分类体系

### 6.1 必选标签

每个文件在 `tags` 字段中必须包含至少一个层级标签和一个类型标签。

**层级标签（必选其一）：**
| 标签 | 说明 |
|------|------|
| `kernel` | 核心系统 |
| `world` | 世界观 |
| `character` | 角色 |
| `plot` | 剧情 |
| `episode` | 章节 |
| `style` | 文风 |

**类型标签（可选）：**
| 标签 | 说明 |
|------|------|
| `constitution` | 宪法 |
| `principles` | 原则 |
| `standard` | 标准 |
| `workflow` | 工作流程 |
| `naming` | 命名规范 |
| `metadata` | 元数据 |
| `markdown` | Markdown 规范 |
| `git` | Git 规范 |
| `changelog` | 变更日志 |
| `template` | 模板 |

### 6.2 辅助标签

| 标签 | 说明 |
|------|------|
| `canon` | 正史设定 |
| `non-canon` | 非正史/平行设定 |
| `wip` | 进行中 |
| `needs-review` | 需要审核 |
| `deprecated` | 已废弃 |
| `archived` | 已归档 |

### 6.3 标签格式规则

- 全小写
- 用连字符（`-`）连接多个单词
- 无空格
- 示例：`["kernel", "standard", "naming"]` ✅
- 示例：`["Kernel", "Standard"]` ❌

---

## 7. 完整示例

```yaml
---
title: "示例文件"
type: world
version: 1.2.3
status: ratified
created: 2025-07-04
updated: 2025-07-10
author: BSOS Core
tags: [world, canon, location]
canon_level: stable
parent: "01_WORLD/LOCATIONS/LOC-000_INDEX"
related:
  - "02_CHARACTERS/CH-001_PROTAGONIST"
  - "03_PLOT/ARC-001_MAIN_ARC"
---
```

---

## 8. 验证规则

前导 `---` 和结尾 `---` 必须在文件最顶部，前后不可有空行。

```yaml
# ✅ 正确
---
title: "正确示例"
type: kernel
...
---

# ❌ 错误（标题前有空行）

---
title: "错误示例"
...
---
```

---

## 附则

- canon_level: **core**
- 所有现存文件需逐步迁移至本规范
- 新文件必须严格遵守
- 验证由 Cato 在 Step 4 自动执行
