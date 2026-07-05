---
name: max-super-prompt
---

# Roadmap — Max Super Prompt

## Vision

Transform Max from a single persona prompt into a complete **AI Skill Framework** — modular, extensible, platform-agnostic, and production-ready for any LLM or agent system.

## Priorities

### ✅ Done (v5.0)
- [x] 3 new capability files: AI/ML, Mobile, Desktop
- [x] Tool Registry with permissions, fallback, and platform matrix
- [x] Merged js-tools → core-tool-abstraction (unified reference)
- [x] CHANGELOG.md + ROADMAP.md
- [x] Version numbers removed from public titles
- [x] "Egyptian Arabic" → "Bilingual English + Arabic" rebranding

### 🔜 Next (v5.x)

| Priority | Item | Impact |
|---|---|---|
| P1 | **Prompt Compression**: target SKILL.md <5KB without losing info | Reduced tokens, faster load |
| P2 | **Memory Interface Layer**: formal abstraction for Hermes memory, SQLite, JSON, Vector DB | Cross-platform persistence |
| P2 | **Architecture Diagrams**: decision flow, tool resolution flow, memory flow (for contributors) | Easier contributions |
| P3 | **Capability: Game Development** (Unity, Unreal, Godot, Phaser) | Broader coverage |
| P3 | **Capability: Embedded Systems** (Arduino, ESP32, Raspberry Pi, Zephyr) | IoT/embedded coverage |

### 🚀 Future (v6+)

| Theme | Description |
|---|---|
| **Benchmark Suite** | Automated tests measuring Max across 5+ LLMs (accuracy, tokens, latency, adherence) |
| **Plugin System** | Third-party capability modules that anyone can author and publish |
| **Auto-Compressor** | Script that analyzes SKILL.md + references and suggests token savings |
| **Multi-Agent Orchestration** | Max as the coordinator delegating sub-tasks to specialized agents |
| **Visual Skill Builder** | GUI tool for assembling persona skills without editing markdown |

## How to Contribute

1. Fork the repo
2. Improve modules under `references/`
3. Test with the Lite version for Edge Gallery safety
4. Submit a PR

> *"Every great achievement starts with the decision to try."* 🚀
