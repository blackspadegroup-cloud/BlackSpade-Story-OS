---
title: "BSOS Protocol"
work_order: BSOS-0-001
type: protocol
version: 1.0
status: active
created: 2026-07-04
author: Cato (BSOS Guardian)
tags: [bsos, foundation, protocol, system]
canon_level: immutable
---

# BSOS 协议手册

> **BSOS Protocol — 黑桃故事操作系统主技术规范**
> 
> 本文档定义了 BSOS 的运作方式、工作流程、架构规则及治理原则。
> 所有进入仓库的内容必须遵循本文规定的协议。
> 术语定义请参阅 [[003_GLOSSARY.md]]。

---

## 1. 工作令协议（Work Order Protocol）

每个工作令（Work Order）是 BSOS 中最小可追踪工作单元，采用统一编号格式：

**格式：`BSOS-[类别]-[NNN]`**

- `BSOS` — 固定前缀，标识属于 BSOS 体系
- `[类别]` — 按功能领域划分的数字分类（见下表）
- `[NNN]` — 三位数字序号，从 001 开始，同一类别内递增

### 类别定义

| 类别代码 | 名称 | 描述 | 示例 |
|---------|------|------|------|
| BSOS-0 | 系统（System） | BSOS 本身的基础设施、协议、工具配置 | BSOS-0-001（本协议）、BSOS-0-002（系统脚本） |
| BSOS-1 | 角色操作系统（Character OS） | 角色建立、人格建模、行为协议、对话风格 | BSOS-1-001（Cato 初始设定） |
| BSOS-2 | 宇宙操作系统（Universe OS） | 世界观设定、物理规则、历史年表、地理地图 | BSOS-2-001（世界基础设定） |
| BSOS-3 | 故事引擎（Story Engine） | 主线剧情、章节结构、情节弧线、叙事规则 | BSOS-3-001（第一幕设计） |
| BSOS-4 | 制作操作系统（Production OS） | 制作工作流、渲染管线、音效、后期流程 | BSOS-4-001（动画制作规范） |
| BSOS-5 | 资产（Assets） | 所有数字资产的管理、版本追踪、存储规则 | BSOS-5-001（资产目录结构） |
| BSOS-6 | 市场营销操作系统（Marketing OS） | 营销策略、社交媒体、社区管理、品牌推广 | BSOS-6-001（发布日历） |
| BSOS-7 | 商业操作系统（Business OS） | 商业模式、收入流、合同模板、财务规划 | BSOS-7-001（收入模型文档） |
| BSOS-8 | 研究（Research） | 调研记录、参考资料、灵感收集、实验性想法 | BSOS-8-001（美术风格调研） |
| BSOS-9 | 存档（Archive） | 已完结项目、历史记录、废弃方案归档 | BSOS-9-001（V1 废弃方案） |

> **规则：** 每个工作令必须在其 Frontmatter 中以 `work_order:` 字段标注编号。同一类别内的序号不可跳跃、不可重复。

---

## 2. 工作令生命周期（Work Order Lifecycle）

每个工作令按以下阶段流转，不允许跳阶段：

```
IDEA → DISCUSSION → DRAFT → REVIEW → APPROVED → WORK ORDER CREATED → IMPLEMENTATION → COMMITTED → CANON → LOCKED
```

### 各阶段定义

| 阶段 | 状态值 | 说明 | 执行者 |
|------|--------|------|--------|
| **IDEA** | `idea` | 最初的想法或需求，尚未形成文档 | 任何人 |
| **DISCUSSION** | `discussion` | 在 Slack/聊天中讨论，确定需求边界 | Steve + 团队 |
| **DRAFT** | `draft` | 草稿文档写入仓库，可修改 | Cato / Claude Code |
| **REVIEW** | `review` | 提交审查，标注`status: review` | Cato + Steve |
| **APPROVED** | `approved` | 审查通过，准备执行 | Steve |
| **WORK ORDER CREATED** | `wo_created` | 正式创建 Work Order 文档，分配编号 | Cato |
| **IMPLEMENTATION** | `implementation` | 正在实现中 | Claude Code / 开发团队 |
| **COMMITTED** | `committed` | 实现完成，代码/文档已提交到仓库 | Claude Code |
| **CANON** | `canon` | Cato 验证通过，标注为 Canon | Cato |
| **LOCKED** | `locked` | 最终锁定，不可再修改 | Steve |

