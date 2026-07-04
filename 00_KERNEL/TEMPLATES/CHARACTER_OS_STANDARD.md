---
title: "Character OS v1.1 — Character Standard"
type: template
version: 1.1
status: active
created: 2026-07-04
author: Cato (BSOS Guardian) — Architecture by Creative Director (ChatGPT)
tags: [bsos, character-os, template, standard]
canon_level: core
---

# Character OS v1.0 — Character Standard

> 这是 BlackSpade Story OS 的 Character Standard。
> 未来所有角色、所有 Universe、所有 IP、所有 Story Engine 全部必须使用本标准。
> 本标准属于 **System**，不属于任何单个 Project。

---

## 设计目标

Character OS 的目标不是记录角色。

而是建立一个能够被 AI、人类创作者、导演、演员共同理解与使用的 **Digital Human Model**。

未来任何 AI 在读取 Character OS 后，都应该能够稳定模拟该角色的：

- 思考
- 决策
- 情绪
- 行为
- 对话
- 成长

**Character OS 是角色唯一的长期真相（Single Source of Truth）。**

---

## 角色文件夹结构

```
CH-NNN_NAME/
├── Character_Snapshot.md      ← AI 默认读取入口（30 秒恢复上下文）
├── CHARACTER_PRINCIPLE.md     ← 角色最高原则（位于 Layer 01 之前）
│
├── Identity.md                ← Layer 01
├── History.md                 ← Layer 02
├── Core.md                    ← Layer 03
├── Mind.md                    ← Layer 04
├── Emotion.md                 ← Layer 05
├── Shadow.md                  ← Layer 06
├── Decision_Engine.md         ← Layer 07
├── Behaviour.md               ← Layer 08
├── Voice_Engine.md            ← Layer 09
├── Relationship_Engine.md     ← Layer 10
├── Growth_Engine.md           ← Layer 11
├── Performance.md             ← Layer 12
│
├── Prompt.md                  ← Output 02: AI 角色生成 Prompt
├── Dialogue_Samples.md        ← Output 03: 角色经典对白样本
│
└── BIBLE.md                   ← 完整角色圣经（由各 Layer 自动/手动汇总）
```

---

## Character Principle（角色原则）

> **Character OS 的最高层定义。位于 Layer 01（Identity）之前。**

### 定义

Character Principle 不是角色介绍。

Character Principle 是：**角色一生都在对抗的核心命题。**

它定义了：
- 这个角色一生最大的内部冲突
- 整个人物成长弧线（Character Arc）的起点与终点

未来 Character OS 所有 Layer 都必须围绕 Character Principle 建立。任何 Layer 不得与 Character Principle 冲突。

### 四规则

| 规则 | 说明 |
|------|------|
| **Rule 01** | 不得描述身份、职业、年龄、外貌。描述的是内在命题，不是外在资料。 |
| **Rule 02** | 必须描述角色一生都无法逃避的核心冲突（安全感、控制、自由、信任、孤独、自我价值等）。 |
| **Rule 03** | 必须能够预测角色最终成长方向。读完应能理解角色未来面对什么挑战、最终成为什么样的人。 |
| **Rule 04** | 必须成为 Character OS 的最高约束。Decision Engine、Behaviour Engine、Voice Engine、Growth Engine 均不得违反。 |

### 格式

```markdown
她追逐财富，不是因为爱钱，而是因为贫穷夺走过她的人生。

**核心命题：** 安全感
```

### Character Gate（角色门禁）

> **Character Principle 为 Character OS 的建立门槛。**

任何角色：
- 若无法定义 Character Principle
- 不得开始建立 Character OS

Executive Producer 与 Creative Director 应先完成 Character Principle Review。通过后，才能建立 Character OS。

### 示例

| 角色 | Character Principle | 核心命题 |
|------|-------------------|---------|
| CH-001 林知夏 | 她追逐财富，不是因为爱钱，而是因为贫穷夺走过她的人生。 | 安全感 |
| CH-002 陆景深 | 他穷尽一生追求掌控，却在爱情面前第一次承认：有些东西，越想控制，越会失去。 | 控制 |

