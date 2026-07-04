---
title: "Archive Index"
type: archive
version: 1.0
status: active
created: 2026-07-04
author: Cato (Project Orchestrator)
tags: [bsos, archive, index]
canon_level: flexible
---

# 归档索引

---

> **归档文件索引。历史版本、废弃系统和已完成项目的记录。**

---

## 归档分类

| 分类 | 文件夹 | 状态 | 描述 |
|------|--------|------|------|
| 废弃系统 | `DEPRECATED_SYSTEMS/` | 空 | 已废弃的 BSOS 版本或子系统 |
| 版本历史 | `VERSION_HISTORY/` | 空 | 已归档的旧版本文件 |

---

## 归档原则

1. **Append-only** — 归档内容只增不减
2. **保留上下文** — 每个归档条目需注明归档原因和日期
3. **可追溯** — 归档内容必须保留来源文件的路径和版本号
4. **不删除** — 旧版本不删除，移入归档

---

*归档操作由 Project Orchestrator (Cato) 执行。*
