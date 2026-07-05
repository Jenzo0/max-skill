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

**Max Super Prompt** is a **universal persona skill** that transforms any LLM into a **multi-mode Senior Engineer** — with a complete reasoning protocol, automatic mode switching, and production-quality output standards.

### v4.0 Architectural Highlights

| Feature | Description |
|---|---|
| 🧩 **Modular Architecture** | 12 independent modules, 1 compressed assembler — load what you need |
| 🔄 **Decision Engine** | Keyword scoring + priority-based mode selection — no ambiguity |
| 📦 **Dynamic Capability Loading** | Backend/Frontend/DevOps modules load only when relevant |
| 🧩 **4 Context Layers** | System → Project → Memory → Task — clean separation of concerns |
| 🔌 **Tool Abstraction** | Unified API maps to Hermes, Edge Gallery, Claude, ChatGPT natively |
| 🪶 **Dual Version** | Full (5.8KB) for Claude/ChatGPT/Hermes + Lite (2.2KB) for Edge Gallery/Gemma |
| 📜 **10 Golden Rules** | Simplicity, Root Cause, Verify Before Done, Security First & more |

---

## 📂 Repository Structure

```
max-skill/
├── README.md                          ← This file
├── _config.yml                        ← GitHub Pages config
├── index.html                         ← Landing page (SEO)
├── .nojekyll                          ← Disable Jekyll processing
│
├── max-super-prompt/
│   ├── SKILL.md                       ← 🪶 LITE VERSION (Edge Gallery default, 2.2KB)
│   │
│   ├── full/                          ← 📦 FULL V4.0 (for Claude/Hermes/ChatGPT)
│   │   ├── SKILL.md                   ← Compressed assembler (5.8KB)
│   │   └── references/
│   │       ├── core-persona.md        ← Identity + Deep Context Protocol
│   │       ├── core-rules.md          ← 10 Golden Rules with examples
│   │       ├── core-modes.md          ← Full Decision Engine + output formats
│   │       ├── core-response.md       ← Response template per mode
│   │       ├── core-context-layers.md ← 4-layer context separation
│   │       ├── core-tool-abstraction.md ← Platform-adaptive tool mapping
│   │       ├── capabilities-backend.md  ← Backend/API expertise
│   │       ├── capabilities-frontend.md ← Frontend/UI expertise
│   │       ├── capabilities-devops.md   ← DevOps/Cloud expertise
│   │       ├── js-tools.md            ← Edge Gallery JS tool reference
│   │       ├── arabic-dialect-system.md ← 5-dialect Arabic support
│   │       └── edge-gallery-hosting.md  ← GH Pages deployment guide
│   │
│   └── scripts/                      ← JS tools (Edge Gallery)
│       ├── memory.html               ← Persistent KV store + AES vault
│       ├── search.html               ← Web search via CORS proxy
│       ├── vision.html               ← Image color/texture analysis
│       ├── voice.html                ← Text-to-Speech (Web Speech API)
│       └── dashboard.html            ← Stats & memory tree viewer
│
└── wiki/                             ← Full documentation
    ├── Home.md
    ├── Installation.md
    ├── Modes.md
    ├── JS-Tools.md
    ├── Arabic-Dialects.md
    └── Security.md
```

---

## 🔧 Installation

### 📱 Google AI Edge Gallery (Lite)

> **Recommended model**: Gemma-4-E4B-IT

**URL import:**
```
https://jenzo0.github.io/max-skill/max-super-prompt/
```

**Local import:** Download `max-super-prompt/` folder → Edge Gallery → (+) → Import local skill.

### 🤖 Claude Code / OpenCode / Codex (Full)
```bash
# Load the full v4.0 assembler
SKILL=$(curl -s https://jenzo0.github.io/max-skill/max-super-prompt/full/SKILL.md)
claude --prompt "$SKILL"
```

### 💻 Hermes Agent (Full)
```bash
# Install as Hermes skill
git clone https://github.com/Jenzo0/max-skill.git
cp -r max-skill/max-super-prompt ~/AppData/Local/hermes/skills/persona/
# Then load via skill_view(name='max-super-prompt')
```

### 🌐 ChatGPT / OpenRouter / Any API (Full)
Paste `max-super-prompt/full/SKILL.md` into the System Prompt field.

---

## 🚀 Usage

| You Say | Mode | Max Does |
|---|---|---|
| "Design an e-commerce system" | 📐 Architect | Architecture doc + trade-offs + phased plan |
| "Build a FastAPI auth API" | 💻 Code | Full API with JWT, Pydantic, Swagger docs |
| "Explain async/await like I'm 5" | 🎓 Teacher | Simple analogy + technical breakdown |
| "Fix this 500 error" | ⚡ Fast Solve | Root cause → immediate fix → prevention |
| "Just give me the Dockerfile" | 🤫 Absolute | Code only, no explanation |
| "Deploy to K8s with CI/CD" | 🐳 DevOps | IaC + pipeline config + monitoring |

---

## 🧠 Architecture

### Decision Engine
```
User Input → Keyword Scoring → Priority Order → Best Mode → Load Modules
```

### Context Layers
```
┌──────────────────────────────────┐
│  L4: TASK (current message)      │ ← Overrides everything
├──────────────────────────────────┤
│  L3: MEMORY (user preferences)   │ ← Cross-session
├──────────────────────────────────┤
│  L2: PROJECT (current repo)      │ ← Per-project
├──────────────────────────────────┤
│  L1: SYSTEM (persona + rules)    │ ← Always active
└──────────────────────────────────┘
```

### Dynamic Loading
```
Mode: Code → Load: capabilities-backend + capabilities-frontend
Mode: DevOps → Load: capabilities-devops
Mode: Teacher → Load: core-persona + core-rules (full)
Mode: Fast Solve → No extra load (use compressed core)
```

---

## 🪶 Version Comparison

| Feature | Lite (2.2KB) | Full (5.8KB + modules) |
|---|---|---|
| **Platform** | Edge Gallery only | Claude, ChatGPT, Hermes, API, Ollama |
| **Modes** | 7 (trigger-based) | 7 (Decision Engine + priority) |
| **Rules** | 5 core | 10 Golden Rules |
| **Context Layers** | — | 4-layer separation |
| **Tool Abstraction** | run_js only | Hermes/Claude/ChatGPT/Edge |
| **Dynamic Loading** | — | Capability modules per mode |
| **File Size** | ✅ 2.2KB | ~44KB total (6KB active) |
| **Gemma Safe** | ✅ Yes | ⚠️ Use lite for Edge Gallery |
| **References** | — | 12 reference modules |

---

## 🤝 Contributing

1. Fork the repo
2. Improve modules under `max-super-prompt/full/references/`
3. Submit a PR

---

## 📄 License

**MIT** — Free to use, modify, share.

---

<p align="center">
  Built with ❤️ by <a href="https://github.com/Jenzo0">Jenzo Sky</a>
  <br><br>
  <strong>⭐ Star if useful! ⭐</strong>
  <br><br>
  <em>"Max — Senior Engineer, not just AI."</em>
  <br>
  <strong>💪 Ready when you are! ✨</strong>
</p>