---

## Layer 01 — Identity（身份）

**回答：这个人是谁？**

### 内容结构

```markdown
## Layer 01 — Identity

### Basic Info
| 字段 | 内容 |
|------|------|
| 全名 | |
| 年龄 | |
| 生日 | |
| 性别 | |
| 职业 | |
| 出身 | |
| 现居 | |
| 社会阶层 | |
| 教育程度 | |

### External Identity（外部身份）
社会眼中的 TA 是什么形象？

### Internal Identity（内部身份）
TA 如何看待自己？

### Identity Conflict（身份冲突）
外在身份 vs 内在身份之间是否存在矛盾？这矛盾如何驱动剧情？

### Signature（标志特征）
让观众一眼记住 TA 的特征是什么？
```

---

## Layer 02 — History（历史）

**回答：为什么会成为今天的他？**

### 内容结构

```markdown
## Layer 02 — History

### Timeline
| 年龄/时间 | 事件 | 影响 |
|-----------|------|------|
| | | |

### Formative Events（形成性事件）
哪些事件塑造了 TA 的核心人格？
每个事件写明：发生了什么 → TA 如何解读 → 这如何改变了 TA

### Key Relationships History（关键关系史）
- 家庭关系历史
- 重要他人历史
- 关键冲突历史

### The Moment Everything Changed（转折点）
哪一件事是 TA 人生前后的分界线？

### Unexplored Past（未探索的过去）
剧本中尚未揭示，但影响 TA 当前决策的隐藏历史。
```

---

## Layer 03 — Core（核心）

**回答：什么永远不会改变？**

### 内容结构

```markdown
## Layer 03 — Core

### Character DNA
3-5 个不可变核心人格特质。每个特质包含：
- 特质名称
- 定义
- 在日常/压力下如何表现
- 当此特质被挑战时的反应

### Core Values（核心价值观）
| 价值 | 优先级 | 说明 |
|------|--------|------|
| 正义 | | |
| 自由 | | |
| 家庭 | | |
| ... | | |

### Principles（原则）
TA 绝对不会打破的规则。每个原则附带：
- 原则陈述
- 为什么 TA 持有这个原则
- 打破它会付出什么代价

### Bottom Line（底线）
TA 的逆鳞——触碰了就会爆发的事项。
```

---

## Layer 04 — Mind（思维）

**回答：这个人如何思考？**

### 内容结构

```markdown
## Layer 04 — Mind

### Thinking Style（思维模式）
- 理性 vs 直觉
- 乐观 vs 悲观
- 全局 vs 细节
- 计划 vs 随机

### Decision-Making Patterns（决策模式）
面对不同类型的选择，TA 如何做决定？

| 情境类型 | 决策模式 | 可能的错误 |
|---------|---------|-----------|
| 爱情 | | |
| 金钱 | | |
| 职业 | | |
| 道德困境 | | |
| 危机 | | |

### Cognitive Biases（认知偏误）
TA 最常落入哪些思维陷阱？

### Mental Models（心智模型）
TA 用来理解世界的框架是什么？

### Inner Monologue Style（内心独白风格）
如果观众能听到 TA 的内心声音，听起来是什么样？
```

---

## Layer 05 — Emotion（情感）

**回答：这个人如何感受世界？**

### 内容结构

```markdown
## Layer 05 — Emotion

### Emotional Baseline（情感基线）
- 默认情绪状态
- 情绪恢复速度
- 情绪表达程度

### Love Map（爱情观）
- TA 如何理解"爱"？
- TA 如何表达爱？
- TA 如何接受爱？
- TA 在爱情中的安全感水平

### Friendship Map（友情观）
- TA 如何看待友谊？
- TA 有多少真正的朋友？
- TA 如何维系友谊？

### Family Map（家庭观）
- TA 与家庭的关系
- TA 对"家庭"的情感定义

### Trust（信任）
- TA 容易信任人吗？
- 什么行为会赢得 TA 的信任？
- 什么行为会破坏 TA 的信任？
- 背叛后还有第二次机会吗？

### Security（安全感）
- TA 的安全感来源
- TA 的不安全感触发点

### Emotional Expression（情绪表达）
- TA 如何表达快乐？
- TA 如何表达悲伤？
- TA 如何表达愤怒？
- TA 如何表达恐惧？
- TA 隐藏什么情绪？为什么？

### Emotional Triggers（情绪触发点）
什么话、什么行为、什么场景会立刻触发 TA 的强烈情绪？
```