### 核心规则

1. **不可跳阶段：** 任何阶段不可跳过，必须顺序通过每个阶段
2. **撤销机制：** 任意阶段可回退到上一阶段（例如 REVIEW 退回 DRAFT）
3. **阶段标记：** 仓库中所有 Canon 文档的 YAML Frontmatter 必须标注当前状态
4. **LOCKED 锁定：** 一旦标记为 LOCKED，任何修改都必须通过 Change Request（见第 13 节）

---

## 3. 仓库工作流（Repository Workflow）

BSOS Obsidian 仓库采用六层架构，每层对应不同的内容类型和权限级别：

```
BlackSpade Story OS/
├── 00_KERNEL/          # 第 0 层 — 内核
│   └── 000_BSOS_PROTOCOL.md        ← （本文件，不可变）
├── 10_FOUNDATIONS/     # 第 1 层 — 基础
│   ├── 001_MISSION.md
│   ├── 002_VISION.md
│   └── 003_GLOSSARY.md
├── 20_IPS/             # 第 2 层 — 知识产权
│   ├── IP-001_BLACKSPADE/
│   ├── IP-002_...
│   └── _TEMPLATES/
├── 50_PRODUCTION/      # 第 3 层 — 生产
│   ├── 00_PROJECTS/
│   ├── 10_SCHEDULES/
│   └── 20_LOGS/
├── 80_ASSETS/          # 第 4 层 — 资产
│   ├── 00_MEDIA/
│   ├── 10_DESIGNS/
│   └── 20_INVENTORIES/
└── 90_ARCHIVE/         # 第 5 层 — 存档
    ├── 00_RESEARCH/
    ├── 10_DEPRECATED/
    └── 20_CLOSED/
```

### 各层级规则

| 层级 | 名称 | 内容类型 | Canon 级别 | 修改权限 |
|------|------|----------|-----------|---------|
| 00_KERNEL | 内核 | 协议、系统配置 | immutable | 需 Change Request |
| 10_FOUNDATIONS | 基础 | 使命、愿景、术语表、核心世界观 | core | CANON 后需 Review |
| 20_IPS | 知识产权 | IP 专属内容（角色、宇宙、故事） | flexible | IP 负责人可修改 |
| 50_PRODUCTION | 生产 | 项目计划、排期、日志 | flexible | 生产团队 |
| 80_ASSETS | 资产 | 媒体文件、设计稿、清单 | flexible | 资产管理者 |
| 90_ARCHIVE | 存档 | 研究、已废弃、已完结 | — | 只读，仅归档操作 |

---

## 4. 命名规范（Naming Convention）

### 文件夹命名

**层级文件夹：** `NN_NAME`
- 两位数字序号 + 下划线 + 英文大写名称
- 示例：`00_KERNEL`、`10_FOUNDATIONS`、`20_IPS`、`50_PRODUCTION`

**IP 文件夹：** `IP-NNN_CODE`
- 固定前缀 `IP-` + 三位数字 + 下划线 + 英文代号
- 示例：`IP-001_BLACKSPADE`、`IP-002_ECHO`

**角色文件夹：** `C-NNN_NAME`
- 固定前缀 `C-` + 三位数字 + 下划线 + 角色英文名
- 示例：`C-001_CATO`、`C-002_STEVE`

### 文件命名

**规范文档：** `NNN_NAME.md`
- 三位数字序号 + 下划线 + 描述性名称
- 示例：`000_BSOS_PROTOCOL.md`、`001_MISSION.md`

**章节/剧集文件：** `EP_NNN.md`
- 固定前缀 `EP_` + 三位数字
- 示例：`EP_001.md`、`EP_042.md`

