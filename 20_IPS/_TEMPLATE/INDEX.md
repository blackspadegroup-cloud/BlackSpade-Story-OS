---
title: "IP Template — How to Create a New IP"
type: template
version: 1.0
status: active
created: 2026-07-04
author: Cato (Project Orchestrator)
tags: [bsos, template, ip]
canon_level: immutable
---

# IP 模板使用指南

---

## 用途

此模板文件夹是创建新 IP 的起点。当需要启动一个新的 IP 项目时：

1. **复制此模板** `20_IPS/_TEMPLATE/` → `20_IPS/IP-NNN_CODE/`
2. **按照以下步骤填充每个文件**

---

## 创建新 IP 的步骤

### Step 1: 确定 IP 信息

| 字段 | 示例 |
|------|------|
| IP 编号 | IP-002 |
| 代号 (CODE) | 建议 1-2 个英文单词，全大写（如 YOURNEXTIP） |
| 中文名称 | 你的下一个 IP 名称 |
| 文件夹名 | `IP-002_YOURNEXTIP` |

### Step 2: 创建目录结构

复制 `_TEMPLATE/` 下的完整结构到 `IP-NNN_CODE/`。目录结构如下：

```
IP-NNN_CODE/
├── INDEX.md                         ← [必填] IP 总览
├── 00_CANON/
│   └── CANON.md                     ← [必填] IP 特定创作宪法
├── 01_UNIVERSE/
│   ├── UNIVERSE_BIBLE.md            ← [必填] 世界观圣经
│   ├── WORLD_RULES.md               ← [必填] 世界规则
│   ├── LOCATIONS.md                 ← [可选] 地点设定
│   ├── ORGANIZATIONS.md             ← [可选] 组织设定
│   └── TIMELINE.md                  ← [可选] 时间线
├── 02_CHARACTERS/
│   ├── CHARACTER_INDEX.md           ← [必填] 角色索引
│   └── C-NNN_CODE/                  ← [按需] 每个角色一个文件夹
│       ├── BIBLE.md
│       ├── DNA.md
│       ├── PSYCHOLOGY.md
│       ├── RELATIONSHIPS.md
│       ├── GROWTH.md
│       ├── DIALOGUE.md
│       └── PROMPT.md
├── 03_STORIES/
│   ├── STORY_INDEX.md               ← [必填] 故事索引
│   └── SEASON_NN/                   ← [按需] 每季一个文件夹
│       ├── SEASON_BIBLE.md
│       ├── ARC_NNN_NAME/
│       │   ├── ARC_BIBLE.md
│       │   ├── EP_001.md
│       │   └── ...
│       ├── HOOK_MAP.md
│       ├── FORESHADOW_MAP.md
│       └── PAYOFF_MAP.md
├── 04_PRODUCTION/
│   ├── STORYBOARD.md                ← [可选] 故事板
│   ├── SHOT_LIST.md                 ← [可选] 镜头清单
│   ├── CAMERA_LANGUAGE.md           ← [可选] 镜头语言
│   ├── IMAGE_PROMPTS.md             ← [可选] 图像生成提示词
│   ├── VIDEO_PROMPTS.md             ← [可选] 视频生成提示词
│   ├── AUDIO_NOTES.md               ← [可选] 音频笔记
│   ├── SUBTITLE_SCRIPTS/            ← [可选] 字幕脚本
│   └── EDITING_NOTES.md             ← [可选] 剪辑笔记
└── 05_ARCHIVE/
    └── VERSION_LOG.md               ← [必填] 版本日志
```

### Step 3: 更新 INDEX.md

修改 IP 总览文件：
- 更新 Frontmatter（title, ip, code）
- 填写项目名称、类型、目标受众
- 记录创作团队
- 撰写 Core Premise

### Step 4: 更新 CANON.md

修改 IP 特定创作宪法：
- 保留 BSOS 全局宪法引用
- 根据 IP 特点添加特定规则
- 设置合适的 canon_level

### Step 5: 由 ChatGPT 输出创意内容

以下文件需要 ChatGPT 作为 Creative Director 输出：
- UNIVERSE_BIBLE.md — 世界观设定
- WORLD_RULES.md — 世界规则
- LOCATIONS.md — 地点设定
- ORGANIZATIONS.md — 组织设定
- TIMELINE.md — 时间线
- CHARACTER_INDEX.md + 角色档案 — 角色系统
- STORY_INDEX.md + 故事档案 — 故事架构

### Step 6: 更新 BSOS 全局文件

在以下位置添加新 IP 的引用：
- `50_PRODUCTION/000_ACTIVE_PROJECTS.md` — 添加到活跃项目列表
- `00_KERNEL/003_ARCHITECTURE.md` — 如果在架构文档中有引用（可选）

### Step 7: 提交版本日志

在 `05_ARCHIVE/VERSION_LOG.md` 中记录首次创建。

---

## 关键原则

1. **每个 IP 完全独立** — 修改一个 IP 不应影响其他 IP
2. **模板是起点，不是终点** — 根据 IP 需要添加/修改子目录
3. **Canon 第一** — 任何内容输出前，确保 IP 特定 Canon 已定义
4. **ChatGPT 主导创作** — Cato 和 Claude Code 负责执行和一致性检查
5. **所有文档使用简体中文**

---

*此模板是 BSOS 核心组成部分。修改需 Steve 批准。*
