---
title: "BSOS 标准工作流程"
type: kernel
version: 1.0.0
status: ratified
created: 2025-07-04
author: BSOS Core
tags: [kernel, workflow, process]
canon_level: core
---

# BSOS 标准工作流程

> 本文档定义 BSOS 创作的 6 步标准流水线。

---

## 流程总览

```
User Input → [Step 1] ChatGPT 创作规格书
                  ↓
           [Step 2] Cato 分类 & 一致性检查
                  ↓
           [Step 3] Claude Code 创建/更新文件
                  ↓
           [Step 4] Cato 验证
                  ↓
           [Step 5] Cato 提交 Git
                  ↓
           [Step 6] Steve 审核 & 批准
                  ↓
              完成 ✦
```

---

## Step 1: ChatGPT 创作规格书

**执行者：** ChatGPT

**输入：** 用户的需求描述、会议纪要、或灵感片段

**输出：** Creative Spec（创作规格书）

**格式：**
- 使用 BSOS 模板（详见 `00_KERNEL/TEMPLATES/`）
- 包含 YAML frontmatter
- 明确标注 canon_level

**内容结构：**
1. 需求概述（1-2 段）
2. 受影响文件列表
3. 具体变更内容
4. 一致性检查要点
5. 风险评估（本变更可能影响哪些已有设定）

---

## Step 2: Cato 分类与一致性检查

**执行者：** Cato（BSOS AI Agent）

### 2.1 分类
判断输入内容属于哪种类型：

| 类型 | 描述 | 处理方式 |
|------|------|---------|
| Creative Spec | 具体的创作规格 | 进入 Step 3 |
| Discussion | 讨论、头脑风暴、灵感碎片 | 存入 `99_ARCHIVE/DISCUSSIONS/`，不入流水线 |
| Meta | 关于系统本身的修改建议 | 进入 Kernel 审核流程 |
| Query | 关于现有内容的问询 | 直接查询 Vault 并回答 |

### 2.2 一致性检查

**检查范围：** 所有与本次改动相关的既有文件

**检查协议：**

| 被修改文件类型 | 需要检查的文件 |
|--------------|-------------|
| `00_KERNEL/*` | 所有 Kernel 文件、受影响原则 |
| `01_WORLD/*` | 相关世界观条目、时间线 |
| `02_CHARACTERS/*` | 相关角色 DNA、关系图 |
| `03_PLOT/*` | 相关剧情弧线、伏笔追踪表 |
| `04_EPISODES/*` | 相关章节、场景卡 |
| `05_STYLE/*` | 文风指南、语言规范 |
| `99_ARCHIVE/*` | 相关废弃设定（确保不冲突） |

**检查项：**
- ✅ 无宪法冲突
- ✅ 一致的角色 DNA
- ✅ 伏笔无断裂
- ✅ 时间线无矛盾
- ✅ 命名符合规范

---

## Step 3: Claude Code 创建/更新文件

**执行者：** Claude Code

**输入：** Creative Spec（来自 Step 1）+ 一致性检查报告（来自 Step 2）

**输出：** 新建或更新后的 BSOS Vault 文件

**执行规则：**
1. 严格按照 Creative Spec 执行
2. 不擅自添加 spec 外的内容
3. 所有文件必须有合规 YAML frontmatter
4. 遵守命名规范（`00_KERNEL/STANDARDS/000_NAMING_CONVENTION.md`）
5. 更新 CHANGELOG（如需）

---

## Step 4: Cato 验证

**执行者：** Cato

**验证清单：**

| # | 检查项 | 说明 |
|---|-------|------|
| 1 | 文件存在 | 所有 spec 指定的文件已创建/更新 |
| 2 | Frontmatter 合规 | 符合 METADATA_STANDARD |
| 3 | 链接完整 | 内部 Obsidian 链接无断裂 |
| 4 | 宪法兼容 | 内容不违反 000_CONSTITUTION 任何条款 |
| 5 | 命名合规 | 符合 NAMING_CONVENTION |
| 6 | 格式正确 | 符合 MARKDOWN_STANDARD |
| 7 | 一致性无误 | 交叉检查通过 |

**失败处理：**
- 验证失败 → 标记问题 → 退回 Step 3 修正
- 验证通过 → 进入 Step 5

---

## Step 5: Cato 提交 Git

**执行者：** Cato

**提交规范：**
- 遵循 `GIT_STANDARD.md` 中的提交格式
- 每次提交为一个原子变更
- commit message 格式：`[type scope]: message`

**示例：**
```
[feat world]: 新增东方大陆地理设定
[fix character]: 修正角色林雪 DNA 中恐惧字段
[refactor plot]: 重构第三章剧情弧线
```

---

## Step 6: Steve 审核与批准

**执行者：** Steve（人类审核者）

**审核内容：**
1. 阅读 Creative Spec 与实际变更的差异
2. 确认所有检查已通过
3. 最终内容和质量判断

**结果：**
- ✅ **批准（Approve）** → 工作流程结束
- ❌ **驳回（Reject）** → 退回 Step 1 或 Step 3，附带驳回理由

---

## 一致性检查快速参考表

> 当修改某个文件时，需要同步检查以下关联文件。

| 修改的文件 | 必须检查的关联文件 |
|-----------|------------------|
| `02_CHARACTERS/*` | 关系图、相关剧情弧、涉及章节 |
| `01_WORLD/LOCATIONS/*` | 涉及该地点的章节、角色行踪记录 |
| `03_PLOT/*` | 所有涉及该弧的角色文件、伏笔追踪表 |
| `04_EPISODES/*` | 前后章节的连贯性、角色状态一致性 |
| `00_KERNEL/*` | 所有下级原则文件、受影响的 Creative Spec |
| `05_STYLE/*` | 示例文本涉及的剧情和角色文件 |

---

## 附则

- 本文件 canon_level: **core**
- 工作流程修改需经 Steve 批准
- 每个 Step 的超时标准：Step 1（30min）/ Step 2（5min）/ Step 3（视范围）/ Step 4（5min）/ Step 5（2min）/ Step 6（24h）
