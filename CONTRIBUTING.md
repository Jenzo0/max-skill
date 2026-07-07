# 🤝 Contributing to Max Super Prompt

Thank you for considering contributing! This project thrives on community additions — modules, platforms, modes, and improvements.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Module Development Guide](#module-development-guide)
- [Adding a New Capability Domain](#adding-a-new-capability-domain)
- [Adding a New Mode](#adding-a-new-mode)
- [Testing Your Changes](#testing-your-changes)
- [Pull Request Process](#pull-request-process)
- [Style Guide](#style-guide)

## Code of Conduct

- Be respectful and constructive in all discussions
- Focus on technical merit — all ideas are welcome
- No discrimination, harassment, or toxicity

## How to Contribute

### 1. Fork & Clone

```bash
git clone https://github.com/<your-username>/max-skill.git
cd max-skill
```

### 2. Choose What to Work On

| Area | Where to Start | Difficulty |
|---|---|---|
| **New capability domain** | Add `references/capabilities-<name>.md` | Medium |
| **New decision mode** | Update `SKILL.md` Decision Engine + core-modes reference | Hard |
| **Platform mapping** | Update `core-tool-abstraction.md` | Medium |
| **Bug fix / doc improvement** | Edit relevant `.md` file | Easy |
| **Lite version sync** | Update `lite/SKILL.md` to match full version | Easy |
| **Translation / locale** | Add dialect support in `arabic-dialect-system.md` | Medium |

### 3. Create a Feature Branch

```bash
git checkout -b feat/my-improvement
```

## Module Development Guide

Each reference module under `references/` is a standalone `.md` file that follows this template:

```markdown
# Module Name

> Brief description (1–2 lines)

## When to Load

| Condition | Action |
|---|---|
| Mode matches X | Load via `skill_view()` |
| Platform is Y | Use Y-specific syntax |

## Content

[Your knowledge — code snippets, tables, conventions, patterns]
```

### Rules

- Keep each module **≤ 500 tokens** (tokenize with `tiktoken` or any tokenizer)
- Use **absolute paths** for cross-references: `skill_view(name='max-super-prompt', file_path='references/<module>.md')`
- Do NOT import modules that import each other cyclically (see dependency graph in SKILL.md)
- Test with both Full and Lite versions

## Adding a New Capability Domain

1. Create `references/capabilities-<name>.md`
2. Add it to **SKILL.md** — `Token-Budget Enforcement Layer` → Module Registry table
3. Add it to **README.md** — Repository Structure tree + Mode Reference table
4. Add loading condition in **core-modes.md** (if a new mode)
5. Update Lite version if the domain is essential

### Capability Template

```markdown
# Capabilities: <Domain Name>

> Expert knowledge for <domain>

## Core Stack

| Technology | Expertise Level | Notes |
|---|---|---|
| ... | Proficient / Expert / Master | ... |

## Patterns & Conventions

[Domain-specific patterns, anti-patterns, best practices]

## Common Tasks

[Frequent operations with code templates]
```

## Adding a New Mode

1. **Decision Engine**: Add row to scoring matrix in `SKILL.md` — keywords, context cues, base energy
2. **Full definition**: Add section in `core-modes.md` — output format, examples, behavior rules
3. **Capability mapping**: Link to relevant capability modules in the Token-Budget table
4. **README**: Add row to Mode Reference table
5. **Lite version**: Add trigger-only entry to `lite/SKILL.md`

## Testing Your Changes

### 1. Token Budget Check (CI — Automatic)

This repository has a **GitHub Actions workflow** (`.github/workflows/token-budget-check.yml`) that automatically runs on every push and pull request touching `SKILL.md`, `lite/SKILL.md`, or `references/` files. It enforces:

- **SKILL.md**: ≤ 500 lines, ≤ 5,000 tokens
- **Reference modules**: ≤ 2,000 tokens each

If the workflow fails, your changes exceed the budget — optimize before merging.

### 2. Local Token Check (Fallback)

For quick local checks before committing:

```bash
# Count tokens in your module
python -c "import tiktoken; enc = tiktoken.get_encoding('cl100k_base'); print(len(enc.encode(open('references/my-module.md').read())))"
```

### 3. Lite Compatibility

Copy the full SKILL.md to `lite/SKILL.md` and strip:
- Token-Budget Enforcement Layer (keep only "Load when active" table)
- Tool Abstraction (keep basic mapping only)
- Capability modules (remove full reference list)

### 4. Render Check

Preview on GitHub or any Markdown renderer:
- Tables are aligned and readable
- Code blocks have correct language tags
- No broken links

### 5. Integration Test

```text
1. [Your mode / capability] — does the model load it correctly?
2. Edge case — unrelated query → should fall back to Teacher mode
3. Mixed mode — query with keywords from 2 modes → should use scoring
```

## Pull Request Process

1. **Run the checklist** above before submitting
2. **Keep PRs focused** — one feature or fix per PR
3. **Update docs** — if you add a capability, update README/CHANGELOG/ROADMAP
4. **Version bump** — minor: capability addition, patch: bug fix, major: breaking change
5. **PR template**:

```markdown
## Description
[What does this change do?]

## Type of Change
- [ ] New capability module
- [ ] New mode
- [ ] Bug fix
- [ ] Documentation update
- [ ] Platform mapping

## Checklist
- [ ] Token budget respected (< 500 tokens per module)
- [ ] Lite version updated (if needed)
- [ ] README updated
- [ ] CHANGELOG updated
- [ ] Tested with 3+ prompts

## Related Issues
[Closes #...]
```

## Style Guide

- **Markdown**: GitHub-Flavored Markdown (tables, fenced code blocks, task lists)
- **Language**: English for public content, English + Arabic for persona responses
- **Tables**: Always use pipe syntax with alignment (`|:---|---:|`)
- **Code blocks**: Specify language (`python`, `bash`, `json`, `yaml`)
- **Version numbers**: Do NOT include in titles or descriptions (kept in CHANGELOG only)
- **Lite version**: Zero `NEVER` directives — causes Gemma hang
- **File names**: lowercase with hyphens (`capabilities-my-domain.md`)

---

> **Questions?** Open a [Discussion](https://github.com/Jenzo0/max-skill/discussions) or tag [@Jenzo0](https://github.com/Jenzo0).
>
> *Let's build the universal engineer persona — together.* 🚀
