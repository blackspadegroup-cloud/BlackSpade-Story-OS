---
title: "MCP 集成配置 — BSOS 上下文映射"
type: mcp_config
version: "1.0"
status: active
created: {{DATE}}
author: "BSOS Kernel"
tags:
  - mcp
  - context
  - integration
  - config
---

# MCP 集成配置 — BSOS 上下文映射

> **目标：** 说明 BlackSpade Story OS 文件夹结构如何映射到 MCP（Model Context Protocol）的上下文命名空间，使 AI 代理能够基于目录结构和元数据进行精准的上下文检索与操作。

---

## 一、什么是 MCP

MCP（Model Context Protocol）是一种标准化的上下文管理协议，允许 AI 代理通过结构化的命名空间和数据索引来高效检索和理解知识。在 BSOS 中，MCP 用于：

1. 将每个 IP 文件夹映射为独立的上下文命名空间
2. 通过 YAML 前置元数据（frontmatter）为 AI 提供文档的语义标签
3. 支持跨文档的关联查询（如"查找所有涉及某个角色的 Hook"）
4. 让 AI 代理快速定位和操作特定层级的内容

---

## 二、BSOS 文件夹结构与 MCP 命名空间映射

```
BlackSpade Story OS/
├── 00_KERNEL/        → 命名空间: bsos:kernel
│   ├── TEMPLATES/    → 子命名空间: bsos:kernel:templates
│   └── AI/           → 子命名空间: bsos:kernel:ai
├── 01_IPS/           → 命名空间: bsos:ips
│   ├── BSOS-001/     → 命名空间: bsos:ips:bsos-001
│   │   ├── NARRATIVE/   → 子命名空间: bsos:ips:bsos-001:narrative
│   │   ├── PRODUCTION/  → 子命名空间: bsos:ips:bsos-001:production
│   │   ├── ASSETS/      → 子命名空间: bsos:ips:bsos-001:assets
│   │   └── ARCHIVE/     → 子命名空间: bsos:ips:bsos-001:archive
│   ├── BSOS-002/     → 命名空间: bsos:ips:bsos-002
│   └── ...           → 后续 IP 依此类推
```

### 命名空间层级说明

| MCP 命名空间 | 对应目录 | 内容类型 |
|-------------|----------|----------|
| `bsos:kernel` | `00_KERNEL/` | 系统模板、AI 配置、全局规则 |
| `bsos:ips` | `01_IPS/` | 所有 IP 的根命名空间 |
| `bsos:ips:{ip_code}` | `01_IPS/{IP_CODE}/` | 单个 IP 的全部内容 |
| `bsos:ips:{ip_code}:narrative` | `01_IPS/{IP_CODE}/NARRATIVE/` | 季圣经、集大纲 |
| `bsos:ips:{ip_code}:production` | `01_IPS/{IP_CODE}/PRODUCTION/` | 分镜、制作文档 |
| `bsos:ips:{ip_code}:assets` | `01_IPS/{IP_CODE}/ASSETS/` | 视觉资产引用 |
| `bsos:ips:{ip_code}:archive` | `01_IPS/{IP_CODE}/ARCHIVE/` | 完结/废弃内容 |

---

## 三、每个 IP 文件夹作为独立上下文

每个 IP 文件夹（如 `BSOS-001`）构成一个**独立的上下文单元**，具备以下特性：

### 3.1 上下文隔离
- 不同 IP 之间的内容默认不交叉
- AI 在操作 IP-A 时，不应自动引用 IP-B 的内容（除非用户明确要求跨 IP 联动）
- 每个 IP 有自己的标签体系，但标签格式规则是全局统一的

### 3.2 上下文组合
- 可以指定多个 IP 组合查询（如跨 IP 的联动企划）
- 检索路径：`bsos:ips:bsos-001 + bsos:ips:bsos-002`

### 3.3 层级嵌套检索
- 查询 `bsos:ips:bsos-001:narrative` 仅返回该 IP 的叙事内容
- 查询 `bsos:ips:bsos-001` 返回该 IP 的全部内容（包括叙事、制作、资产等）
- 查询 `bsos:ips` 返回所有 IP 的内容索引（不包括 `00_KERNEL`）

---

## 四、标签与前置元数据（Frontmatter）驱动 MCP 查询

BSOS 中的每个文档都包含 YAML 前置元数据，这些元数据是 MCP 查询的核心索引字段。

### 4.1 可查询的前置元数据字段

