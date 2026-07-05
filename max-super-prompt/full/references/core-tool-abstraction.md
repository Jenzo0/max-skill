# 🔌 Tool Abstraction Layer — Universal Adapter

> Load this module when you need to use tools (save, search, execute) and want to know the right platform-specific syntax.
> Load trigger: Agent Mode, any request involving file operations, web search, or code execution.

## Core Philosophy

The same mental model for tools, different syntax per platform. Instead of hardcoding `run_js` (Edge Gallery), use a universal concept and map it to the platform's native API.

## Universal Tool API

| Operation | Concept | Edge Gallery | Hermes Agent | Claude | ChatGPT |
|---|---|---|---|---|---|
| **Save data** | `store(key, value)` | `run_js` memory.html | `memory` tool | Tool use | GPT Actions |
| **Load data** | `load(key)` | `run_js` memory.html | `memory` tool | Tool use | GPT Actions |
| **Search memory** | `search(query)` | `run_js` memory.html | `session_search` | Tool use | GPT Actions |
| **Web search** | `fetch(url)` or `search(query)` | `run_js` search.html | `web_search` / `curl` | `web_search` | Web Browsing |
| **Execute code** | `run(code)` | — | `terminal` / `execute_code` | `bash` | Code Interpreter |
| **Read file** | `read(path)` | — | `read_file` | Tool use | Code Interpreter |
| **Write file** | `write(path, content)` | — | `write_file` | Tool use | Code Interpreter |
| **Ask user** | `ask(question)` | Text response | `clarify` | Direct response | Direct response |
| **Edit file** | `edit(path, old, new)` | — | `patch` / `sed` | Tool use | Code Interpreter |
| **Delegate** | `delegate(task)` | — | `delegate_task` | Projects | GPT Actions |
| **Screenshot** | `capture()` | — | `browser_vision` | Tool use | — |
| **Search files** | `find(pattern)` | — | `search_files` | `grep` | Code Interpreter |

## Platform Detection

Detect which platform you're running on by checking available tool names:

```python
# Pseudo-logic for adaptive tool selection
if "terminal" in available_tools → Hermes Agent
if "run_js" in available_tools → Edge Gallery
if "bash" in available_tools → Claude Code
if "python" in available_tools → ChatGPT / Code Interpreter
```

If you can't detect the platform, fall back to:
- **Provide code** the user can run locally (Python scripts, bash commands, curl)
- **Use markdown code blocks** that the user can copy-paste
- **Describe the steps** for manual execution

## Abstraction Examples

### Example 1: Save a user preference
```
Concept: store("theme", "dark")
→ Edge Gallery: run_js memory.html {"action":"save","key":"theme","value":"dark"}
→ Hermes: memory(action="add", target="user", content="User prefers dark theme")
→ Claude: tool_use(name="memory", input={"action":"save","key":"theme","value":"dark"})
→ ChatGPT: "I've noted your preference for dark theme."
```

### Example 2: Search the web for documentation
```
Concept: search_web("FastAPI middleware documentation")
→ Edge Gallery: run_js search.html {"query":"FastAPI middleware"}
→ Hermes: web_search(query="FastAPI middleware documentation")
→ Claude: web_search(query="FastAPI middleware documentation")
→ ChatGPT: Web Browsing search "FastAPI middleware documentation"
→ Fallback: curl -s "https://api.duckduckgo.com/?q=FastAPI+middleware&format=json"
```

## Edge Gallery — JS Tool Reference

Only when `run_js` is available. See `js-tools.md` for full payload reference.

| Script | Purpose | Key Example |
|---|---|---|
| `memory.html` | Persistent KV store + AES vault + auto-backup | `{"action":"save","key":"x","value":"y"}` |
| `search.html` | Web search via CORS proxy | `{"query":"latest AI news"}` |
| `vision.html` | Image color/texture analysis | `{"url":"https://..."}` |
| `voice.html` | Text-to-Speech | `{"text":"Hello"}` |
| `dashboard.html` | Stats + memory tree viewer | `{"mode":"stats"}` |
