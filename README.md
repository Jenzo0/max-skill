![Max Banner](https://files.catbox.moe/d3ji1i.jpg)

<h1 align="center">🧠 Max — Universal AI Skill Framework</h1>
<h3 align="center">CTO + Senior Dev + Architect + Teacher in One Prompt · 100% Prompt-Only</h3>

<p align="center">
  <a href="https://github.com/Jenzo0/max-skill/releases"><img src="https://img.shields.io/github/v/release/Jenzo0/max-skill?style=flat-square&label=Version&color=FF6B6B" alt="Version"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT License"></a>
  <a href="https://github.com/Jenzo0/max-skill/stargazers"><img src="https://img.shields.io/github/stars/Jenzo0/max-skill?style=flat-square&label=Stars&color=yellow" alt="Stars"></a>
  <a href="https://jenzo0.github.io/max-skill/"><img src="https://img.shields.io/badge/GitHub%20Pages-Deployed-blueviolet?style=flat-square" alt="Pages"></a>
  <br>
  <img src="https://img.shields.io/badge/Model-Agnostic-4299e1?style=flat-square" alt="Model Agnostic">
  <img src="https://img.shields.io/badge/Platform-Universal-success?style=flat-square" alt="Universal">
  <img src="https://img.shields.io/badge/Locale-English%20%7C%20Arabic-orange?style=flat-square" alt="Bilingual">
  <img src="https://img.shields.io/badge/Architecture-Modular-purple?style=flat-square" alt="Modular">
  <img src="https://img.shields.io/badge/Integrations-Claude%20·%20ChatGPT%20·%20Hermes%20·%20Edge%20Gallery-blue?style=flat-square" alt="Integrations">
</p>

<p align="center">
  <em>"Senior Engineer, not just AI."</em>
  <br>
  <strong>Open Source</strong> · <strong>Model Agnostic</strong> · <strong>Platform Agnostic</strong> · <strong>100% Prompt</strong>
</p>

---

## 🚀 Quick Start

| Platform | One-Liner |
|----------|-----------|
| Claude Code / OpenCode | `curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > /tmp/max.md` then `claude --prompt "$(cat /tmp/max.md)"` |
| ChatGPT / Claude / Gemini | Paste `https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md` as system prompt |
| Edge Gallery / Gemma | `https://jenzo0.github.io/max-skill/max-super-prompt/lite/` |
| Hermes Agent | `git clone https://github.com/Jenzo0/max-skill.git` then `cp -r max-skill/max-super-prompt ~/AppData/Local/hermes/skills/persona/` |
| Cursor IDE | Paste `max-super-prompt/SKILL.md` into Settings > Custom Instructions |
| Try Online | [ClawMama](https://app.clawmama.run/skills/t40ue3/hermes) |

---

## 📦 Core Files

| File | Purpose |
|------|---------|
| [SKILL.md](max-super-prompt/SKILL.md) | Entry point - Full (1.5K tokens) |
| [Lite](max-super-prompt/lite/SKILL.md) | Lightweight (700 tokens, zero NEVER) |
| [Decision Engine](max-super-prompt/references/core/workflow.md) | Mode routing + context layering |
| [10 Golden Rules](max-super-prompt/references/core/golden-rules.md) | Core behavior constraints |
| [Persona](max-super-prompt/references/core/persona.md) | Identity and tone |
| [Response Templates](max-super-prompt/references/core/response-template.md) | Per-mode output formats |
| [Arabic Dialects](max-super-prompt/references/core/dialects.md) | 5-dialect auto-detection |
| [Capabilities](max-super-prompt/references/capabilities/) | 8 domain modules |
| [Modes](max-super-prompt/references/modes/) | 8 mode modules |
| [Tool Registry](max-super-prompt/references/tools/registry.md) | 14 ops x 7 platforms |
| [Memory Layer](max-super-prompt/references/memory/) | Persistence abstraction |
| [JS Tools](max-super-prompt/scripts/) | Edge Gallery browser tools |

---

## 📚 Examples

| Scenario | File |
|----------|------|
| Building an API with FastAPI + JWT | [examples/01-code-api.md](examples/01-code-api.md) |
| MySQL deadlock debugging | [examples/02-fast-solve-mysql-deadlock.md](examples/02-fast-solve-mysql-deadlock.md) |
| Chat system architecture | [examples/03-architect-chat-system.md](examples/03-architect-chat-system.md) |
| Async/await teaching walkthrough | [examples/04-teacher-async-await.md](examples/04-teacher-async-await.md) |
| Contributing guide walkthrough | [examples/05-contributing-guide.md](examples/05-contributing-guide.md) |

---

## 🖥️ Platform Support

| Platform | Full | Lite | Tools | Arabic |
|----------|:----:|:----:|:-----:|:------:|
| Hermes Agent | ✅ | ✅ | ✅ Native | ✅ |
| Edge Gallery | ❌ | ✅ | ✅ JS | ✅ |
| Claude / ChatGPT / Gemini | ✅ | ✅ | ✅ | ✅ |
| OpenCode / Codex CLI | ✅ | ✅ | ✅ | ✅ |
| Cursor IDE | ⚠️ | ✅ | ⚠️ | ✅ |
| Ollama | ⚠️ | ✅ | ❌ | ✅ |
| OpenRouter | ✅ | ✅ | ⚠️ | ✅ |

> Full model matrix (25+ models) -> [SUPPORTED_MODELS.md](SUPPORTED_MODELS.md)

---

## 📊 Stats

| Metric | v6.0 |
|--------|:----:|
| Mode selection accuracy | 95% |
| First-response correctness | 88% |
| Arabic dialect detection | 95% |
| Token waste | ~4% |
| NEVER directives (Gemma hazard) | 0 |
| Production-ready deliverables | 90% |

> Full comparison -> [CHANGELOG.md](CHANGELOG.md)

---

## 📖 Docs & Links

| Resource | Link |
|----------|------|
| FAQ | [docs/FAQ.md](docs/FAQ.md) |
| Roadmap | [ROADMAP.md](ROADMAP.md) |
| Changelog | [CHANGELOG.md](CHANGELOG.md) |
| Contributing | [CONTRIBUTING.md](CONTRIBUTING.md) |
| License | [LICENSE](LICENSE) - MIT |
| Security | [SECURITY.md](SECURITY.md) |
| Code of Conduct | [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) |
| Audit Report | [AUDIT-REPORT.md](AUDIT-REPORT.md) |

---

<h3 align="center">Jenzo Sky</h3>
<p align="center">Senior Engineer - Building useful AI tools.</p>
<p align="center">Star - Fork - Try with your favorite LLM</p>
