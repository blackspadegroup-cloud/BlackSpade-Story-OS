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
| REL-001 | [[CH-001_LINZHIXIA]] | `romantic`/`complex` | [[CH-002_LUJINGSHEN]] | 7 | S1 | evolving | S1: 初遇 — 商业交锋中遇见陆景深，他"看不懂"让她感到不安。<br>S1: 拉锯 — 陆景深的接近让她防御升级，但开始隐约期待他的出现。<br>S1: 裂痕 — 林知夏的冷漠与陆景深的耐心持续角力中。 | S1E01, S1E03, S1E05, S1E08 |
| REL-002 | [[CH-001_LINZHIXIA]] | `familial` | [[CH-NNN_LINMOTHER]] | 9 | pre-story | active | S0: 童年 — 母女相依为命，母亲打两份工供她读书。<br>S0: 创伤 — 弟弟/妹妹因贫无钱医治去世（或母亲积劳错过治疗时机），此事定义了林知夏的人生。<br>S1: 报恩 — 经济独立后每月汇款，但母女之间有很多未说出口的话。 | — |
| REL-003 | [[CH-002_LUJINGSHEN]] | `familial` | [[CH-NNN_LUFATHER]] | 8 | pre-story | dormant | S0: 坠落 — 父亲陆正廷因决策失误导致家族企业崩塌，陆景深目睹全过程。<br>S0: 决裂 — 十六岁后父子关系名存实亡。不恨，但也不靠近。<br>S1: 当前 — 极少联系。陆景深不主动提起父亲。但某些决策时会下意识模仿父亲当年的某些动作——他自己没意识到。 | — |
| REL-004 | [[CH-001_LINZHIXIA]] | `friend` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-005 | [[CH-002_LUJINGSHEN]] | `friend` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-006 | [[CH-001_LINZHIXIA]] | `antagonistic` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-007 | [[CH-002_LUJINGSHEN]] | `antagonistic` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-008 | [[CH-001_LINZHIXIA]] | `mentor` | [[CH-NNN_LINMENTOR]] | 5 | pre-story | active | S0: 初入行 — 前上司/行业前辈，对刚入行的她有知遇之恩。<br>S1: 当前 — 仍保持联系，是林知夏为数不多愿意主动联系的人。 | — |
| REL-009 | [[CH-002_LUJINGSHEN]] | `mentor` | [[CH-NNN_XUSHIJIE]] | 7 | pre-story | active | S0: 创业初期 — 许世杰是陆景深早期投资人兼导师，在陆景深最困难的时候给了他第一笔资金和一个机会。<br>S0: 默契 — 两人性格相似（都是话少、精准的人），成为了罕见的「沉默的信任」关系。<br>S1: 当前 — 许世杰是陆景深为数不多可以不用解释就懂他的人。 | — |
| REL-010 | [[CH-001_LINZHIXIA]] | `professional` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-011 | [[CH-002_LUJINGSHEN]] | `professional` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-012 | [[CH-001_LINZHIXIA]] | `rival` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-013 | [[CH-002_LUJINGSHEN]] | `rival` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-014 | [[CH-001_LINZHIXIA]] | `complex` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-015 | [[CH-002_LUJINGSHEN]] | `complex` | [[CH-NNN_NAME]] | — | — | planned | — | — |

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

## 4. 初始数据行（CH-001 & CH-002 & CH-003）

以下行为 CH-001（林知夏）、CH-002（陆景深）和 CH-003（顾言川）的预留关系数据行，随角色文档创建后填充：

| 关系 ID | 角色 A | 关系类型 | 角色 B | 强度 | 引入季节 | 当前状态 | 演化记录 | 关键剧情引用 |
|---------|--------|----------|--------|:----:|:--------:|:---------:|----------|--------------|
| REL-001 | [[CH-001_LINZHIXIA]] | `romantic`/`complex` | [[CH-002_LUJINGSHEN]] | 7 | S1 | evolving | S1: 初遇 — 商业交锋；S1: 拉锯；S1: 裂痕 | S1E01, S1E03, S1E05, S1E08 |
| REL-003 | [[CH-002_LUJINGSHEN]] | `familial` | [[CH-NNN_LUFATHER]] | 8 | pre-story | dormant | 父子关系，详见主表 REL-003 | — |
| REL-009 | [[CH-002_LUJINGSHEN]] | `mentor` | [[CH-NNN_XUSHIJIE]] | 7 | pre-story | active | 师徒/创业引路人，详见主表 REL-009 | — |
| REL-016 | [[CH-001_LINZHIXIA]] | `familial` | [[CH-NNN_LINMOTHER]] | 9 | pre-story | active | 母女关系，详见主表 REL-002 | — |
| REL-017 | [[CH-001_LINZHIXIA]] | `friend` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-018 | [[CH-001_LINZHIXIA]] | `professional` | [[CH-NNN_LINMENTOR]] | 5 | pre-story | active | 师徒/知遇之恩，详见主表 REL-008 | — |
| REL-019 | [[CH-002_LUJINGSHEN]] | `friend` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-020 | [[CH-002_LUJINGSHEN]] | `antagonistic` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-021 | [[CH-002_LUJINGSHEN]] | `professional` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-022 | [[CH-001_LINZHIXIA]] | — | 待填充 | — | — | planned | — | — |
| REL-023 | [[CH-001_LINZHIXIA]] | — | 待填充 | — | — | planned | — | — |
| REL-024 | [[CH-002_LUJINGSHEN]] | `rival` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-025 | [[CH-002_LUJINGSHEN]] | `complex` | [[CH-NNN_NAME]] | — | — | planned | — | — |
| REL-026 | [[CH-003_GUYANCHUAN]] | `complex`/`romantic` | [[CH-001_LINZHIXIA]] | 6 | S1 | evolving | S1: 初遇 — 酒会上遇见林知夏，她那种「也想逃」的神情让他第一次主动搭讪。<br>S1: 磁吸 — 他开始不自觉地取消行程、推迟出发，为了多待一会儿。<br>S1: 裂痕 — 他害怕了——「走不了」比「走」更让他恐惧。 | S1E01, S1E03, S1E05, S1E08 |
| REL-027 | [[CH-003_GUYANCHUAN]] | `rival`/`respect` | [[CH-002_LUJINGSHEN]] | 4 | S1 | evolving | S1: 初识 — 两人在宴会/工作场合相遇。陆景深代表秩序与掌控，顾言川代表自由与流动。互相感受到对方身上的「对极性」。<br>S1: 暗流 — 当意识到两人都与林知夏产生连接后，敌意浮现——但保持绅士距离。 | S1E02, S1E04 |
| REL-028 | [[CH-003_GUYANCHUAN]] | `familial` | [[CH-NNN_GUMOTHER]] | 5 | pre-story | dormant | S0: 童年 — 母亲是商业联姻中的牺牲品，但尽力给他温暖。<br>S0: 疏离 — 母亲在他青春期后离开家庭，留下一句「你长大了，不需要我了」。<br>S1: 当前 — 偶尔会用匿名的旅行照片联系她，但从未真正和解。 | — |
| REL-029 | [[CH-003_GUYANCHUAN]] | — | 待填充 | — | — | planned | — | — |
| REL-030 | [[CH-003_GUYANCHUAN]] | — | 待填充 | — | — | planned | — | — |

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