---

## Layer 06 — Shadow（阴影）

**回答：为什么他一直无法成长？**

### 内容结构

```markdown
## Layer 06 — Shadow

### Core Wound（核心创伤）
塑造 TA 的最深心理创伤。
- 创伤事件
- TA 对事件的解读（可能是错误的）
- 这个解读如何影响 TA 之后的所有选择

### Fear（恐惧）
- 表层恐惧（TA 承认的）
- 深层恐惧（TA 不愿承认的）
- 最根本的恐惧（TA 甚至没有意识到的）

### Trauma（创伤）
- 过去的创伤经历
- 这些创伤的触发点
- 创伤的当前影响

### The Lie（谎言）
TA 相信的、实际上错误的信念。
例如："我必须完美才会被爱" / "信任他人就是给他人伤害我的机会"

### The Truth（真相）
TA 最终必须理解的人生真相。
The Lie 的对立面。

### Defense Mechanisms（防御机制）
当创伤/恐惧被触发时，TA 如何保护自己？
- 逃避
- 攻击
- 合理化
- 封闭
- 讨好
- 控制
```

---

## Layer 07 — Decision Engine（决策引擎）

**回答：角色面对不同情境时的稳定决策逻辑。**

目标是让未来 AI 不需要猜测角色会怎么选择。

### 内容结构

```markdown
## Layer 07 — Decision Engine

### Core Decision Principles（核心决策原则）
角色做决策时最优先考虑的 3-5 个因素。
优先级从高到低排列。

### Decision Matrix（决策矩阵）

| 情境 | 默认反应 | 影响因素 | 例外条件 |
|------|---------|---------|---------|
| 被迫说谎 | | | |
| 见到不公平 | | | |
| 被需要帮助 | | | |
| 被背叛 | | | |
| 有机会走捷径 | | | |
| 面对道德困境 | | | |
| 被威胁 | | | |
| 目睹他人受伤害 | | | |

### Cost-Benefit Calculus（成本效益计算）
TA 在面对决策时的心理权衡模式：
- TA 更害怕失去什么？
- TA 更渴望获得什么？
- TA 愿意承担什么风险？
- TA 绝对不愿意牺牲什么？

### Under Pressure（压力下决策）
在时间紧迫/情绪激烈时，TA 的决策质量如何变化？
TA 在压力下最容易犯什么类型的错误？

### Moral Compass（道德指南针）
TA 的道德边界在哪里？
TA 愿意为了什么打破自己的道德？
```

---

## Layer 08 — Behaviour Engine（行为引擎）

**回答：角色的行为模式是什么？**

### 内容结构

```markdown
## Layer 08 — Behaviour Engine

### Default Mode（默认模式）
没有特殊压力时，TA 处于什么状态？

### Common Habits（日常习惯）
| 习惯 | 频率 | 背后原因 |
|------|------|---------|
| | | |

### Body Language Profile（肢体语言档案）
- 站立姿势
- 坐姿
- 走路方式
- 手的习惯动作
- 眼神习惯
- 个人空间需求

### Stress Reactions（压力反应）
| 压力等级 | TA 的表现 | 外部观察者的感知 |
|---------|---------|----------------|
| 低压力 | | |
| 中等压力 | | |
| 高压力 | | |
| 崩溃边缘 | | |

### Emotional Behaviour（情绪行为）
| 情绪 | TA 的行为表现 |
|------|-------------|
| 开心 | |
| 生气 | |
| 悲伤 | |
| 害怕 | |
| 尴尬 | |
| 惊喜 | |
| 失望 | |

### Likes & Dislikes（喜好）
- 喜欢：食物、颜色、音乐、天气、活动、话题
- 不喜欢：同样维度

### Triggers（行为触发点）
什么事件/言语/场景会引发 TA 做出特定行为？
```

