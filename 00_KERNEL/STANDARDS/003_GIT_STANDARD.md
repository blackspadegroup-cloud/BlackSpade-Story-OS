---
title: "BSOS Git 标准"
type: standard
version: 1.0.0
status: ratified
created: 2025-07-04
author: BSOS Core
tags: [kernel, standard, git]
canon_level: core
---

# BSOS Git 标准

> 本文档定义 BSOS Vault 的 Git 工作流程、分支策略、提交规范和版本管理规则。

---

## 1. 分支策略

### 1.1 分支命名与用途

| 分支类型 | 命名格式 | 用途 | 来源 | 合并目标 |
|---------|---------|------|------|---------|
| `main` | `main` | 生产分支，已审核通过的内容 | — | — |
| `develop` | `develop` | 开发主线，集成中的内容 | `main` | `main` |
| `feature/*` | `feature/<简短描述>` | 功能/内容开发 | `develop` | `develop` |
| `release/*` | `release/<版本号>` | 发布准备分支 | `develop` | `main` + `develop` |
| `hotfix/*` | `hotfix/<简短描述>` | 紧急修复 | `main` | `main` + `develop` |

### 1.2 分支生命周期

```
main  ←─────────────────  release/*
  ↑                            ↑
develop  ←──  feature/*  ←─────┘
  ↑
hotfix/* (从 main 分出，合并回 main + develop)
```

### 1.3 分支管理规则

- **`main`**：保护分支，禁止直接推送。仅通过 PR/MR 合并
- **`develop`**：保护分支，feature 分支合并需经 Cato 验证
- **`feature/*`**：命名使用 kebab-case，示例：
  - `feature/add-eastern-continent` ✅
  - `feature/fix-character-dna` ✅
  - `feature/修改世界设定` ❌（禁止中文）
- **`release/*`**：版本号格式 `release/v1.0.0`
- **`hotfix/*`**：命名使用 kebab-case，示例：`hotfix/fix-timeline-conflict`

---

## 2. 提交规范

### 2.1 提交信息格式

```
[type scope]: 简短描述

详细说明（可选，空一行后写）

- 变更点 1
- 变更点 2
- 关联问题
```

**类型（type）：**

| 类型 | 含义 | 示例 |
|------|------|------|
| `feat` | 新功能/新内容 | `[feat world]: 新增东方大陆地理设定` |
| `fix` | 修错 | `[fix character]: 修正林雪年龄矛盾` |
| `refactor` | 重构 | `[refactor plot]: 重构第三章剧情结构` |
| `docs` | 文档变更 | `[docs standard]: 更新命名规范示例` |
| `style` | 格式/文风 | `[style markdown]: 统一表格格式` |
| `meta` | 元数据/配置 | `[meta git]: 更新 .gitignore` |
| `chore` | 杂项 | `[chore]: 清理废弃分支` |

**范围（scope）：**

| 范围 | 含义 |
|------|------|
| `kernel` | 核心系统 |
| `constitution` | 宪法 |
| `principle` | 原则 |
| `standard` | 标准/规范 |
| `workflow` | 工作流程 |
| `world` | 世界观 |
| `character` | 角色 |
| `plot` | 剧情 |
| `episode` | 章节 |
| `style` | 文风 |
| `template` | 模板 |
| `meta` | 元数据/配置 |

### 2.2 提交规范示例

```
[feat world]: 新增东方大陆地理设定

- 新增 LOC-045 ~ LOC-050 共 6 个地点
- 更新世界地图索引
- 关联 IP-023

[fix character]: 修正林雪年龄矛盾

第三章林雪自称"25岁"与角色档案中"28岁"冲突
统一为 28 岁，并调整相关时间线
```

### 2.3 提交原子性

- 一次提交 = 一个逻辑变更
- 不要混合不相关的修改
- 示例：
  - ❌ `[feat world][fix character]` — 混合变更
  - ✅ 分两次提交：
    - `[feat world]: 新增东方大陆`
    - `[fix character]: 修正林雪年龄`