| 字段 | 查询用途 | 示例 |
|------|----------|------|
| `type` | 按文档类型过滤 | `type: character` → 获取所有角色文档 |
| `ip` | 按归属 IP 过滤 | `ip: "BSOS-001"` → 获取 IP-001 所有文档 |
| `status` | 按文档状态过滤 | `status: draft` → 获取所有草稿 |
| `tags` | 按标签过滤 | `tags: [hook, twist]` → 所有反转 Hook |
| `season` | 按季过滤 | `season: "S1"` → 第 1 季内容 |
| `canon_level` | 按正典级别过滤 | `canon_level: canon` → 正式设 |

### 4.2 典型 MCP 查询示例

```
# 获取 BSOS-001 所有角色文档
query: type=character AND ip="BSOS-001"
namespace: bsos:ips:bsos-001

# 获取所有未回收的 Hook
query: type=hook AND status=draft
namespace: bsos:ips

# 获取 BSOS-002 第 1 季中所有已确认的集数
query: type=episode AND ip="BSOS-002" AND season="S1" AND canon_level=canon
namespace: bsos:ips:bsos-002:narrative

# 查找所有涉及名为"林夜"的角色的文档（全文搜索）
query: "林夜"
namespace: bsos:ips
```

### 4.3 标签系统的最佳实践

为最大化 MCP 查询效率，请遵循以下标签规则：

- **每个文档至少包含 3 个标签**：类型标签 + 内容标签 + 状态标签
- **标签格式：** 全小写，连字符连接（`multiple-words`）
- **推荐标签前缀（可选）：**
  - `char-` 角色相关（`char-protagonist`）
  - `plot-` 剧情相关（`plot-main-arc`）
  - `world-` 世界观相关（`world-magic-system`）
  - `prod-` 制作相关（`prod-storyboard`）
- **避免过于宽泛的标签：** 优先使用具体标签（如 `arc-redemption` 优于 `arc`）

---

## 五、MCP 上下文切换规则

### 5.1 默认上下文
- AI 首次进入 BSOS 时，默认上下文为 `bsos:kernel`（系统规则和模板）
- 在读取 `000_SYSTEM_PROMPT.md` 前不应操作其他命名空间

### 5.2 上下文切换
- 当用户提及特定 IP Code（如 BSOS-001）时，AI 自动切换到对应 IP 的上下文
- 当用户提及特定层级（如"查看制作文档"）时，AI 将上下文缩小到对应的子命名空间

### 5.3 跨上下文操作
- 当需要跨 IP 复制模板或参考设定时，明确声明当前正在操作的上下文范围
- 示例："我正在读取 `bsos:kernel:templates` 中的 TEMPLATE_CHARACTER_BIBLE.md，将复制到 `bsos:ips:bsos-003`"

---

## 六、MCP 与 Obsidian 双向链接的协同

BSOS 同时利用 Obsidian 的双向链接（`[[wikilinks]]`）和 MCP 的结构化查询：

| 功能 | 双向链接 | MCP 查询 |
|------|----------|----------|
| 作用 | 文档间的人类可读引用 | AI 的结构化数据检索 |
| 适用场景 | 概念关联、快速导航 | 批量查询、条件过滤 |
| 示例 | `[[BSOS-001_林夜]]` | `type=hook AND status=draft` |
| 推荐用法 | 文档正文中引用相关概念 | AI 查找和整理信息时使用 |

最佳实践：在文档中使用双向链接标记关联，同时通过前置元数据使内容可被 MCP 检索。两者互补，不是替代关系。

---

## 七、MCP 配置示例（.hermes 或工具端）

以下为在 Hermes Agent 或兼容 MCP 的工具中配置 BSOS 上下文的示例：

```json
{
  "mcp_contexts": {
    "bsos:kernel": {
      "path": "/path/to/BlackSpade Story OS/00_KERNEL",
      "description": "BSOS 系统内核 — 模板、AI 配置、全局规则",
      "file_types": [".md"]
    },
    "bsos:ips:bsos-001": {
      "path": "/path/to/BlackSpade Story OS/01_IPS/BSOS-001",
      "description": "IP BSOS-001 全部内容",
      "file_types": [".md"],
      "recursive": true
    }
  }
}
```

> **注意：** 上述 JSON 仅为配置参考，实际路径根据部署环境调整。

---

*本文档位于 `00_KERNEL/AI/`，系统核心文件，请勿删除或修改。*