---

## Layer 09 — Voice Engine（语言引擎）

**回答：角色的语言模型是什么？**

### 内容结构

```markdown
## Layer 09 — Voice Engine

### Speech Profile（语言档案）
- 说话速度：快/中/慢
- 音调：高/中/低
- 音量：大/中/小
- 口音/方言
- 标志性口头禅
- 常用词汇类型

### Communication Style（沟通风格）
- 直接 vs 含蓄
- 感性 vs 理性
- 主动 vs 被动
- 正式 vs 随意

### Humour Style（幽默风格）
- 开什么类型的玩笑
- 什么情况下会幽默
- 什么情况下绝不会幽默

### Attack Mode（攻击模式）
被激怒时，TA 的语言风格如何？
- 冷暴力沉默
- 语言犀利
- 逻辑碾压
- 情绪爆发
- 被动攻击

### Comfort Mode（安慰模式）
TA 如何安慰他人？
- 给予空间 vs 陪伴 vs 给建议
- TA 说得出安慰的话吗？

### Rejection Style（拒绝方式）
TA 如何拒绝别人？

### Love Expression（爱的表达方式）
- 语言上如何表达爱
- 行动上如何表达爱
- TA 最渴望被爱的方式

### Anger Expression（愤怒的表达方式）
- 从不满到暴怒的阶梯
- 每个阶段的言语特征

### Core Dialogue Principles（核心对白原则）
3-5 条规则，确保 AI 生成的角色对白始终符合人物。
```

---

## Layer 10 — Relationship Engine（关系引擎）

**回答：角色如何建立、维持、改变人与人之间的关系？**

这不是关系名单。而是关系逻辑。

### 内容结构

```markdown
## Layer 10 — Relationship Engine

### Relationship Formation（关系建立）
TA 如何认识新的人？
- 主动还是被动
- 快速信任还是长期观察
- 第一印象偏见

### Relationship Maintenance（关系维持）
TA 如何维系现有关系？
- 联系频率
- 付出模式
- 边界设定

### Relationship Change（关系变化）
- TA 如何化解冲突？
- TA 如何原谅？
- TA 如何结束一段关系？

### Relationship Patterns（关系模式）
TA 在关系中反复出现的模式（健康和不健康的）。

### Attachment Style（依恋风格）
安全型 / 焦虑型 / 回避型 / 混乱型
这对 TA 的关系产生什么影响？

### Social Battery（社交能量）
- 外向 vs 内向
- 独处恢复时间
- 社交最大时长

### Role in Groups（群体角色）
在团队/社交圈中，TA 通常扮演什么角色？
领袖 / 调和者 / 旁观者 / 执行者 / 破坏者

### Relationship with Power（权力关系）
TA 如何对待：
- 比自己权力高的人
- 和自己权力平等的人
- 比自己权力低的人
```

---

## Layer 11 — Growth Engine（成长引擎）

**回答：角色的完整成长机制是什么？**

### 内容结构

```markdown
## Layer 11 — Growth Engine

### Want（想要）
角色自认为想要的东西。
- 具体内容
- 为什么 TA 想要这个
- 这个 Want 与 Need 的关系

### Need（需要）
角色真正需要学习的人生课题。
- 具体内容
- 与 Want 的冲突关系
- TA 如何才能意识到真正的 Need

### Character Arc（角色弧线）
- Arc Type：成长弧 / 堕落弧 / 转变弧 / 固定弧
- Starting Point（起点）：TA 在故事开始时的状态
- End Point（终点）：TA 在故事结束时的状态
- Key Milestones：沿弧线的关键转折点

### Growth Conditions（成长条件）
TA 需要经历什么才能成长？
- 必须面对什么真相
- 必须做出什么选择
- 必须放弃什么
- 必须接受什么

### Growth Resistance（成长阻力）
为什么成长这么难？
- 内在阻力：恐惧、The Lie、创伤
- 外在阻力：环境、对手、限制

### Final Growth（最终成长）
- 成长的具体表现是什么？
- 观众如何看出 TA 成长了？
- TA 付出了什么代价？

### Regression Risk（倒退风险）
即使成长了，什么情况下 TA 可能倒退？
```

