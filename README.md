<p align="center">
  <img src="https://img.shields.io/badge/v4.0-Modular-FF6B6B" alt="v4.0">
  <img src="https://img.shields.io/badge/Edge%20Gallery-Compatible-success" alt="Edge Gallery">
  <img src="https://img.shields.io/badge/Any%20Agent-Universal-blue" alt="Universal">
  <img src="https://img.shields.io/badge/Model-Agnostic-FF6B6B" alt="Model Agnostic">
  <img src="https://img.shields.io/badge/License-MIT-green" alt="License">
  <img src="https://img.shields.io/badge/Locale-English%20%7C%20Arabic-orange" alt="Language">
  <img src="https://img.shields.io/badge/Architecture-Modular-purple" alt="Modular">
</p>

<h1 align="center">🧠 Max Super Prompt v4.0 — The Jarvis Killer</h1>
<h3 align="center">Modular Multi-Mode Senior Engineer Persona for Any LLM</h3>

<p align="center">
  <em>"A full-stack company in one body — modular, adaptive, token-efficient."</em>
</p>

<p align="center">
  <strong>Open Source</strong> · <strong>Model Agnostic</strong> · <strong>Platform Agnostic</strong> · <strong>100% Prompt</strong>
</p>

---

## 📦 What Is Max Super Prompt v4.0?

A **universal persona skill** that transforms any LLM into a **multi-mode Senior Engineer** — CTO, Architect, Developer, Teacher & DevOps in one. Features automatic mode switching, a reasoning protocol, and production-quality output standards.

### v4.0 Architectural Highlights

| Feature | Description |
|---|---|
| 🧩 **Modular Architecture** | 12 independent reference modules + compressed assembler — load what you need |
| 🔄 **Decision Engine** | Keyword scoring + priority-based mode selection — zero ambiguity |
| 📦 **Dynamic Capability Loading** | Backend/Frontend/DevOps modules load only when relevant (saves tokens) |
| 🧩 **4 Context Layers** | System → Project → Memory → Task — clean separation of concerns |
| 🔌 **Tool Abstraction** | Unified API maps to Hermes, Edge Gallery, Claude, ChatGPT natively |
| 🪶 **Dual Version** | Full (5.9KB) for Claude/ChatGPT/Hermes + Lite (2.2KB) for Edge Gallery/Gemma |
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
│   ├── SKILL.md                       ← 🏆 PRIMARY: Full v4.0 (5.9KB, 12 modules)
│   │                                      For: Claude, ChatGPT, Hermes, OpenRouter, API
│   │
│   ├── lite/
│   │   └── SKILL.md                   ← 🪶 SECONDARY: Lite version (2.2KB)
│   │                                      For: Edge Gallery, Gemma, resource-constrained
│   │
│   ├── references/                    ← 🧩 12 reference modules
│   │   ├── core-persona.md            ← Identity + Deep Context Protocol
│   │   ├── core-rules.md              ← 10 Golden Rules with examples
│   │   ├── core-modes.md              ← Full Decision Engine + output formats
│   │   ├── core-response.md           ← Response template per mode
│   │   ├── core-context-layers.md     ← 4-layer context separation
│   │   ├── core-tool-abstraction.md   ← Platform-adaptive tool mapping
│   │   ├── capabilities-backend.md    ← Backend/API expertise
│   │   ├── capabilities-frontend.md   ← Frontend/UI expertise
│   │   ├── capabilities-devops.md     ← DevOps/Cloud expertise
│   │   ├── js-tools.md               ← Edge Gallery JS tool reference
│   │   ├── arabic-dialect-system.md   ← 5-dialect Arabic support
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

### 🏆 Claude Code / OpenCode / Codex (Full v4.0 — Recommended)
```bash
curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > /tmp/max.md
claude --prompt "$(cat /tmp/max.md)"
```

### 🤖 Hermes Agent (Full v4.0)
```bash
git clone https://github.com/Jenzo0/max-skill.git
cp -r max-skill/max-super-prompt ~/AppData/Local/hermes/skills/persona/
# Then: skill_view(name='max-super-prompt')
```

### 🌐 ChatGPT / OpenRouter / Any API (Full v4.0)
Paste `https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md` into the System Prompt field.

### 📱 Google AI Edge Gallery / Gemma (Lite v4.0)
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
Mode: DevOps    → Load: capabilities-devops
Mode: Teacher   → Load: core-persona + core-rules (extended)
Mode: Fast Solve→ No extra load (use compressed core only)
```

---

## 🪶 Version Comparison

| Feature | Primary: Full (5.9KB) | Secondary: Lite (2.2KB) |
|---|---|---|
| **Target** | Claude, ChatGPT, Hermes, API, OpenRouter | Edge Gallery, Gemma, resource-constrained |
| **Modes** | 7 (Decision Engine + priority scoring) | 7 (trigger-based) |
| **Rules** | 10 Golden Rules (full table) | 5 core rules |
| **Context Layers** | ✅ 4-layer separation | — |
| **Tool Abstraction** | ✅ Hermes/Claude/ChatGPT/Edge | ✅ run_js only |
| **Dynamic Loading** | ✅ Capability modules per mode | — |
| **Reference Modules** | 12 | — |
| **NEVER Directives** | 1 (safe for target platforms) | 0 (zero, for Gemma safety) |
| **Import URL** | `max-super-prompt/` | `max-super-prompt/lite/` |

---

## 🤝 Contributing

1. Fork the repo
2. Improve modules under `references/` — each module is a standalone `.md` file
3. Test with the lite version for Edge Gallery safety
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
