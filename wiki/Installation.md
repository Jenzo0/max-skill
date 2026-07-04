# 📦 Installation Guide

## Google AI Edge Gallery

1. Open **Edge Gallery** app
2. Select your model → **Agent Skills** tab
3. Tap **(+)** → **Load skill from URL**
4. Paste:
   ```
   https://jenzo0.github.io/max-skill/max-super-prompt/
   ```
5. Tap **Add**

### Local Import
1. Download the `max-super-prompt/` folder
2. Open **Edge Gallery** → **(+)** → **Import local skill**
3. Select the folder

---

## Claude Code (Anthropic)

```bash
# Method 1: CLI prompt injection
claude --prompt "$(curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md)"

# Method 2: .claude.md file
curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > .claude.md
```

---

## OpenAI API / OpenRouter

```python
import openai
openai.base_url = "https://openrouter.ai/api/v1"

response = openai.chat.completions.create(
  model="openai/gpt-4o",
  messages=[
    {
      "role": "system",
      "content": """<PASTE FULL SKILL.md HERE>"""
    },
    {"role": "user", "content": "Build me a FastAPI auth API"}
  ]
)
```

---

## ChatGPT / Claude.ai

1. Open **Settings** → **Custom Instructions**
2. Paste the entire `SKILL.md` content in the **System Prompt** field
3. Save and start chatting

---

## Ollama (Local)

```bash
# Create a modelfile
echo "FROM gemma-4
SYSTEM \"\"\"
$(curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md)
\"\"\"" > Maxfile

# Build and run
ollama create max -f Maxfile
ollama run max
```

---

## Cursor / Copilot

1. Create `.cursorrules` or `.github/copilot-instructions.md`
2. Paste SKILL.md contents
3. Start coding with Max persona active