**模板文件：** `_NAME.md`
- 前缀下划线，用于标记模板而非正式内容
- 示例：`_WORK_ORDER_TEMPLATE.md`、`_CHARACTER_TEMPLATE.md`

### 版本规范

- **BSOS 级别：** 语义化版本 `vMajor.Minor.Patch`（如 `v1.0.0`）
- **IP 级别：** `IP-NNN-vMajor.Minor`（如 `IP-001-v1.2`）
- **文件级别：** YAML Frontmatter 中的 `version` 字段

### 编码系统

- `CANON` — 正典/已核准内容
- `WIP` — 进行中
- `DRAFT` — 草稿
- `TMPL` — 模板
- `ARCH` — 已存档

---

## 5. 版本策略（Version Strategy）

### BSOS 层级版本

**格式：`vX.Y.Z`（Major.Minor.Patch）**

| 版本位 | 触发条件 | 示例 |
|--------|---------|------|
| Major (X) | 协议重大变更；不可向后兼容 | `v1.0.0` → `v2.0.0` |
| Minor (Y) | 新增功能或协议扩展；向后兼容 | `v1.0.0` → `v1.1.0` |
| Patch (Z) | 修复、文字修正、小调整 | `v1.0.0` → `v1.0.1` |

### IP 层级版本

**格式：`IP-NNN-vX.Y`（Major.Minor）**

- Major：IP 核心设定变动
- Minor：补充设定、扩展内容

### 文件层级版本

每个文件的 YAML Frontmatter 必须包含 `version` 字段，与 Git Tag 保持一致。

---

## 6. 分支策略（Branch Strategy）

采用 Git Flow 衍生模型：

```
main (稳定)
  └── develop (集成)
       ├── feature/bsos-xxx           # BSOS 系统特性
       ├── feature/ip-001-xxx         # 特定 IP 特性
       ├── feature/c-001-xxx          # 特定角色特性
       ├── release/v*.*.*             # 发布分支
       └── hotfix/xxx                 # 紧急修复
```

### 分支规则

| 分支 | 基础分支 | 用途 | 合并目标 |
|------|---------|------|---------|
| `main` | — | 生产就绪的 Canon 内容 | — |
| `develop` | `main` | 日常开发集成 | `main` |
| `feature/*` | `develop` | 单个任务/特性开发 | `develop` |
| `release/v*.*.*` | `develop` | 发布准备 | `main` + `develop` |
| `hotfix/*` | `main` | 紧急修复 | `main` + `develop` |

> **规则：** `main` 分支上的所有 Commit 必须对应一个已通过完整生命周期的 Work Order。

---

## 7. Git 约定（Git Convention）

### Commit 格式

```
[type] [scope]: message
```

例如：
- `[bsos] [protocol]: 更新 Work Order 生命周期，新增 LOCKED 阶段`
- `[ip] [blackspade]: 添加 Cato 角色背景故事第三节`
- `[canon] [world]: 确认魔法体系最终版本 v2.1`
- `[fix] [typo]: 修正 001_MISSION.md 中的拼写错误`
- `[docs] [readme]: 更新仓库使用说明`
- `[chore] [config]: 更新 Obsidian 插件配置`

### Type 类型

| 类型 | 适用范围 |
|------|---------|
| `[bsos]` | BSOS 系统层级的修改 |
| `[ip]` | 某个 IP 内容的新增或修改 |
| `[canon]` | 标记内容正式成为 Canon |
| `[fix]` | 修复错误或问题 |
| `[docs]` | 文档类修改（非 Canon 内容） |
| `[chore]` | 配置、维护等杂项 |

### Tag 格式

- BSOS 版本标签：`bsos-vX.X.X`（如 `bsos-v1.0.0`）
- IP 版本标签：`ip-001-vX.X`（如 `ip-001-v2.1`）

---

## 8. Markdown 标准（Markdown Standard）

### 标题层级

