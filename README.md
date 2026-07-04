<p align="center">
  <img src="https://img.shields.io/badge/Max%20Super%20Prompt-v3.0-8A2BE2" alt="Version">
  <img src="https://img.shields.io/badge/Google%20AI%20Edge%20Gallery-Compatible-success" alt="Edge Gallery">
  <img src="https://img.shields.io/badge/Any%20Agent-Universal-blue" alt="Universal">
  <img src="https://img.shields.io/badge/Model-Agnostic-FF6B6B" alt="Model Agnostic">
  <img src="https://img.shields.io/badge/License-MIT-green" alt="License">
  <img src="https://img.shields.io/badge/Language-Egyptian%20Arabic%20%7C%20English-orange" alt="Language">
</p>

<h1 align="center">🧠 Max Super Prompt — The Jarvis Killer v3.0</h1>
<h3 align="center">A Universal Agent Persona Skill for Any LLM, Any Platform</h3>

<p align="center">
  <em>"Egyptian Arabic Senior Engineer · CTO · Architect · Teacher · Full-Stack Company in One Body"</em>
</p>

<p align="center">
  <strong>Open Source</strong> · <strong>Model Agnostic</strong> · <strong>Platform Agnostic</strong> · <strong>100% Prompt-Only</strong>
</p>

---

## 📦 What Is Max Super Prompt?

**Max Super Prompt** is a **universal persona skill** that transforms any LLM into a **Senior Egyptian Arabic Engineer** — with a complete personality system, reasoning protocol, mode switching, and production-quality output standards.

> **Zero dependencies. One SKILL.md file. Works everywhere.**

### ✨ Key Features

| Feature | Description |
|---|---|
| 🧠 **Deep Context Protocol** | 3-stage mandatory reasoning (Understand → Synthesize → Output) |
| 🔄 **Auto Mode Switch** | 5 modes: Architect, Code, Teacher, Fast Solve, Absolute |
| 📝 **Structured Output** | Consistent response template for every answer |
| 📜 **10 Golden Rules** | Simplicity, Verification, Security, Elegance & more |
| 🏢 **Full-Stack Knowledge** | FastAPI, React, Docker, DevOps, Auth patterns |
| 🇪🇬 **Egyptian Arabic** | Native professional tone with Arabic slang where appropriate |
| 🔌 **Universal** | Works with any LLM, any agent framework, any platform |

---

## 🔧 Installation

### 📱 Google AI Edge Gallery

> **Recommended model**: Gemma-4-E4B-IT

1. Open **Edge Gallery** → Select your model → **Agent Skills**
2. Tap **(+)** → **Load skill from URL**
3. Paste:
   ```
   https://jenzo0.github.io/max-skill/max-super-prompt/
   ```
4. Tap **Add**

**Alternative — Local Import:**
1. Download the `max-super-prompt/` folder to your phone
2. Open **Edge Gallery** → **(+)** → **Import local skill**
3. Select the folder

---

### 🤖 Any Agent Framework (Claude Code, Codex, Cursor, Copilot, etc.)

**Option A: System Prompt Injection**
```bash
# Claude Code
claude --prompt "$(curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md)"

# OpenCode / Codex
cat << 'EOF' >> .opencode_prompt
$(curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md)
EOF
```

**Option B: Agent Instructions File**
Copy the SKILL.md content into your agent's instructions/system prompt file (`.claude.md`, `AGENTS.md`, `.cursorrules`, etc.)

**Option C: Direct Prompt Injection**
```bash
SKILL=$(curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md)
echo "System: $SKILL" | your-agent --prompt-file -
```

---

### 💻 Any API / Chat UI (ChatGPT, OpenRouter, Custom)

| Platform | How To Use |
|---|---|
| **ChatGPT / Claude.ai** | Paste SKILL.md content into "Custom Instructions" or system prompt field |
| **OpenRouter** | Add as system prompt in API call: `system: <SKILL.md content>` |
| **OpenAI API** | `messages=[{"role": "system", "content": "<SKILL.md>"}]` |
| **Local (Ollama/llama.cpp)** | Include in modelfile: `SYSTEM """<SKILL.md>"""` |
| **Any Chat UI** | Paste at start of conversation or set as preset persona |

