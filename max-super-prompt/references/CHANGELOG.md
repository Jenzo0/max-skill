---
name: max-super-prompt
---

# Changelog — Max Super Prompt

All notable changes to the Max Super Prompt skill.

## 5.0 — 2026-07-05 — Capability Expansion + Tool Registry

### Added
- **3 new capability modules**: `capabilities-ai-ml.md`, `capabilities-mobile.md`, `capabilities-desktop.md`
- **Tool Registry v5.0**: Permissions, fallback chain per tool, platform compatibility matrix
- **CHANGELOG.md** + **ROADMAP.md** — version tracking and vision documentation

### Changed
- **core-tool-abstraction.md**: Merged from old `core-tool-abstraction.md` + `js-tools.md` — unified registry with 14 operations × 5 platforms
- **SKILL.md**: Updated Dynamic Capability Loading table with 3 new modules; compressed sections
- **js-tools.md**: Removed (content merged into core-tool-abstraction.md)

### Fixed
- Version numbers removed from titles everywhere (README, repo description, badges)
- "Egyptian Arabic" label replaced with "Bilingual English + Arabic" on repo topics

## 4.0 — 2026-07-05 — Modular Architecture

### Added
- Modular reference system: 12 independent `.md` modules under `references/`
- Decision Engine with 7 modes (Architect, Code, Teacher, Fast Solve, Absolute, Agent, DevOps)
- Dynamic Capability Loading (backend, frontend, devops loaded on-demand)
- 4 Context Layers (System, Project, Memory, Task)
- Tool Abstraction Layer (Hermes, Edge Gallery, Claude, ChatGPT)
- Lite version `<3KB` for Edge Gallery / Gemma
- Arabic Dialect Detection (5 dialects) + GitHub Pages hosting guide

### Changed
- Monolithic v3.0 split into compressed SKILL.md (5.9KB) + 12 reference files
- "NEVER" directives removed from Lite version (Gemma compatibility fix)

## 3.0 — 2026-07-04 — Initial Release

### Added
- First modular version with Edge Gallery hosting
- JS tools: memory.html, search.html, vision.html, voice.html, dashboard.html
- Wiki documentation pages
- GitHub Pages deployment with `.nojekyll` + `_config.yml`
- SEO landing page (`index.html`)