### 2.4 提交签名

- 所有提交必须包含明确的作者信息
- 推荐使用 GPG 签名（可选但鼓励）

---

## 3. 版本标记（Tag）规范

### 3.1 标记格式

```
vMAJOR.MINOR.PATCH
```

示例：
- `v1.0.0` — 初始发布
- `v1.1.0` — 新增功能
- `v1.1.1` — 修错

### 3.2 标记规则

- 所有 tag 必须为 annotated tag（含说明）
- tag 必须与 `main` 分支上的 commit 关联
- tag 说明包含该版本的 CHANGELOG 摘要

**示例：**
```bash
git tag -a v1.0.0 -m "BSOS v1.0.0 — 初始系统建立"
git tag -a v1.1.0 -m "BSOS v1.1.0 — 新增东方大陆设定"
```

### 3.3 发布版本号递增规则

| 场景 | MAJOR | MINOR | PATCH |
|------|-------|-------|-------|
| 宪法修改 | +1 | 0 | 0 |
| 新增标准/原则 | 0 | +1 | 0 |
| 新增世界观内容 | 0 | +1 | 0 |
| 修错/优化 | 0 | 0 | +1 |
| 文档修正 | 0 | 0 | +1 |
| 文风调整 | 0 | 0 | +1 |

---

## 4. 工作流程脚本

### 4.1 标准提交流程

```bash
# 1. 确保在正确的分支上
git checkout develop

# 2. 创建 feature 分支
git checkout -b feature/add-eastern-continent

# 3. 进行修改
# ...（Cato 创建/更新文件）

# 4. 暂存与提交
git add <files>
git commit -m "[feat world]: 新增东方大陆地理设定"

# 5. 合并回 develop
git checkout develop
git merge feature/add-eastern-continent

# 6. （可选）发起 PR

# 7. 推送
git push origin develop
```

### 4.2 发布流程

```bash
# 1. 从 develop 创建 release 分支
git checkout -b release/v1.1.0 develop

# 2. 更新 CHANGELOG 和版本号
# （手动编辑）

# 3. 提交发布准备
git commit -m "[chore]: v1.1.0 发布准备"

# 4. 合并到 main
git checkout main
git merge release/v1.1.0

# 5. 打 tag
git tag -a v1.1.0 -m "BSOS v1.1.0 — 新增东方大陆设定"

# 6. 合并回 develop
git checkout develop
git merge release/v1.1.0

# 7. 推送
git push origin main --tags
git push origin develop
```

### 4.3 紧急修复流程

```bash
git checkout main
git checkout -b hotfix/fix-timeline-conflict
# 修复...
git commit -m "[fix plot]: 修正时间线冲突"
git checkout main
git merge hotfix/fix-timeline-conflict
git tag -a v1.0.1 -m "BSOS v1.0.1 — 修时间线冲突"
git checkout develop
git merge hotfix/fix-timeline-conflict
```

---

## 5. .gitignore 配置

```gitignore
# Obsidian
.obsidian/workspace
.obsidian/cache
.obsidian/plugins/better-word-count/data.json

# OS
.DS_Store
Thumbs.db

# Editor
*.swp
*.swo
*~

# Temp
*.tmp
*.bak

# IDE
.idea/
.vscode/
```

---

## 6. 自动化检查

Cato 在 Step 5 自动执行以下 Git 检查：

| 检查项 | 说明 |
|--------|------|
| 提交格式 | commit message 是否符合 `[type scope]: desc` 格式 |
| 分支规范 | 当前分支命名是否合规 |
| 文件状态 | 确认无未暂存修改 |
| Tag 合规 | release 是否包含对应 tag |

---

## 附则

- canon_level: **core**
- Git 标准由 Cato 在 Step 5 自动执行
- 本标准的修改须经 BSOS Core 讨论通过
