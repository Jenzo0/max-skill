# 🤝 Contributing to Max

> **Mode**: Documentation | **File**: CONTRIBUTING.md

## How to Contribute

We welcome contributions of all kinds:

- 🐛 Bug reports and fixes
- ✨ New features and capability modules
- 📝 Documentation improvements
- 🌍 Translations and dialect improvements
- 🚀 Performance and token efficiency optimizations

## Adding a New Capability

1. Create `references/capabilities/<name>.md` following the template below
2. Register it in `SKILL.md`'s Dynamic Module Loading section
3. Add the import trigger capability reference
4. Run the token budget check
5. Submit a PR

### Capability Template

```markdown
# 🏷️ <Capability Name> Capabilities

> Load trigger: <keywords>

## Core Stack

| Language | Frameworks |
|---|---|
| ... | ... |

## Key Principles

| Principle | Practice |
|---|---|
| ... | ... |

## Deliverable Checklist

- [ ] Item 1
- [ ] Item 2

## Best Practices

- Rule 1 with explanation
- Rule 2 with explanation
```

## Adding a New Mode

1. Create `references/modes/<name>.md` with:
   - Trigger keywords
   - Behavior description
   - Output format (with example)
   - Procedure if applicable
2. Add to Decision Engine table in `SKILL.md`
3. Add to Dynamic Module Loading if it needs capabilities

## Style Guide

- **Markdown**: GitHub-Flavored Markdown
- **Frontmatter**: YAML format (name, description, version, author)
- **Tables**: Pipe-formatted with alignment
- **Code blocks**: Language-annotated triple backticks
- **Headings**: ATX-style (`##`, `###`)
- **Emojis**: Use as visual cues, not replacements for text
- **Arabic**: Include Arabic terms in dialect modules (with context)
- **Line length**: Soft wrap at 100 chars for readability

## Token Budget Policy

- SKILL.md: ≤2,000 tokens (cl100k_base)
- Lite SKILL.md: ≤800 tokens
- Reference module: ≤500 tokens each
- Capability module: ≤500 tokens each

Run the check before submitting:
```bash
python .github/workflows/token-budget-check.yml
```

## PR Workflow

1. Fork → Branch → Commit → Push → PR
2. PR title format: `[type]: brief description`
   - `[feature] Add Rust capability module`
   - `[fix] Resolve circular reference in workflow.md`
   - `[docs] Update Quick Start guide`
3. Link any related issues
4. Ensure token budget passes
5. Test with Lite version for Edge Gallery compatibility
6. Request review

## Code of Conduct

All contributors must adhere to our [Code of Conduct](CODE_OF_CONDUCT.md). Be respectful, constructive, and collaborative.
