# Supported Models — Full Compatibility Matrix

> This file contains the complete model compatibility list.
> For the condensed top-picks table, see [README.md](README.md#-model-compatibility).

---

## Complete Model Matrix

| Provider | Model | Full | Lite | Tools | Arabic | Memory | Status |
|----------|-------|:----:|:----:|:-----:|:------:|:------:|--------|
| **Anthropic** 🟠 | Sonnet 5 | ✅ | ✅ | ✅ | ✅ | ✅ | 🏆 Recommended |
| | Opus 5 | ✅ | ✅ | ✅ | ✅ | ✅ | 🏆 Recommended |
| | Fable 5 | ✅ | ✅ | ✅ | ✅ | ✅ | 🏆 Recommended |
| **OpenAI** 🟢 | GPT 5.4 | ✅ | ✅ | ✅ | ✅ | ✅ | 🏆 Excellent |
| | GPT 5.5 | ✅ | ✅ | ✅ | ✅ | ✅ | 🏆 Excellent |
| | o5 | ⚠️ | ✅ | ❌ | ✅ | ❌ | Good |
| **Google** 🔵 | Gemini 3.5 Flash | ⚠️ | ✅ | ⚠️ | ✅ | ❌ | Good |
| | Gemini 3.5 Pro | ✅ | ✅ | ⚠️ | ✅ | ❌ | Good |
| **Meta** ⚫ | Llama 5 | ✅ | ✅ | ⚠️ | ✅ | ❌ | Good |
| | Llama 4 Turbo | ❌ | ✅ | ❌ | ⚠️ | ❌ | Lite only |
| **Alibaba** 🟤 | QWEN 3.7 Plus | ✅ | ✅ | ✅ | ✅ | ✅ | 🚀 Fast |
| | QWEN 3.5 Max | ✅ | ✅ | ✅ | ✅ | ⚠️ | Fast |
| **DeepSeek** 🟢 | DeepSeek V4 Flash | ✅ | ✅ | ✅ | ✅ | ✅ | 🚀 Fast |
| | DeepSeek V4 | ✅ | ✅ | ✅ | ✅ | ✅ | Recommended |
| **Zhipu AI** 🟦 | GLM 5.2 | ✅ | ✅ | ⚠️ | ✅ | ⚠️ | Good |
| | GLM 5.1 Lite | ❌ | ✅ | ❌ | ✅ | ❌ | Lite only |
| **Moonshot** 🟣 | KIM 2.7 | ✅ | ✅ | ⚠️ | ⚠️ | ❌ | Good |
| | KIM 2.5 | ✅ | ✅ | ❌ | ⚠️ | ❌ | Basic |
| **Mistral** 🟡 | Mistral 4 Large | ✅ | ✅ | ⚠️ | ✅ | ✅ | Good |
| | Mistral 4 Small | ❌ | ✅ | ❌ | ⚠️ | ❌ | Lite only |
| **Microsoft** 🔵 | Phi-5 | ❌ | ✅ | ❌ | ⚠️ | ❌ | Lite only |
| **xAI** ⚫ | Grok 4 | ✅ | ✅ | ⚠️ | ✅ | ✅ | Good |
| **01.AI** 🟠 | Yi 3.5 Max | ✅ | ✅ | ⚠️ | ✅ | ⚠️ | Good |
| **NVIDIA** 🟢 | Nemotron 3 Ultra | ✅ | ✅ | ⚠️ | ✅ | ❌ | Good |
| **Cohere** 🟤 | Command R+ 2 | ✅ | ✅ | ⚠️ | ✅ | ⚠️ | Good |
| **Reka** 🟣 | Reka Core 2.5 | ✅ | ✅ | ⚠️ | ✅ | ⚠️ | Good |

---

## Platform Support

| Platform | Full | Lite | Tools | Arabic | Memory |
|----------|:----:|:----:|:-----:|:------:|:------:|
| Hermes Agent | ✅ | ✅ | ✅ Native | ✅ | ✅ |
| Edge Gallery | ❌ | ✅ | ✅ JS | ✅ | ✅ |
| OpenCode CLI | ✅ | ✅ | ✅ | ✅ | ❌ |
| Cursor | ⚠️ | ✅ | ⚠️ | ✅ | ✅ |
| Ollama | ⚠️ | ✅ | ❌ | ✅ | ❌ |
| OpenRouter | ✅ | ✅ | ⚠️ | ✅ | ❌ |
| Codex CLI | ✅ | ✅ | ✅ | ✅ | ❌ |
| Any OpenAI API | ✅ | ✅ | ⚠️ | ✅ | ❌ |

---

## Integration Guide

| Provider | Model | Version | Integration Method |
|----------|-------|:-------:|:-------------------|
| Anthropic | Sonnet 5 | Full | Paste as system prompt |
| Anthropic | Opus 5 | Full | Paste as system prompt |
| Anthropic | Fable 5 | Full | Paste as system prompt |
| OpenAI | GPT 5.4 | Full + Lite | System message |
| OpenAI | GPT 5.5 | Full | System message |
| Google | Gemini 3.5 Flash | Lite | Paste as system prompt |
| Google | Gemini 3.5 Pro | Full | Paste as system prompt |
| DeepSeek | DeepSeek V4 Flash | Full | System message |
| Alibaba | QWEN 3.7 Plus | Full | System prompt |
| xAI | Grok 4 | Full + Lite | System message |
| Mistral | Mistral 4 Large | Full + Lite | System message |

> 💡 **Tip:** Paste the raw SKILL.md URL into any platform that supports system prompts:
> `https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md`
