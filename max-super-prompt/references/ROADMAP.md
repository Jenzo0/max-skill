---
name: max-super-prompt
---

# Roadmap — Max Universal AI Skill Framework

## Vision

Transform Max from a single persona prompt into a complete **AI Skill Framework** — modular, extensible, platform-agnostic, production-ready for any LLM or agent system, with a community skill ecosystem.

## What's New in v6.0

| Feature | Status |
|---------|--------|
| Enterprise modular architecture (core/modes/capabilities/memory/tools) | ✅ Done |
| SKILL.md compressed 36% (~1,475 tokens) | ✅ Done |
| Memory abstraction layer (strategy + 6 backends) | ✅ Done |
| Tool Registry v6.0 (14 ops × 7 platforms) | ✅ Done |
| Database + Security capability modules | ✅ Done |
| Practical examples directory (5 guides) | ✅ Done |
| Open-source files (SECURITY, CODE_OF_CONDUCT, SUPPORT) | ✅ Done |
| GitHub Issue templates | ✅ Done |
| Zero NEVER directives in Lite (Gemma-safe) | ✅ Done |

### 🔜 Next (v6.x)

| Priority | Item | Impact |
|---|---|---|
| P1 | **Plugin SDK**: Define standard for third-party capability modules | Community contributions |
| P2 | **Skill Marketplace**: Hosted community registry for user-contributed skills | Discovery & reuse |
| P2 | **Auto-Compressor**: Script that analyzes SKILL.md + references and suggests token savings | Performance |
| P3 | **Capability: Game Development** (Unity, Unreal, Godot) | Broader coverage |
| P3 | **Capability: Embedded Systems** (Arduino, ESP32, Zephyr) | IoT coverage |
| P3 | **Benchmark Suite**: Automated tests across LLMs (accuracy, tokens, adherence) | Quality |

### 🚀 Future (v7+)

| Theme | Description | Target |
|---|---|---|
| **Memory Providers** | Redis adapter, SQLite backend, Vector DB (Chroma/Qdrant) | Q4 2026 |
| **Multi-Agent Runtime** | Max as coordinator delegating to specialized sub-agents | Q1 2027 |
| **Community Skill Library** | Published skill registry with versioning and dependency management | Q1 2027 |
| **Tool Providers SDK** | Third-party tool integrations via webhook/plugin | Q2 2027 |
| **Visual Skill Builder** | GUI for assembling persona skills without markdown editing | Q2 2027 |

## How to Contribute

1. Fork the repo
2. Add/improve modules under `references/{core,modes,capabilities,memory,tools}/`
3. Ensure token budget passes (run the CI check)
4. Test with Lite version for Edge Gallery safety
5. Submit a PR