---

## Layer 12 — Performance（演绎）

**回答：未来演员与 AI 演绎角色的统一标准是什么？**

### 内容结构

```markdown
## Layer 12 — Performance

### Energy Level（能量等级）
| 场景类型 | 能量等级（1-10） | 表现方式 |
|---------|----------------|---------|
| 日常 | | |
| 紧张 | | |
| 情感戏 | | |
| 高潮戏 | | |

### Gaze & Eyes（眼神与目光）
- 日常眼神状态
- 说谎时的眼睛
- 紧张时的眼睛
- 爱意流露时的眼睛
- 愤怒时的眼睛

### Breath（呼吸）
- 安静时
- 紧张时
- 激动时
- 爆发前

### Pause & Silence（停顿与沉默）
- TA 什么时候会停顿
- TA 的沉默代表什么
- TA 的沉默节奏

### Micro-expressions（微表情）
- TA 控制不住的微表情
- TA 试图隐藏情绪时的面部表现

### Physical Presence（身体存在感）
- TA 走进房间时给人的感觉
- TA 站在一群人中的位置
- TA 在冲突中的身体位置

### Voice Performance（声音演绎）
- 日常说话的音调
- 情绪激动时音调的变化
- 低声时的质感
- 爆发时的质感

### Camera Notes（镜头备注）
特定角色的关键镜头指导：
- 标志性出场方式
- 重要情感场景的镜头语言建议
- 角色标志性画面构图
```

---

## Output 01 — Character Snapshot

**用途：30 秒恢复角色上下文。AI 默认读取入口。**

参见：[[TEMPLATE_CHARACTER_SNAPSHOT.md]]

| 维度 | 内容 |
|------|------|
| 一句话介绍 | |
| Character DNA | |
| Want / Need / Core Wound / The Lie / The Truth | |
| Current Arc | |
| Current Relationship | |
| Current Story Status | |

---

## Output 02 — AI Prompt

**用途：统一维护角色的生成 Prompt，供 Image、Video、LLM、Avatar 使用。**

参见：[[TEMPLATE_CHARACTER_PROMPT.md]]

存储在：`CH-NNN_NAME/Prompt.md`

---

## Output 03 — Dialogue Samples

**用途：维护角色经典对白，帮助 AI 快速学习角色语言风格。**

参见：[[TEMPLATE_CHARACTER_DIALOGUE.md]]

存储在：`CH-NNN_NAME/Dialogue_Samples.md`

---

## 角色文件夹 Frontmatter 标准

所有角色文件夹内文件的统一 frontmatter 规范：

```yaml
---
type: identity | history | core | mind | emotion | shadow | decision_engine | behaviour | voice_engine | relationship_engine | growth_engine | performance | snapshot | prompt | dialogue
ch_code: "CH-NNN"
name: "角色全名"
ip: "IP-NNN"
version: 1.0
status: draft | active | archived
canon_level: immutable | core | flexible | experimental
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [bsos, ip-001, character, layer]
---
```

详细字段定义参见：[[REFERENCE_CHARACTER_FRONTMATTER.md]]

---

## 标准维护说明

1. **本标准属于 System**，不是 Project。所有 IP 的所有角色都必须遵循。
2. **不得跳过 Layer**。角色可以从 Snapshot 开始，但最终必须覆盖全部 12 个 Layer。
3. **Layer 可以扩展，不能缩减**。如果某个 Layer 对特定角色需要额外维度，可以增加。但基础维度不能删除。
4. **本标准修改必须通过 Work Order**。
5. **12 Layer 文件 + 3 Output 文件 = 每位角色的完整 Character OS**。

---

*Character OS v1.0 Standard — BlackSpade Story OS*
*最后更新：2026-07-04*
