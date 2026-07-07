# 📥 Installation

> How to use Max Super Prompt on any platform.

---

## 🏆 Full v5.1 (Recommended — 9.4KB)

### Claude Code / OpenCode / Codex
```bash
curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > /tmp/max.md
claude --prompt "$(cat /tmp/max.md)"
# or: opencode --prompt "$(cat /tmp/max.md)"
```

### Hermes Agent
```bash
git clone https://github.com/Jenzo0/max-skill.git
cp -r max-skill/max-super-prompt ~/AppData/Local/hermes/skills/persona/
# Then load: skill_view(name='max-super-prompt')
# For reference modules: skill_view(name='max-super-prompt', file_path='references/<module>.md')
```

### ChatGPT / OpenRouter / Any API
Paste the contents of `max-super-prompt/SKILL.md` into the **System Prompt** field.

Available at:
```
https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md
```

### Ollama / Local Models
```bash
curl -s https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md
# Pipe to Ollama: cat /tmp/max.md | ollama run llama3
```

---

## 🪶 Lite v5.1 (Edge Gallery / Gemma — 3.0KB)

### Google AI Edge Gallery
**URL import:**
```
https://jenzo0.github.io/max-skill/max-super-prompt/lite/
```

**Local import:** Download `max-super-prompt/lite/SKILL.md` → Edge Gallery (+) → Import local skill.

**Models tested:** Gemma-4-E4B-IT, Gemma-3-27B

---

## 🛠️ Reference Modules (Full v5.1 only)

Load extended modules on demand for deep dives:

```
skill_view(name='max-super-prompt', file_path='references/core-modes.md')
skill_view(name='max-super-prompt', file_path='references/core-context-layers.md')
skill_view(name='max-super-prompt', file_path='references/core-tool-abstraction.md')
```

---

## ⚡ Which Version Should I Use?

| Use Case | Version |
|---|---|
| Claude, ChatGPT, Hermes, OpenRouter | 🏆 **Full v5.1** |
| Edge Gallery, Gemma | 🪶 **Lite v5.1** |
| Low-token-budget applications | 🪶 **Lite v5.1** |
| Complex projects with deep dives | 🏆 **Full v5.1** |
| Quick prototyping | 🏆 **Full v5.1** |