- `# 标题` — 仅用于文档标题（每文件一个）
- `## 标题` — 主要章节
- `### 标题` — 子章节
- `#### 标题` — 小节点（仅在必要时使用）

### 交叉引用格式

- Obsidian 内部链接：`[[文档名称]]`
- 带显示文字：`[[文档名称|显示文字]]`
- 标题锚点：`[[文档名称#标题]]`
- 示例：`[[003_GLOSSARY.md]]`、`[[001_MISSION.md#核心价值]]`

### 表格格式

```
| 列1 | 列2 | 列3 |
|-----|-----|-----|
| 内容 | 内容 | 内容 |
```

### 脚注格式

```
正文内容[^1]

[^1]: 脚注内容
```

### 其他规则

- 代码块必须标注语言（如 ` ```yaml`）
- 引用使用 `>` 前缀
- 列表使用 `-` 而非 `*`
- 加粗使用 `**`，斜体使用 `*`
- 水平分隔线使用 `---`（前后空行）

---

## 9. 元数据标准（Metadata Standard）

所有进入仓库的 Canon 文档必须包含以下 YAML Frontmatter 字段：

### 必填字段

```yaml
---
title: "文档标题"           # 文档名称
work_order: "BSOS-X-NNN"    # 工作令编号（如适用）
type: "protocol|canon|work_order|note|template"  # 文档类型
ip: "IP-NNN"                # 所属 IP（如适用）
version: "1.0.0"            # 版本号
status: "active|draft|review|canon|locked|archived"  # 状态
created: "2026-07-04"       # 创建日期（YYYY-MM-DD）
updated: "2026-07-04"       # 最后修改日期（YYYY-MM-DD）
author: "作者名称"          # 创建者/维护者
tags: [tag1, tag2, tag3]    # 标签数组
canon_level: "immutable|core|flexible|experimental"  # 正典等级
---
```

### canon_level 定义

| 等级 | 含义 | 示例 | 修改难度 |
|------|------|------|---------|
| `immutable` | 不可变。BSOS 核心协议 | 本文档（BSOS 协议） | 需 Change Request，Steve 亲自批准 |
| `core` | 核心正典。世界观/角色根基 | 使命愿景、核心世界观 | 需 Work Order 完整生命周期 |
| `flexible` | 灵活正典。可在合理范围内修改 | IP 扩展设定、故事细节 | IP 负责人可提议修改 |
| `experimental` | 实验性。尚未正式定稿 | 探索方向、A/B 方案 | 可随时修改，不保证留存 |

---

## 10. AI 协作工作流（AI Collaboration Workflow）

BSOS 定义了一个六步 AI 协作流水线，确保从创意到 Canon 的无缝转化：

### 流水线

```
[Step 1] ChatGPT（创意生成）
    ↓ 原始创意文本
[Step 2] Cato（分类 + 一致性检查）
    ↓ 分类结果 + 验证报告
[Step 3] Claude Code（实现执行）
    ↓ 写入仓库的文档/代码
[Step 4] Cato（验证）
    ↓ 验证通过 / 拒绝退回
[Step 5] Cato（Git Commit）
    ↓ Commit 到 develop 分支
[Step 6] Steve（审查 + 批准）
    ↓ 批准后合并到 main
