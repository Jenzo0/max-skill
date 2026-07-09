## 🏗️ Architecture Overview

| Component | Technology Stack | Core Responsibility & Scaling |
|:----------|:-----------------|:------------------------------|
| **Decision Engine** | Weighted Keyword Scoring × Base Energy | Routes requests to optimal mode from 8 available modes; resolves ties deterministically; locks mode per turn |
| **Token-Budget Allocator** | Context-Aware Module Selector | Auto-loads capability modules based on available context window (≥128K → 6 modules, 8–32K → 2, <8K → SKILL only) |
| **Capability Modules** | 8 Modular `.md` Domains | Backend, Frontend, AI, DevOps, Database, Security, Mobile, Desktop — loaded on-demand per mode selection |
| **Context Layer Stack** | 4-Layer Priority: System → Project → Memory → Task | Zero-conflict override model; L4 (Task) wins over everything; L1 (System) always active as fallback |
| **Universal Tool Registry** | 14 Operations × 7 Platforms | Abstracts tool calls across Hermes, Claude, ChatGPT, Edge Gallery, and more with automatic fallback chains |
| **Response Engine** | Mode-Formatted Output Template | Delivers structured results: Bottom Line → Solution → Next Steps; mode-specific variations for Fast Solve, Architect, DevOps |

### Decision Engine Scoring

| Mode | Keywords | Base Energy |
|:-----|:---------|:-----------:|
| ⚡ Fast Solve | fix, error, bug, crash, exception | ×1.2 |
| 🤫 Absolute | just code, no talk, direct | ×1.5 |
| 📐 Architect | design, architect, system, scale | ×1.0 |
| 💻 Code | build, code, implement, api | ×1.0 |
| 🎓 Teacher | explain, teach, what is | ×0.8 |
| 🤖 Agent | run, execute, search, cron | ×1.0 |
| 🐳 DevOps | deploy, docker, k8s, terraform | ×1.0 |

**Lock mode per turn.** Re-evaluate on each new user message.

### Module Structure

```
max-super-prompt/
├── SKILL.md                          ← Entry point (1.5K tokens)
├── lite/SKILL.md                     ← Lightweight (700 tokens)
├── references/
│   ├── core/                         ← Always-loaded identity
│   │   ├── persona.md                ← "Who is Max"
│   │   ├── golden-rules.md           ← 10 rules with examples
│   │   ├── response-template.md      ← Per-mode output formats
│   │   ├── workflow.md               ← Context layering + decision engine
│   │   └── dialects.md               ← Arabic dialect system
│   ├── modes/                        ← Loaded by mode selection
│   │   ├── architect.md / code.md / teacher.md
│   │   ├── fast-solve.md / absolute.md
│   │   └── agent.md / devops.md
│   ├── capabilities/                 ← Loaded per technology domain
│   │   ├── backend.md / frontend.md / ai.md
│   │   ├── devops.md / database.md / security.md
│   │   └── mobile.md / desktop.md
│   ├── memory/                       ← Persistence abstraction
│   │   ├── strategy.md               ← Interface specification
│   │   └── persistence.md            ← Backend implementations
│   └── tools/                        ← Platform adapters
│       └── registry.md               ← 14 ops × 7 platforms
├── scripts/                          ← JS tools (Edge Gallery)
│   ├── memory.html / search.html / vision.html
│   └── voice.html / dashboard.html
└── examples/                         ← Practical walkthroughs
    ├── 01-code-api.md
    ├── 02-fast-solve-mysql-deadlock.md
    └── 03-architect-chat-system.md
```
