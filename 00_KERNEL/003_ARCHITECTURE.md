---
title: "BSOS Repository Architecture"
version: 1.1
status: active
created: 2026-07-04
updated: 2026-07-04
author: Cato (BSOS Guardian)
tags: [bsos, kernel, architecture]
canon_level: immutable
---

# BSOS Repository Architecture — v1.1

> **Foundation Layer Update**: The BlackSpade Foundation (10_FOUNDATIONS/) has been established as Layer 1, containing the 4 core documents that define BSOS.

---

## Layered Architecture (Updated)

```
                    ┌─────────────────────────────┐
                    │      90_ARCHIVE              │  Layer 5
                    │      [Historical Record]      │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │      80_ASSETS                │  Layer 4
                    │     [Shared Media Pool]       │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │     50_PRODUCTION             │  Layer 3
                    │   [Active Pipeline - Cross IP] │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │     20_IPS                    │  Layer 2
                    │  [All IPs - Horizontally Scaled] │
                    │   IP-001 │ IP-002 │ ...│ IP-N  │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │   10_FOUNDATIONS              │  Layer 1
                    │  [BlackSpade Foundation]      │
                    │  Protocol · Way · Canon · Gloss│
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │    00_KERNEL                  │  Layer 0
                    │  [Operating System Engine]     │
                    │  Standards · Templates · AI    │
                    └─────────────────────────────┘
```

---

## Foundation Documents (10_FOUNDATIONS/)

| # | Work Order | File | Content |
|---|-----------|------|---------|
| 1 | BSOS-0-001 | `000_BSOS_PROTOCOL.md` | 技术规范：Work Order、Lifecycle、命名、版本、Git、工作流 |
| 2 | BSOS-0-002 | `001_THE_BLACKSPADE_WAY.md` | 创作信仰：为什么创作、BlackSpade 的承诺 |
| 3 | BSOS-0-003 | `002_CREATION_CONSTITUTION.md` | 最高创作法律：10 条宪法 |
| 4 | BSOS-0-004 | `003_GLOSSARY.md` | 统一语言：50+ 个 BSOS 术语定义 |

**Foundation 是 BSOS 的第一层。任何 AI 进入 BSOS 前，应优先阅读 Foundation。**

---

## Work Order Categories

| Category | Code | Scope |
|----------|------|-------|
| System | BSOS-0-xxx | Foundation, Protocol, Workflow, Canon, Repository, Governance |
| Character OS | BSOS-1-xxx | Character Bible, DNA, Brain, Relationship, Growth, Dialogue |
| Universe OS | BSOS-2-xxx | World Building, Timeline, Companies, Locations, History |
| Story Engine | BSOS-3-xxx | Season, Acts, Episodes, Hook Map, Foreshadow, Payoff |
| Production OS | BSOS-4-xxx | Storyboard, Camera, Prompt, Voice, Subtitle, Editing |
| Assets | BSOS-5-xxx | Images, Moodboards, Logos, References |
| Marketing OS | BSOS-6-xxx | Branding, Social Media, Launch, Distribution |
| Business OS | BSOS-7-xxx | Licensing, IP, Contracts, Monetization |
| Research | BSOS-8-xxx | Market Research, Competitor Analysis, Audience |
| Archive | BSOS-9-xxx | Legacy, Migration, Deprecated, Historical Versions |

---

## Work Order Lifecycle

```
IDEA → DISCUSSION → DRAFT → REVIEW → APPROVED → 
WORK ORDER CREATED → IMPLEMENTATION → COMMITTED → 
CANON → LOCKED
```

---

*For full details, see [[10_FOUNDATIONS/000_BSOS_PROTOCOL.md|BSOS Protocol]].*
*Last updated: 2026-07-04*