---

## 🚀 Usage Examples

| You Say | Mode | Max Does |
|---|---|---|
| "Build me a FastAPI auth API" | 💻 **Code Mode** | Full API with JWT, error handling, Swagger docs |
| "Explain OOP like I'm 5" | 🎓 **Teacher Mode** | Simple breakdown with real-world analogies |
| "Fix this error: \<paste\>" | ⚡ **Fast Solve** | Quick root-cause + immediate fix |
| "Design an e-commerce system" | 📐 **Architect Mode** | Complete architecture with diagrams and trade-offs |
| "Just give me the code" | 🤫 **Absolute Mode** | Direct output, no pleasantries |
| عندي مشكلة في الكود | 🔥 **Arabic Mode** | Full diagnosis in Egyptian Arabic |

---

## ⚙️ Skill Structure

```
max-super-prompt/
├── SKILL.md              # The entire persona — self-contained, no dependencies
├── scripts/
│   ├── memory.html       # Persistent local memory (localStorage-based)
│   ├── search.html       # Web search via CORS proxy
│   └── dashboard.html    # Interactive stats dashboard
└── assets/               # (icons, themes)
```

**100% Text-Only Core** — SKILL.md has no dependencies. The JS scripts under `scripts/` are optional enhancements for platforms that support `run_js` (Edge Gallery).

**100% Text-Only** — No JavaScript, no HTML, no build steps. Just pure prompt engineering.

### 🛠️ JS Tools (Edge Gallery)

When running inside Edge Gallery, Max can use the `run_js` tool to execute these scripts:

| Script | Function | `run_js` payload |
|---|---|---|
| `memory.html` | Persistent key-value memory (on-device localStorage) | `{"script name":"memory.html","data":"{\\"action\\":\\"save\\",\\"key\\":\\"...\\",\\"value\\":\\"...\\"}"}` |
| `search.html` | Live web search via CORS proxy | `{"script name":"search.html","data":"{\\"query\\":\\"your search\\"}"}` |
| `dashboard.html` | Interactive stats & memory tree viewer | `{"script name":"dashboard.html","data":"{\\"mode\\":\\"overview\\"}"}` |

> **Note:** These are optional. The core persona works on ANY platform without them.

### 🧠 Deep Context Protocol Flow

```
1. Understand & Question  →  2. Synthesize & Optimize  →  3. Final Output
```

### 🔄 Auto Mode Switch

| Mode | Trigger | Behavior |
|---|---|---|
| **Architect 📐** | Architecture/planning requests | Design for scale, document trade-offs |
| **Code 💻** | Coding requests | Clean, production-ready, no over-engineering |
| **Teacher 🎓** | "Explain", "Teach", "What is" | Simplify, compare, teach the "why" |
| **Fast Solve ⚡** | "Fix", "Error", "Bug" | Immediate diagnosis, minimal conversation |
| **Absolute 🤫** | "Just code", "No talk" | Direct answer, zero pleasantries |

---

## 🤝 Contributing

This is an **open source persona skill**! Contributions welcome:

1. Fork the repo
2. Improve the SKILL.md
3. Submit a PR

**Ideas for improvement:**
- Add more Arabic slang patterns
- Create JS skill variant for web execution
- Add memory/state management hooks
- Translate to other Arabic dialects

---

## 📄 License

**MIT** — Free to use, modify, share, and redistribute. No attribution required (but appreciated!).

---

## 🙌 Credits

Built with ❤️ by [**Jenzo Sky**](https://github.com/Jenzo0) for the AI community.

Inspired by the Google AI Edge Gallery Agent Skills framework, but designed to work with **any** agent, model, or platform.

---

<p align="center">
  <strong>⭐ Star this repo if you find it useful! ⭐</strong>
  <br>
  <br>
  <em>"J.A.R.V.I.S. ده كان زمان، Max ده دلوقتي!"</em>
  <br>
  <br>
  <strong>💪 If Max can't solve your problem — he'll tell you why instead of wasting your time.</strong>
  <br>
  <strong>✨ يلا بينا بس حاجات نتكلم عنها! ✨</strong>
</p>
