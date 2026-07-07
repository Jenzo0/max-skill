---
name: max-super-prompt
---

# Changelog — Max Super Prompt

All notable changes to the Max Super Prompt skill.

## 6.0 — 2026-07-07 — Enterprise Universal AI Skill Framework

### Added
- **Enterprise modular architecture**: `references/core/`, `modes/`, `capabilities/`, `memory/`, `tools/` subdirectories
- **2 new capability modules**: `database.md` (SQL/NoSQL, ORMs, performance), `security.md` (OWASP Top 10, web security, infra security)
- **Memory abstraction layer**: `strategy.md` (interface spec) + `persistence.md` (6 backend implementations)
- **Tool Registry v6.0**: 14 operations × 7 platforms with fallback chains & platform detection
- **Practical examples directory**: `examples/01-code-api.md` through `examples/05-contributing-guide.md`
- **GitHub Issue Templates**: `bug_report.md`, `feature_request.md`, `pull_request_template.md`
- **Open-source supporting files**: `SECURITY.md`, `CODE_OF_CONDUCT.md`, `SUPPORT.md`
- **Complete AUDIT-REPORT.md**: 28 issues identified across 8 categories
- **Token budget CI workflow**: Updated for recursive subdirectory checking

### Changed
- **SKILL.md**: Compressed from ~2,300 tokens to ~1,475 tokens (36% reduction)
- **README.md**: Completely rewritten with Why Max, Architecture, Examples, Benchmarks, FAQ, Comparison table
- **Lite SKILL.md**: Updated to v6.0-lite, zero NEVER directives (2,924 bytes / ~700 tokens)
- **Decision Engine**: Deterministic routing tree — weighted keywords × base energy + mode locking
- **Capability modules**: Refreshed with current frameworks (FastAPI 2026 era, React 19, Kwai, etc.)
- **CONTRIBUTING.md**: Updated for new subdirectory module structure
- **ROADMAP.md**: Updated with v6+ milestones (Plugin SDK Q3, Multi-Agent Q1 2027)

### Removed
- Flat `references/*.md` files (migrated to subdirectories)
- `wiki/` directory (content merged into README + modular references)

## 5.1 — 2026-07-05 — Scored Decision Engine + Token-Budget + MoA Fix

### Added
- **Scored Mode Selection Protocol**: Weighted keyword matrix (×2) + context cues (×1) + base energy tuning → deterministic score-based mode selection
- **Token-Budget Enforcement Layer**: Module registry with token costs, dependency graph, context-dependent greedy fit algorithm + 4-tier budget rules
- **CONTRIBUTING.md**: Full contributor onboarding with module template, PR workflow, token-budget check, Lite sync guide
- **Mermaid Architecture Diagram** in README — interactive system flow visualization (GitHub-rendered)
- **Demo Gallery** in README — scored mode selection examples with real query/score/output

### Changed
- **Decision Engine**: "NEVER mix modes" replaced with primary/secondary blending (|Δ| ≤ 1 allows mixing) + required `mode_selection_reason` output
- **README**: Architecture section replaced with Mermaid flowchart + Token-Budget Load Algorithm; old Dynamic Module Loading table merged into new Token-Budget section
- **Contributing section**: Points to new CONTRIBUTING.md with full workflow
- **MoA script** (`moa_v6_multi_provider.py`): Repaired from dead OpenCode Zen (403) + OpenRouter (dead free models) to working **NVIDIA NIM** + **Google Gemini** — 5/5 models now functional

### Fixed
- MoA v8.7: OpenCode Zen keys (403) + OpenRouter (no free models) replaced with NVIDIA NIM (40 RPM free) + Google Gemini — all 5 models contribute to aggregation

### Reproducibility
- MoA evaluation (5 models, 5/5 contributed): **SKILL 87/100 · REPO 72/100** — verified on NVIDIA NIM + Gemini 2.5 Flash

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
