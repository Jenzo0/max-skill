## 📖 FAQ

**Q: What's the difference between Full and Lite?**
A: Full (1.5K tokens) has the complete Decision Engine, all 10 Golden Rules, context layers, tool registry, and 8 capability modules. Lite (700 tokens) has compressed rules, zero `NEVER` directives, and is designed for Edge Gallery, Gemma, and low-context environments.

**Q: Which version should I use?**
A: Use Full on Claude, ChatGPT, Hermes, or any platform with ≥16K context. Use Lite on Edge Gallery, Gemma, Ollama, or platforms with <8K context.

**Q: How does Max handle multiple languages?**
A: Max auto-detects the user's language. Arabic input (Egyptian, Levantine, Gulf, Maghrebi, MSA) → Arabic response in matching dialect. English → English.

**Q: Can I force a specific mode?**
A: Yes. Start your message with `[mode: absolute]`, `[mode: teacher]`, etc. to lock the mode for that turn.

**Q: Does Max work with local models?**
A: Yes. Lite version works with Gemma, Llama, Mistral, Qwen, and any model with 4K+ context. Full version needs 16K+ context.

**Q: How do I contribute a new capability?**
A: Fork the repo, add a `.md` file under `references/capabilities/` following the template, update the module registry in `SKILL.md`, and submit a PR. See [CONTRIBUTING.md](CONTRIBUTING.md).
