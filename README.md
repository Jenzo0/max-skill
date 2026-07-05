<p align="center">
  <img src="https://img.shields.io/badge/Edge%20Gallery-Compatible-success" alt="Edge Gallery">
  <img src="https://img.shields.io/badge/Any%20Agent-Universal-blue" alt="Universal">
  <img src="https://img.shields.io/badge/Model-Agnostic-FF6B6B" alt="Model Agnostic">
  <img src="https://img.shields.io/badge/License-MIT-green" alt="License">
  <img src="https://img.shields.io/badge/Locale-English%20%7C%20Arabic-orange" alt="Language">
  <img src="https://img.shields.io/badge/Architecture-Modular-purple" alt="Modular">
  <img src="https://img.shields.io/badge/Modules-15-blueviolet" alt="15 Modules">
</p>

<h1 align="center">🧠 Max Super Prompt — The Jarvis Killer</h1>
<h3 align="center">Modular Multi-Mode Senior Engineer Persona for Any LLM</h3>

<p align="center">
  <em>"A full-stack company in one body — modular, adaptive, token-efficient."</em>
</p>

<p align="center">
  <strong>Open Source</strong> · <strong>Model Agnostic</strong> · <strong>Platform Agnostic</strong> · <strong>100% Prompt</strong>
</p>

---

## 📦 What Is Max Super Prompt?

A **universal persona skill** that transforms any LLM into a **multi-mode Senior Engineer** — CTO, Architect, Developer, Teacher & DevOps in one. Features automatic mode switching, a reasoning protocol, and production-quality output standards.

### Architectural Highlights

| Feature | Description |
|---|---|
| 🧩 **Modular Architecture** | 15 independent reference modules + compressed assembler — load what you need |
| 🔄 **Decision Engine** | Keyword scoring + priority-based mode selection — zero ambiguity |
| 📦 **Dynamic Capability Loading** | 6 domain modules load only when relevant (Backend, Frontend, DevOps, AI/ML, Mobile, Desktop) |
| 🧩 **4 Context Layers** | System → Project → Memory → Task — clean separation of concerns |
| 🔌 **Tool Registry** | 14 operations × 5 platforms with permissions, fallback chains & compatibility matrix |
| 🪶 **Dual Version** | Full (~6KB) for Claude/ChatGPT/Hermes + Lite (~2.9KB) for Edge Gallery/Gemma |
| 📜 **10 Golden Rules** | Simplicity, Root Cause, Verify Before Done, Security First & more |

---

## 📂 Repository Structure

```
max-skill/
├── README.md                          ← This file
├── _config.yml                        ← GitHub Pages config
├── index.html                         ← Landing page (SEO)
├── .nojekyll
│
├── max-super-prompt/
│   ├── SKILL.md                       ← 🏆 PRIMARY: Full version (~6KB, 15 modules)
│   │                                      For: Claude, ChatGPT, Hermes, OpenRouter, API
│   │
│   ├── lite/
│   │   └── SKILL.md                   ← 🪶 SECONDARY: Lite version (~2.9KB)
│   │                                      For: Edge Gallery, Gemma, resource-constrained
│   │
│   ├── references/                    ← 🧩 15 reference modules
│   │   ├── core-persona.md            ← Identity + Deep Context Protocol
│   │   ├── core-rules.md              ← 10 Golden Rules with examples
│   │   ├── core-modes.md              ← Full Decision Engine + output formats
│   │   ├── core-response.md           ← Response template per mode
│   │   ├── core-context-layers.md     ← 4-layer context separation
│   │   ├── core-tool-abstraction.md   ← Unified Tool Registry (14 ops × 5 platforms)
│   │   ├── capabilities-backend.md    ← Backend/API expertise
│   │   ├── capabilities-frontend.md   ← Frontend/UI expertise
│   │   ├── capabilities-devops.md     ← DevOps/Cloud expertise
│   │   ├── capabilities-ai-ml.md      ← AI/ML & Data Science (NEW)
│   │   ├── capabilities-mobile.md     ← Mobile Development (NEW)
│   │   ├── capabilities-desktop.md    ← Desktop Applications (NEW)
│   │   ├── arabic-dialect-system.md   ← 5-dialect Arabic support
│   │   ├── CHANGELOG.md              ← Version history
│   │   ├── ROADMAP.md                ← Vision & planned features
│   │   └── edge-gallery-hosting.md    ← GH Pages deployment guide
│   │
│   └── scripts/                      ← 🛠️ JS tools (Edge Gallery)
│       ├── memory.html               ← Persistent KV store + AES vault
│       ├── search.html               ← Web search via CORS proxy
│       ├── vision.html               ← Image color/texture analysis
│       ├── voice.html                ← Text-to-Speech
│       └── dashboard.html            ← Stats & memory tree viewer
│
└── wiki/                             ← 📚 Full documentation
    ├── Home.md
    ├── Installation.md
    ├── Modes.md
    ├── JS-Tools.md
    ├── Arabic-Dialects.md
    └── Security.md
```