[已发布 Canon]
```

### 各步骤职责

| 步骤 | 角色 | 职责 |
|------|------|------|
| Step 1 | ChatGPT | 根据需求生成创意内容、初稿 |
| Step 2 | Cato | 对创意分类（属于哪个 BSOS 类别）；检查与现有 Canon 的一致性 |
| Step 3 | Claude Code | 按仓库规范编写正式文档、代码；创建/修改文件 |
| Step 4 | Cato | 验证 Claude Code 的输出是否符合协议；检查格式、Frontmatter、交叉引用 |
| Step 5 | Cato | 执行 Git Add、Commit、Push；添加规范的 Commit Message |
| Step 6 | Steve | 最终人工审查；确认无误后批准合并至 `main` 并标记 CANON / LOCKED |

---

## 11. 创作讨论 vs 正典（Creative Discussion vs Canon）

### 核心原则

> **只有创作规范（Creative Spec）进入仓库。聊天讨论留在聊天里。**

### 界定规则

| 内容 | 去向 | 示例 |
|------|------|------|
| 即时想法、脑暴、闲聊 | 留在 ChatGPT / Slack / Discord | "如果主角是只猫会怎样？" |
| 头脑风暴中产生的可行方案 | 整理成 Work Order 草稿 | "新角色提案：猫侦探" |
| 确认的设计决策 | 写入仓库，标记 CANON | "猫侦探角色设定 v1.0" |
| 讨论中的争议点 | 记录到 Discussion Log，等待 Steve 裁决 | "猫侦探是否应该怕水" |
| 废弃的备选方案 | 移至 `90_ARCHIVE` | "猫侦探 V1 废弃设定" |

### 落地步骤

1. 在讨论中达成基本共识
2. Cato 创建 Work Order 草案
3. 提交 REVIEW
4. Steve 批准后，Claude Code 写入仓库
5. 标记 CANON

---

## 12. 审查流程（Review Flow）

### 审查者职责矩阵

| 内容类型 | 审阅者 | 批准者 | 说明 |
|---------|--------|--------|------|
| BSOS 协议修改 | Cato + Steve | Steve | 不可变级别，双重审查 |
| 基础文档（10_FOUNDATIONS） | Cato | Steve | 核心内容，必须 Steve 确认 |
| IP 内容（20_IPS） | Cato | Steve（新 Canon）/ IP 负责人 | 新设定需 Steve 确认 |
| 生产文档（50_PRODUCTION） | 项目负责人 | Steve | 计划类需 Steve 确认 |
| 资产清单（80_ASSETS） | 资产管理者 | Cato | 资产管理层可自行批准 |
| 存档（90_ARCHIVE） | Cato | — | 仅归档操作，无需批准 |
| Work Order 文档 | Cato | Steve | 所有 Work Order 需批准 |

### 审查标准

1. **一致性：** 与现有 Canon 不冲突
2. **完整性：** Frontmatter 完整，格式合规
3. **可读性：** 语言清晰，结构合理
4. **可追踪：** Work Order 编号有效，版本号正确

### 退回机制

审查未通过时：
- 审查者添加评论说明原因
- 状态回退至 DRAFT
- 修改后重新提交 REVIEW

---

## 13. 变更请求流程（Change Request Flow）

当需要修改已标记为 LOCKED 的内容（如 BSOS 协议本身）时，必须通过正式变更请求流程。

### 步骤

1. **创建新 Work Order**
   标题注明"CHANGE:" + 原文档标题
   分类属于对应的 BSOS 类别

2. **Work Order 内容必须包含**
   - **修改原因：** 为什么需要修改
   - **影响范围：** 哪些内容/IP/角色将受影响
   - **版本升级：** 本次修改对应的版本号提升方案
   - **完整的修改方案：** 具体要修改什么
   - **批准记录：** 谁批准了（必须包含 Steve）

3. **等待 Steve 审查**
   只有 Steve 可以批准对 LOCKED 内容的修改

4. **批准后执行**
   按正常 WORK ORDER CREATED → IMPLEMENTATION 流程进行

### 禁止行为

> ❌ 不可对 LOCKED 内容直接编辑
> ❌ 不可绕过 Change Request 流程
> ❌ 不可在未经 Steve 批准的情况下修改 immutable 级别内容

---

## 14. 正典锁定规则（Canon Lock Rule）

### 锁定条件

内容满足以下所有条件后方可锁定：

1. 已完成完整的 Work Order 生命周期
2. 已在 `main` 分支上
3. 已通过 Steve 的最终审查
4. 与所有现有 Canon 无冲突

### 锁定后的规则

| 操作 | 允许？ | 说明 |
|------|--------|------|
| 读取 | ✅ 允许 | 任何人都可以阅读 Canon 内容 |
| 引用 | ✅ 允许 | 其他文档可用 `[[link]]` 引用 |
| 修改 Frontmatter | ❌ 禁止 | 即使是日期更新也不行 |
| 修改正文 | ❌ 禁止 | 任何文字变动都不允许 |
| 删除 | ❌ 禁止 | 锁定内容不可删除 |
| 新增版本 | ⚠️ 需 Change Request | 通过 CR 创建新版本 |

### 特殊例外

如果发现锁定内容中存在事实性严重错误（如矛盾或错误信息）：
- 创建紧急 Work Order，优先级标记为 `URGENT`
- Steve 可特批跳过部分阶段
- 修改后重新锁定

---

## 15. 仓库治理（Repository Governance）

### 角色与职责

| 角色 | 人员 | 职责 |
|------|------|------|
| **BSOS Guardian** | Cato | 维护协议一致性；验证所有入库内容；执行 Git 操作；维护仓库结构 |
| **最终决策者** | Steve | 批准所有 Canon 变更；裁决争议；BSOS 最高权限 |
| **IP 负责人** | 待定 | 特定 IP 的日常维护和内容提案 |
| **执行者** | Claude Code | 按 Work Order 执行文件写入和修改 |

### Cato（Guardian）核心职责

1. 确保所有入库内容符合本协议
2. 维护 Work Order 编号连续性
3. 执行 Git 操作（提交、打标签、合并）
4. 定期检查 Canon 一致性
5. 发现冲突时报告并等待 Steve
6. 维护仓库目录结构和命名规范

### Steve 核心职责

1. 批准/驳回 Work Order
2. 审查 Canon 变更
3. 裁决 Canon 冲突
4. 锁定最终版本
5. 决定 BSOS 战略方向

---

## 16. 冲突解决协议（Conflict Resolution Protocol）

当发现 Canon 内容之间存在冲突时：

### 冲突检测

冲突来源包括：
- 同一概念在不同文档中的描述不一致
- 新提案与已有 Canon 矛盾
- AI 生成内容与历史记录不符

### 处理流程

1. **Cato 检测到冲突**
   - 记录详细冲突信息（哪些文档、哪些内容冲突）
   - 写入 `90_ARCHIVE/00_RESEARCH/Conflict_Report_YYYY-MM-DD.md`

2. **冲突报告模板**

   ```yaml
   ---
   title: "Conflict Report — YYYY-MM-DD"
   type: conflict_report
   status: open
   created: YYYY-MM-DD
   ---
   
   ## Conflicting Documents
   - [[Doc A]]: 声称 X
   - [[Doc B]]: 声称 Y
   
   ## Description
   详细描述矛盾所在...
   
   ## Proposed Resolutions
   - 方案 A：...
   - 方案 B：...
   
   ## Status
   等待 Steve 裁决。
   ```

3. **上报 Steve**
   - 通知 Steve 冲突存在
   - 附上冲突报告链接

### 核心禁令

> ❌ **Cato 不得自行解决冲突**
> ❌ **Cato 不得在冲突未解决前推进相关内容**
> ❌ **Cato 不得"创造性调和"冲突内容**
> 
> ✅ **正确做法：** 记录冲突，等待 Steve 给出裁决。

### 冲突解决后的操作

- Steve 给出裁决后，更新冲突报告状态为 `resolved`
- 执行 Steve 指定的修改方案
- 标记受影响的文档为新版本

---

## 附录 A：协议元数据

| 字段 | 值 |
|------|-----|
| 协议名称 | BSOS Protocol |
| 工作令编号 | BSOS-0-001 |
| 当前版本 | 1.0.0 |
| 规范等级 | immutable |
| 创建日期 | 2026-07-04 |
| 维护者 | Cato (BSOS Guardian) |
| 批准者 | Steve |

> 本协议的修改必须遵循第 13 节（变更请求流程）。
> 本协议的修改必须记录在 Change Log 并更新版本号。
> 本协议的终审权归属于 Steve。

---

*— BSOS Protocol v1.0.0 — 黑桃故事操作系统之基石 —*
