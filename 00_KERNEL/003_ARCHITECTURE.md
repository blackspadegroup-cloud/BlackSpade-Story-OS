---
title: BSOS Repository Architecture
version: 1.0
status: active
created: 2026-07-04
author: Cato (Project Orchestrator)
approved: Steve (Executive Producer)
---

# BSOS Repository Architecture

## BlackSpade Story OS — 企业级故事操作系统

---

## Table of Contents

1. [Design Philosophy](#1-design-philosophy)
2. [Layered Architecture](#2-layered-architecture)
3. [Folder Tree](#3-folder-tree)
4. [Naming Convention](#4-naming-convention)
5. [Markdown Standard](#5-markdown-standard)
6. [Git Strategy](#6-git-strategy)
7. [Obsidian Strategy](#7-obsidian-strategy)
8. [AI Compatibility](#8-ai-compatibility)
9. [Scalability Model](#9-scalability-model)
10. [Workflow](#10-workflow)

---

## 1. Design Philosophy

### Core Belief

> BSOS is not a script folder. It is a **Story Operating System**.
> It must outlive any single project, any single AI model, any single tool.

### Inspired By

| Source | Lesson for BSOS |
|--------|----------------|
| **Pixar Writers Room** | Braintrust process, story spine, rewrite culture |
| **Marvel Story Bible** | Interconnected universe, character-first, canon discipline |
| **Riot Lore Repository** | Modular lore, retcon protocol, multi-media consistency |
| **AAA Game Narrative Pipeline** | Branching narrative systems, data-driven dialogue, quest structures |
| **Software Engineering** | Separation of concerns, layered architecture, single responsibility, API-first thinking |
| **Obsidian Second Brain** | Backlinks, graph view, atomic notes, Zettelkasten principles |

### Five Architectural Pillars

1. **Separation of Concerns** — Each layer has a distinct responsibility. No file serves two purposes.
2. **Horizontal Scalability** — Adding IP #101 requires creating one folder, not restructuring the tree.
3. **Immutable Core, Mutable Content** — The Kernel layer (00_KERNEL) is versioned and rarely changed. Everything else evolves freely.
4. **AI-First Design** — Every folder, file, and metadata field is designed to be read and written by AI agents without human intervention.
5. **Single Source of Truth** — Obsidian is the canonical store. Git is the version layer. All AI tools read from Obsidian, never from chat history.

---

## 2. Layered Architecture

```
                    ┌─────────────────────────────┐
                    │       LAYER 5: ARCHIVE       │
                    │      [Historical Record]      │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │      LAYER 4: ASSETS         │
                    │     [Shared Media Pool]       │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │    LAYER 3: PRODUCTION       │
                    │   [Active Pipeline - Cross IP] │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │    LAYER 2: IP UNIVERSE      │
                    │  [All IPs - Horizontally Scaled] │
                    │   IP-001 │ IP-002 │ ...│ IP-N  │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │   LAYER 1: FOUNDATIONS       │
                    │  [Shared Creative DNA]        │
                    └─────────────────────────────┘
                    ┌─────────────────────────────┐
                    │    LAYER 0: KERNEL            │
                    │  [Immutable Operating System]  │
                    └─────────────────────────────┘
```

### Layer 0 — KERNEL (00_KERNEL)
**Purpose:** The operating system. Never restructured.
**Contents:** Constitution, standards, templates, AI integration, changelog.
**Mutation:** Only via version bump through Steve approval.
**Analogy:** Linux kernel — you don't rewrite it per application.

### Layer 1 — FOUNDATIONS (10_FOUNDATIONS)
**Purpose:** Shared creative infrastructure reusable across all IPs.
**Contents:** Narrative theory, archetypes, genre frameworks, plot devices.
**Mutation:** Evolves as the creative team discovers new patterns.
**Analogy:** Standard library — reusable modules any IP can import.

### Layer 2 — IP UNIVERSE (20_IPS/)
**Purpose:** Every intellectual property lives here, fully isolated.
**Structure:** One folder per IP. Each IP follows the same internal template.
**Scalability:** Horizontal. Add IP-101 by creating one folder.
**Analogy:** Microservices — each IP is a self-contained service with its own data.

### Layer 3 — PRODUCTION (50_PRODUCTION/)
**Purpose:** Active production artifacts that span multiple IPs or don't belong to a single IP.
**Contents:** Storyboards, shot lists, prompt libraries, daily logs.
**Mutation:** Ephemeral. Cleared or archived after project delivery.

### Layer 4 — ASSETS (80_ASSETS/)
**Purpose:** Shared media repository.
**Contents:** Logos, moodboards, reference materials, brand assets.
**Mutation:** Grows monotonically. Old assets are archived, never deleted.

### Layer 5 — ARCHIVE (90_ARCHIVE/)
**Purpose:** Historical record of everything that came before.
**Contents:** Deprecated systems, old versions, superseded designs.
**Mutation:** Append-only.

---

## 3. Folder Tree

```
BlackSpade Story OS/
│
├── README.md                                    ← Project overview
│
├── 00_KERNEL/                                   ← LAYER 0: Operating System
│   ├── 000_CONSTITUTION.md                      ← 创作宪法（最高法律）
│   ├── 001_PRINCIPLES.md                        ← 创作原则
│   ├── 002_WORKFLOW.md                          ← 标准工作流程
│   ├── 003_ARCHITECTURE.md                      ← 本文件
│   ├── 004_CHANGELOG.md                         ← BSOS 版本日志
│   ├── STANDARDS/
│   │   ├── 000_NAMING_CONVENTION.md
│   │   ├── 001_METADATA_STANDARD.md
│   │   ├── 002_MARKDOWN_STANDARD.md
│   │   └── 003_GIT_STANDARD.md
│   ├── TEMPLATES/
│   │   ├── TEMPLATE_IP_README.md
│   │   ├── TEMPLATE_CHARACTER_BIBLE.md
│   │   ├── TEMPLATE_SEASON.md
│   │   ├── TEMPLATE_EPISODE.md
│   │   ├── TEMPLATE_HOOK.md
│   │   └── TEMPLATE_PRODUCTION_SHOT.md
│   └── AI/
│       ├── 000_SYSTEM_PROMPT.md                 ← Master AI instruction
│       └── 001_MCP_CONFIG.md                    ← MCP integration
│
├── 10_FOUNDATIONS/                              ← LAYER 1: Shared Creative DNA
│   ├── 000_NARRATIVE_THEORY.md                  ← Story structures, beat sheets
│   ├── 001_ARCHETYPES.md                        ← Archetypal character patterns
│   ├── 002_GENRE_FRAMEWORKS.md                  ← Genre-specific conventions
│   ├── 003_PLOT_DEVICES.md                      ← Reusable plot mechanics
│   └── 004_PROMPT_LIBRARY.md                    ← Cross-IP prompt templates
│
├── 20_IPS/                                      ← LAYER 2: All IPs
│   ├── IP-001_MINGYUN/                          ← 《命运早已写好答案》
│   │   ├── INDEX.md                             ← IP metadata & overview
│   │   ├── 00_CANON/                            ← IP-specific canon
│   │   │   └── CANON.md
│   │   ├── 01_UNIVERSE/                         ← World bible
│   │   │   ├── UNIVERSE_BIBLE.md
│   │   │   ├── WORLD_RULES.md
│   │   │   ├── LOCATIONS.md
│   │   │   ├── ORGANIZATIONS.md
│   │   │   └── TIMELINE.md
│   │   ├── 02_CHARACTERS/                       ← Character OS
│   │   │   ├── CHARACTER_INDEX.md
│   │   │   └── [CHARACTER_CODE]_[NAME]/
│   │   │       ├── BIBLE.md                     ← Full character bible
│   │   │       ├── DNA.md                       ← Immutable character core
│   │   │       ├── PSYCHOLOGY.md                ← Inner world
│   │   │       ├── RELATIONSHIPS.md
│   │   │       ├── GROWTH.md                    ← Character arc
│   │   │       ├── DIALOGUE.md                  ← Voice & speech patterns
│   │   │       └── PROMPT.md                    ← AI character simulation prompt
│   │   ├── 03_STORIES/                          ← Story Engine
│   │   │   ├── STORY_INDEX.md
│   │   │   ├── SEASON_01/
│   │   │   │   ├── SEASON_BIBLE.md
│   │   │   │   ├── ARC_001_[NAME]/
│   │   │   │   │   ├── ARC_BIBLE.md
│   │   │   │   │   ├── EP_001.md
│   │   │   │   │   ├── EP_002.md
│   │   │   │   │   └── ...
│   │   │   │   ├── HOOK_MAP.md
│   │   │   │   ├── FORESHADOW_MAP.md
│   │   │   │   └── PAYOFF_MAP.md
│   │   │   └── SEASON_PLAN.md
│   │   ├── 04_PRODUCTION/                       ← Production pipeline
│   │   │   ├── STORYBOARD.md
│   │   │   ├── SHOT_LIST.md
│   │   │   ├── CAMERA_LANGUAGE.md
│   │   │   ├── IMAGE_PROMPTS.md
│   │   │   ├── VIDEO_PROMPTS.md
│   │   │   ├── AUDIO_NOTES.md
│   │   │   ├── SUBTITLE_SCRIPTS/
│   │   │   └── EDITING_NOTES.md
│   │   └── 05_ARCHIVE/
│   │       └── VERSION_LOG.md
│   │
│   └── _TEMPLATE/                               ← IP template (copy to create a new IP)
│       └── ... (mirrors IP-001 structure)
│
├── 50_PRODUCTION/                               ← LAYER 3: Active Pipeline
│   ├── 000_ACTIVE_PROJECTS.md
│   ├── DAILY_LOG/
│   ├── IMAGE_PROMPT_OUTPUTS/
│   ├── VIDEO_PROMPT_OUTPUTS/
│   ├── AUDIO_OUTPUTS/
│   └── REVIEW_NOTES/
│
├── 80_ASSETS/                                   ← LAYER 4: Shared Media
│   ├── 000_ASSET_INDEX.md
│   ├── BRAND/
│   │   ├── LOGO/
│   │   └── BRAND_GUIDELINES.md
│   ├── MOODBOARDS/
│   ├── REFERENCES/
│   │   ├── FILM/
│   │   ├── LITERATURE/
│   │   └── RESEARCH/
│   └── _SOURCE_URLS.md                          ← Record of asset provenance
│
└── 90_ARCHIVE/                                  ← LAYER 5: Historical Record
    ├── 000_ARCHIVE_INDEX.md
    ├── DEPRECATED_SYSTEMS/
    └── VERSION_HISTORY/
```

---

## 4. Naming Convention

### 4.1 Folder Naming

| Rule | Example |
|------|---------|
| Top-level layers: `[NUMBER]_[NAME]` where NUMBER is 2 digits | `00_KERNEL`, `20_IPS`, `80_ASSETS` |
| Within layers: `[NNN]_[NAME]` where NNN is 3-digit counter | `000_CONSTITUTION.md`, `001_PRINCIPLES.md` |
| IP folders: `IP-[NNN]_[CODE]` | `IP-001_MINGYUN`, `IP-002_YOURNEXTIP` |
| Character folders: `[C-NNN]_[NAME]` | `C-001_LINYUXUAN`, `C-002_GUMUYI` |
| Season folders: `SEASON_[NN]` | `SEASON_01`, `SEASON_02` |
| Arc folders: `ARC_[NNN]_[NAME]` | `ARC_001_THEMEETING`, `ARC_002_FIRSTCONFLICT` |
| Use UPPERCASE for codes (MINGYUN, not mingyun) | |

### 4.2 File Naming

| Element | Convention | Example |
|---------|-----------|---------|
| Canon files | `CANON.md` | `CANON.md` |
| Bible files | `[TYPE]_BIBLE.md` | `UNIVERSE_BIBLE.md`, `SEASON_BIBLE.md` |
| Episode files | `EP_[NNN].md` | `EP_001.md`, `EP_012.md` |
| Index files | `[CONTEXT]_INDEX.md` | `CHARACTER_INDEX.md`, `STORY_INDEX.md` |
| Map files | `[TYPE]_MAP.md` | `HOOK_MAP.md`, `FORESHADOW_MAP.md` |
| Template files | `TEMPLATE_[NAME].md` | `TEMPLATE_CHARACTER_BIBLE.md` |
| AI files | `[NNN]_[PURPOSE].md` | `000_SYSTEM_PROMPT.md` |

### 4.3 Version Convention

| Artifact | Format |
|----------|--------|
| BSOS version | `vMajor.Minor.Patch` (e.g., `v1.0.0`) |
| IP version | `IP-001-vMajor.Minor` (e.g., `IP-001-v1.2`) |
| Season version | `S01-vMajor.Minor` |
| File-level | YAML frontmatter `version: 1.0` field |

### 4.4 Code System

Each IP gets a **short code** for internal reference:

```
IP-001 = MINGYUN  (《命运早已写好答案》)
IP-002 = ...

Characters within IP use C-NNN:
C-001 = LINYUXUAN  (女主角)
C-002 = GUMUYI     (男主角)
```

This code system is critical for:
- Git branch naming (`bsos/ip-001/season-01`)
- Tag naming filters
- AI agent reference in prompts
- Cross-IP backlinks in Obsidian

---

## 5. Markdown Standard

### 5.1 Frontmatter (YAML)

Every document must start with:

```yaml
---
title: "Document Title"
type: bible | canon | episode | hook | template | prompt
ip: IP-001
version: 1.0
status: draft | review | active | archived | deprecated
created: YYYY-MM-DD
updated: YYYY-MM-DD
author: ChatGPT | Cato | Claude Code
tags: [tag1, tag2, tag3]
canon_level: immutable | core | flexible | experimental
---
```

### 5.2 `canon_level` Semantics

| Level | Meaning |
|-------|---------|
| `immutable` | Cannot be changed. Foundation of the IP. |
| `core` | Stable. Changes require Creative Director + Steve approval. |
| `flexible` | Can evolve during writing. |
| `experimental` | May be discarded. No canon impact. |

### 5.3 Headings

```markdown
# Title (H1) — Document title only
## Section (H2) — Major sections
### Subsection (H3) — Within sections
#### Detail (H4) — Specific details
```

No skipping levels. No inline HTML unless necessary for Obsidian.

### 5.4 Cross-References (Obsidian Links)

```markdown
- See [[00_KERNEL/000_CONSTITUTION.md|创作宪法]]
- Related character: [[20_IPS/IP-001_MINGYUN/02_CHARACTERS/C-001_LINYUXUAN/BIBLE.md|林雨萱]]
- This hook pays off in [[EP_012.md|EP 012]]
```

### 5.5 Tags (Obsidian Properties)

Every document uses tags for:

- `#bsos` — belongs to BlackSpade Story OS system
- `#ip-001` — IP code
- `#character`, `#universe`, `#story`, `#production` — content type
- `#canon`, `#draft`, `#review` — workflow status
- `#season-01`, `#arc-001` — story position

---

## 6. Git Strategy

### 6.1 Branch Strategy

```
main                          ← Always stable. Mirrors Steve-approved BSOS.
├── develop                   ← Integration branch.
├── feature/bsos-xxx          ← BSOS infrastructure changes.
├── feature/ip-001-xxx        ← IP-001 content changes.
├── feature/ip-002-xxx        ← IP-002 content changes.
├── release/v*.*.*            ← Release candidates.
└── hotfix/xxx                ← Emergency fixes.
```

### 6.2 Commit Convention

```
[type] [scope]: [short description]

Types:
  bsos    — BSOS infrastructure change (kernel, standards, templates)
  ip      — IP content change (story, character, universe)
  canon   — Canon modification (requires explicit approval)
  fix     — Error correction
  archive — Archival operation
  docs    — Documentation only
  chore   — Maintenance

Scope examples: ip-001, kernel, standards, templates, ai

Examples:
  bsos kernel: add naming convention for character folders
  ip ip-001: create character bible for Lin Yuxuan
  canon ip-001: update timeline order for EP_005 and EP_006
  fix ip-001: correct location name in EP_003
```

### 6.3 Release Strategy

```
v1.0.0 — First stable BSOS (this build)
v1.1.0 — Infrastructure improvement
v2.0.0 — Major BSOS restructuring (rare)
IP-001-v1.0 — First IP content release
IP-001-v1.1 — IP content update
```

### 6.4 Tag Convention

```
bsos-v1.0.0
ip-001-v1.0
season-01-v1.0
```

---

## 7. Obsidian Strategy

### 7.1 Folder Structure

The file system IS the Obsidian folder structure. No duplication. Every folder in the vault maps directly to the BSOS tree.

### 7.2 Properties (Frontmatter)

Obsidian's built-in Properties panel maps to our YAML frontmatter. All properties are structured for Dataview queries.

### 7.3 Dataview Queries

Standard queries embedded in INDEX.md files:

```dataview
TABLE status, version, created AS "Created"
FROM "20_IPS/IP-001_MINGYUN"
SORT file.name ASC
```

```dataview
TABLE summary AS "Hook"
FROM #hook AND #ip-001 AND #season-01
SORT episode ASC
```

### 7.4 Backlinks

Every document must link to:
- Its IP home (`[[20_IPS/IP-001_MINGYUN/INDEX.md|IP-001]]`)
- Related characters (`[[C-001_LINYUXUAN]]`)
- Related story documents (`[[EP_005]]`)
- Related hooks (`HOOK_MAP.md`)

This builds Obsidian's Graph View into a complete narrative dependency map.

### 7.5 Templates

All new documents are created from `00_KERNEL/TEMPLATES/` using Obsidian's Templates core plugin. This ensures frontmatter consistency automatically.

### 7.6 Graph View Clusters

The Graph View will show natural clusters:
- **Kernel cluster** — all canon, standards, templates (tightly interconnected)
- **IP cluster** — one cluster per IP, connected via character-story-production links
- **Cross-IP links** — archetypes, shared universe elements

---

## 8. AI Compatibility

### 8.1 Design for AI Reading

Every layer is designed to be consumed by AI agents:

```
AI Entry Point → README.md (project overview)
               → 00_KERNEL/ (rules of the system)
               → 20_IPS/IP-NNN/ (specific IP context)
               → 02_CHARACTERS/C-NNN/ (character context)
               → 03_STORIES/SEASON_NN/ (story context)
```

### 8.2 AI Agent Instructions

The `00_KERNEL/AI/000_SYSTEM_PROMPT.md` file is the master instruction for any AI entering BSOS. It contains:

- BSOS rules and principles
- Workflow instructions for each AI role
- File modification protocols
- Consistency check procedures

### 8.3 MCP Compatibility

The folder structure is designed for MCP (Model Context Protocol) servers:
- Each IP folder can be exposed as a separate context namespace
- Obsidian-local REST API can serve documents to any MCP client
- Tags and frontmatter can be queried via MCP tools

### 8.4 Future AI Models

The system avoids:
- Tool-specific formatting (no ChatGPT-only syntax, no Claude-only conventions)
- Proprietary metadata schemas
- Platform-dependent features

YAML frontmatter + Markdown + Obsidian links = universal.

---

## 9. Scalability Model

### 9.1 Horizontal Scaling (IPs)

```
20_IPS/
├── IP-001_MINGYUN/        ← Current
├── IP-002_NEXT/            ← Future
├── IP-003_ANOTHER/         ← Future
├── ...
└── IP-100_YOURS/           ← Still works
```

Adding IP #101: create `IP-101_CODE/` with the standard internal structure. Done. No changes to any existing folder.

### 9.2 Vertical Scaling (Content Within IP)

```
IP-NNN/
├── 02_CHARACTERS/
│   ├── C-001_NAME/
│   ├── C-002_NAME/
│   ├── ...
│   └── C-050_NAME/          ← 50 characters supported
│
├── 03_STORIES/
│   ├── SEASON_01/
│   ├── SEASON_02/
│   ├── ...
│   └── SEASON_10/           ← 10 seasons supported
│       └── ARC_001/
│           └── EP_001.md    ← Episode files
```

### 9.3 Cross-IP Scaling

Shared elements live in `10_FOUNDATIONS/`:
- Character archetypes can be referenced by multiple IPs
- Plot devices can be shared
- Genre frameworks apply across IPs

### 9.4 Team Scaling

| Team Size | BSOS Impact |
|-----------|-------------|
| 1-3 creators | Full BSOS, single git branch |
| 3-10 creators | Feature branches per creator IP |
| 10+ creators | CI/CD, review gates, automated canon checks |

---

## 10. Workflow

### The Creative Pipeline

```
┌─────────────────────────────────────────────────────────────┐
│                    CREATIVE PIPELINE                          │
├───────────────┬──────────────────────┬───────────────────────┤
│  STEP 1       │  STEP 2             │  STEP 3                │
│  ChatGPT      │  Cato               │  Claude Code           │
│  Outputs      │  Reviews            │  Implements            │
│  Creative     │  → Classifies       │  → Creates files       │
│  Spec         │  → Checks canon     │  → Updates docs        │
│               │  → Identifies       │  → Syncs references    │
│               │    conflicts        │  → Marks complete      │
├───────────────┼──────────────────────┼───────────────────────┤
│  STEP 4       │  STEP 5             │  STEP 6                │
│  Cato         │  Cato               │  Steve                 │
│  Consistency  │  Git Commit         │  Final Review          │
│  Check        │  → feature branch   │  → Approve or          │
│  → Cross-IP   │  → conventional     │    request changes     │
│  → Cross-file │    commit           │  → Merge to develop    │
│  → Validate   │  → PR description   │                        │
│    metadata   │                     │                        │
└───────────────┴──────────────────────┴───────────────────────┘
```

### Standard File Creation Workflow

1. **ChatGPT** produces creative output (character, episode, hook, etc.)
2. **Cato** classifies: is this Creative Spec or discussion?
   - Discussion → no action
   - Creative Spec → proceed
3. **Cato** checks consistency against existing documents (canon, timelines, other characters)
   - Conflicts found → log to conflict queue, wait for Steve
   - Clean → proceed
4. **Cato** delegates to **Claude Code**: create/update specific files using templates
5. **Cato** validates output: correct frontmatter? correct folder? links updated?
6. **Cato** commits to feature branch, creates PR
7. **Steve** reviews and approves/merge

### Consistency Check Protocol

When any file is modified, check these for sync:

```
Modified File                → Check These
─────────────────────────────────────────────────
Character Bible (DNA)        → Relationships, Growth, Prompt, Timeline, Hook Map
Season Bible                 → All episode files, Hook Map, Foreshadow Map, Timeline
Episode file                 → Hook Map (add new hook), Foreshadow Map, Timeline, Character Growth
Universe Bible               → All character bibles (world context), Timeline
Canon (constitution)         → ALL files (canon is law)
Hook Map                     → Each hook must link to its episode and payoff episode
Foreshadow Map               → Each foreshadow must link to its payoff
```

---

*This document is part of BSOS Kernel. Last updated 2026-07-04 by Cato.*