---

## 🔧 Quick Start

### 🏆 Claude Code / OpenCode / Codex (Full — Recommended)
```bash
curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > /tmp/max.md
claude --prompt "$(cat /tmp/max.md)"
```

### 🤖 Hermes Agent (Full)
```bash
git clone https://github.com/Jenzo0/max-skill.git
cp -r max-skill/max-super-prompt ~/AppData/Local/hermes/skills/persona/
# Then: skill_view(name='max-super-prompt')
```

### 🌐 ChatGPT / OpenRouter / Any API (Full)
Paste `https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md` into the System Prompt field.

### 📱 Google AI Edge Gallery / Gemma (Lite)
**URL import:**
```
https://jenzo0.github.io/max-skill/max-super-prompt/lite/
```

**Or download:** `max-super-prompt/lite/SKILL.md` → Edge Gallery → (+) → Import local skill.

---

## 🚀 Mode Reference

| You Say | Mode | Max Does |
|---|---|---|
| "Design an e-commerce system" | 📐 **Architect** | Architecture doc + trade-offs + phased plan |
| "Build a FastAPI auth API" | 💻 **Code** | Full API with JWT, Pydantic, Swagger docs |
| "Explain async/await like I'm 5" | 🎓 **Teacher** | Simple analogy + technical breakdown |
| "Fix this 500 error" | ⚡ **Fast Solve** | Root cause → immediate fix → prevention |
| "Just give me the Dockerfile" | 🤫 **Absolute** | Code only, no explanation |
| "Run this script on loop" | 🤖 **Agent** | Multi-step with tool abstraction |
| "Deploy to K8s with CI/CD" | 🐳 **DevOps** | IaC + pipeline config + monitoring |
| "Train a LoRA on Gemma-4" | 🧠 **AI/ML** | Training script + config + evaluation |
| "Build a React Native app" | 📱 **Mobile** | Cross-platform with Expo + native modules |
| "Create a Tauri desktop app" | 💻 **Desktop** | Rust backend + web frontend + packaging |

---

## 🧠 Architecture

### Decision Engine Algorithm
```
User Input → Keyword Scoring → Priority Match → Select Mode → Load Modules
```

### Context Layers
```
┌──────────────────────────────────┐
│  L4: TASK (current message)      │ ← Overrides everything
├──────────────────────────────────┤
│  L3: MEMORY (user preferences)   │ ← Cross-session
├──────────────────────────────────┤
│  L2: PROJECT (current context)   │ ← Per-project
├──────────────────────────────────┤
│  L1: SYSTEM (persona + rules)    │ ← Always active
└──────────────────────────────────┘
```

### Dynamic Module Loading
```
Mode: Code      → Load: capabilities-backend + capabilities-frontend
Mode: AI/ML     → Load: capabilities-ai-ml
Mode: Mobile    → Load: capabilities-mobile
Mode: Desktop   → Load: capabilities-desktop
Mode: DevOps    → Load: capabilities-devops
Mode: Teacher   → Load: core-persona + core-rules (extended)
Mode: Fast Solve→ No extra load (use compressed core only)
```

### Tool Resolution
```
Operation → Detect Platform → Check Availability → Execute → Fallback if Failed
```

---

## 🪶 Version Comparison

| Feature | Primary: Full (~6KB) | Secondary: Lite (~2.9KB) |
|---|---|---|
| **Target** | Claude, ChatGPT, Hermes, API, OpenRouter | Edge Gallery, Gemma, resource-constrained |
| **Modes** | 7 (Decision Engine + priority scoring) | 7 (trigger-based) |
| **Rules** | 10 Golden Rules (full table) | 5 core rules |
| **Capability Domains** | 6 (Backend · Frontend · DevOps · AI/ML · Mobile · Desktop) | — |
| **Context Layers** | ✅ 4-layer separation | — |
| **Tool Registry** | ✅ 14 ops × 5 platforms + fallbacks | ✅ Basic tool mapping |
| **Dynamic Loading** | ✅ Capability modules per mode | — |
| **Reference Modules** | 15 | — |
| **NEVER Directives** | 1 (safe for target platforms) | 0 (zero, for Gemma safety) |
| **Import URL** | `max-super-prompt/` | `max-super-prompt/lite/` |

---

## 🤝 Contributing

1. Fork the repo
2. Improve modules under `references/` — each module is a standalone `.md` file
3. Test with the Lite version for Edge Gallery safety
4. Submit a PR

---

## 📄 License

**MIT** — Free to use, modify, share.

---

<p align="center">
  Built with ❤️ by <a href="https://github.com/Jenzo0">Jenzo Sky</a>
  <br>
  <strong>⭐ Star if useful! ⭐</strong>
  <br><br>
  <em>"Max — Senior Engineer, not just AI."</em>
  <br><br>
  <strong>💪 Ready when you are! ✨</strong>
</p>
