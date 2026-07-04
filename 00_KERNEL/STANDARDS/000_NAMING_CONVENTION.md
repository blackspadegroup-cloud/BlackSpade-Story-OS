---
title: "BSOS 命名规范"
type: standard
version: 1.0.0
status: ratified
created: 2025-07-04
author: BSOS Core
tags: [kernel, standard, naming]
canon_level: core
---

# BSOS 命名规范

> 本文档定义 BSOS Vault 中所有文件夹、文件和代码的命名规则。
>
> 违反命名规范的文件视为格式违规，验证时将不通过。

---

## 1. 文件夹命名规则

### 1.1 顶层文件夹

| 名称 | 前缀 | 用途 |
|------|------|------|
| `00_KERNEL` | `00_` | 系统核心定义（宪法、原则、标准、工作流） |
| `01_WORLD` | `01_` | 世界观设定（地理、历史、文化、组织） |
| `02_CHARACTERS` | `02_` | 角色档案（角色 DNA、关系图） |
| `03_PLOT` | `03_` | 剧情弧线（主弧、支弧、伏笔追踪） |
| `04_EPISODES` | `04_` | 章节与场景（分集、场景卡） |
| `05_STYLE` | `05_` | 文风与语言（文体指南、术语表、示例文本） |
| `99_ARCHIVE` | `99_` | 归档（废弃设定、讨论记录、历史版本） |

**规则：**
- 数字前缀 = 两位阿拉伯数字
- 前缀后跟下划线
- 全大写命名
- 示例：`00_KERNEL` ✅ `00_Kernel` ❌ `0_KERNEL` ❌

### 1.2 子文件夹

- 全部大写 + 下划线
- 示例：`00_KERNEL/STANDARDS/` ✅ `00_KERNEL/standards/` ❌

---

## 2. 文件命名规则

### 2.1 编号 + 标题模式

**格式：** `NNN_TITLE.md`

| 部分 | 规则 | 示例 |
|------|------|------|
| NNN | 三位数字编号（从 000 开始） | `000`, `001`, `042` |
| 分隔符 | 下划线 | `_` |
| TITLE | 大写 + 下划线连接 | `CONSTITUTION`, `NAMING_CONVENTION` |
| 扩展名 | `.md` | `.md` |

**示例：**
- ✅ `000_CONSTITUTION.md`
- ✅ `001_METADATA_STANDARD.md`
- ❌ `000_constitution.md`
- ❌ `000-CONSTITUTION.md`
- ❌ `CONSTITUTION.md`

### 2.2 特殊后缀

| 后缀 | 含义 | 示例 |
|------|------|------|
| `_INDEX` | 索引/目录文件 | `CHARACTER_INDEX.md` |
| `_TEMPLATE` | 模板文件 | `EPISODE_TEMPLATE.md` |
| `_MAP` | 关联映射文件 | `RELATION_MAP.md` |

### 2.3 禁止规则

- 不允许空格（用下划线替代）
- 不允许中文字符在文件名中
- 不允许特殊字符（`@#$%^&*()` 等）
- 不允许连续下划线
- 不允许文件名以标点结尾

---

## 3. 版本号规则

遵循 **Semantic Versioning 2.0.0**：

```
MAJOR.MINOR.PATCH
```

| 层级 | 递增条件 | 示例 |
|------|---------|------|
| MAJOR | 宪法级修改、不兼容变更 | 1.0.0 → 2.0.0 |
| MINOR | 新增功能/文件，向后兼容 | 1.0.0 → 1.1.0 |
| PATCH | 修错、优化、文档 | 1.0.0 → 1.0.1 |

**版本号出现在：**
- 每个文件的 YAML frontmatter `version` 字段
- 文件名中不使用版本号（版本由 frontmatter 和 Git tag 管理）

---

## 4. 编码系统

### 4.1 IP-NNN — Idea / Plot / Premise 编号

**格式：** `IP-NNN`

```
IP-001   第一个创意提案
IP-042   第四十二个创意提案
```

**用途：** 标记创意规格书（Creative Spec）、剧情提案、构思笔记。

**放置位置：** `99_ARCHIVE/IDEAS/` 或相应文件夹

**引用方式：** 在文件中用 `[IP-001]` 格式引用。

### 4.2 C-NNN — Chapter / Episode 编号

**格式：** `C-NNN`

```
C-001   第一章/第一集
C-042   第四十二章/第四十二集
```

**用途：** 标记章节、剧集、场景卡。

**放置位置：** `04_EPISODES/`

**引用方式：** 在文件中用 `[[C-001]]` Obsidian 链接引用。

### 4.3 编码对照表

| 编码 | 全称 | 范围 | 存放位置 |
|------|------|------|---------|
| `IP-NNN` | Idea/Plot Proposal | IP-000 ~ IP-999 | `99_ARCHIVE/IDEAS/` |
| `C-NNN` | Chapter/Episode | C-000 ~ C-999 | `04_EPISODES/` |
| `CH-NNN` | Character | CH-000 ~ CH-999 | `02_CHARACTERS/` |
| `LOC-NNN` | Location | LOC-000 ~ LOC-999 | `01_WORLD/LOCATIONS/` |
| `ORG-NNN` | Organization | ORG-000 ~ ORG-999 | `01_WORLD/ORGANIZATIONS/` |
| `ARC-NNN` | Plot Arc | ARC-000 ~ ARC-999 | `03_PLOT/` |
| `F-NNN` | Foreshadowing/Forecast | F-000 ~ F-999 | `03_PLOT/FORESHADOWING/` |

---

## 5. 配置与元数据文件

| 文件名 | 用途 |
|--------|------|
| `.obsidian/` | Obsidian 配置目录 |
| `.gitignore` | Git 忽略规则 |
| `.gitattributes` | Git 属性配置 |
| `README.md` | Vault 入口文件（仅在根目录） |

---

## 6. 命名检查清单

在创建任何文件前，逐一核对：

- [ ] 文件夹名是否大写 + 数字前缀 + 下划线？
- [ ] 文件名是否为 `NNN_TITLE.md` 格式？
- [ ] 文件名是否有空格或中文字符？
- [ ] frontmatter 中的 `title` 是否为自然语言？
- [ ] frontmatter 中的 `tags` 是否包含标准标签？
- [ ] 编码引用是否为 `IP-NNN` 或 `C-NNN` 格式？

---

## 附则

- canon_level: **core** — 可通过核心团队讨论修改
- 所有现有文件必须在一周内完成命名规范化
- 新文件必须严格遵守本规范
