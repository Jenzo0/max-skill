# 🔌 Tool Abstraction Layer — Universal Adapter + Registry

> Load this module for any tool operation (save, search, execute, files).
> Load trigger: Agent Mode, any request involving file ops, web search, or code execution.

## Core Philosophy

Same mental model for tools, different syntax per platform. Never hardcode a single platform.

## Universal Tool Registry (v5.0)

| Operation | Concept | Hermes | Edge Gallery | Claude | ChatGPT | Fallback (if unavailable) |
|---|---|---|---|---|---|---|
| **Save data** | `store(key, val)` | `memory` tool | `run_js` memory.html | Tool use | GPT Actions | Markdown file write |
| **Load data** | `load(key)` | `memory` tool | `run_js` memory.html | Tool use | GPT Actions | Read from file |
| **Search memory** | `search(query)` | `session_search` | `run_js` memory.html | Tool use | GPT Actions | grep text files |
| **Web search** | `search_web(q)` | `web_search` | `run_js` search.html | `web_search` | Web Browsing | `curl` DuckDuckGo API |
| **Execute code** | `run(code)` | `terminal` / `execute_code` | — (provide script) | `bash` | Code Interpreter | Paste code block for user |
| **Read file** | `read(path)` | `read_file` | — | Tool use | Code Interpreter | `cat` via terminal |
| **Write file** | `write(path, content)` | `write_file` | — | Tool use | Code Interpreter | `echo` + redirect |
| **Edit file** | `edit(path, old, new)` | `patch` | — | Tool use | Code Interpreter | sed + explain |
| **Ask user** | `ask(question)` | `clarify` | Text response | Direct | Direct | — |
| **Delegate** | `delegate(task)` | `delegate_task` | — | Projects | GPT Actions | Sequential execution |
| **Screenshot** | `capture()` | `browser_vision` | — | Tool use | — | Describe steps |
| **Search files** | `find(pattern)` | `search_files` | — | `grep` | Code Interpreter | `find`/`grep` via terminal |
| **Notify** | `notify(msg)` | Telegram/WhatsApp send | `console.log` | — | — | Log to file |
| **Schedule** | `cron(schedule, task)` | `cronjob` tool | — | — | — | at/cron via terminal |

### Platform Compatibility Matrix

| Platform | Terminal | File Ops | Web | Memory | Delegate | Vision | Cron |
|---|---|---|---|---|---|---|---|
| **Hermes Agent** | ✅ Full | ✅ Full | ✅ Full | ✅ Structured | ✅ Background | ✅ | ✅ Native |
| **Claude Code** | ✅ bash | ✅ Tool use | ✅ Via tool | ✅ Via tool | ✅ Projects | ✅ | ❌ |
| **Claude (Chat)** | ❌ | ✅ Artifacts | ✅ Web | ✅ Projects | ❌ | ✅ | ❌ |
| **ChatGPT** | ✅ Code Interpreter | ✅ Interpreter | ✅ Browsing | ✅ Memory | ✅ GPT Actions | ✅ | ❌ |
| **Edge Gallery** | ❌ | ❌ | ✅ search.html | ✅ memory.html | ❌ | ✅ vision.html | ❌ |
| **OpenCode CLI** | ✅ Full | ✅ Full | ❌ | ❌ | ✅ | ❌ | ❌ |

**Rule**: If a platform lacks the tool, use the Fallback column. If even the fallback is missing, provide executable code the user can run locally.

## Platform Detection

Detect platform by checking available tool names:

```python
if "terminal" in available_tools → Hermes Agent
if "run_js" in available_tools → Edge Gallery
if "bash" in available_tools → Claude Code
if "python" in available_tools → ChatGPT / Code Interpreter
```

If undetectable, fall back to: provide runnable code + markdown blocks the user can copy.

## Edge Gallery — JS Tool Reference

Only when `run_js` is available:

### Memory System — `memory.html`
```json
{"script name": "memory.html", "data": "{\"action\": \"ACTION\", \"key\": \"...\", \"value\": \"...\"}"}
```

| Action | Description | Required |
|---|---|---|
| `save` | Store a value | `key`, `value` |
| `load` | Retrieve a value | `key` |
| `search` | Find keys by query | `query` |
| `delete` | Remove a key | `key` |
| `clear` | Remove ALL data | (none) |
| `vault_save` | AES-256-GCM encrypt + store | `key`, `value`, `password` |
| `vault_load` | Decrypt + retrieve | `key`, `password` |
| `export` | Export all data as JSON | (none) |
| `import` | Import from JSON export | `data` |

### Web Search — `search.html`
```json
{"script name": "search.html", "data": "{\"query\": \"...\", \"max_results\": 5}"}
```

### Interactive Dashboard — `dashboard.html`
```json
{"script name": "dashboard.html", "data": "{\"mode\": \"MODE\"}"}
```
Modes: `memory_tree`, `stats`, `skills_overview`, `evolution_map`

### Vision Analysis — `vision.html`
```json
{"script name": "vision.html", "data": "{\"url\": \"https://...image.jpg\"}"}
```
Analyzes: dominant colors, object detection proxy, text overlay, edge density.

### Voice TTS — `voice.html`
```json
{"script name": "voice.html", "data": "{\"text\": \"Text to speak\"}"}
```
Optional: `{voice: "female|male", rate: 0.5..2.0, pitch: 0.5..2.0}`.

## Tool Usage Rules

1. **Check availability first** — don't use `run_js` on Hermes or `terminal` on Edge Gallery
2. **Fail gracefully** — if preferred tool fails, try fallback, then offer user manual steps
3. **Log tool calls** — always show what tool you're using and what it returned
4. **Don't simulate** — if you can't actually run the tool, say so, don't fabricate output
5. **Abstract operations, not syntax** — think `store(key, value)` not `memory(action="add", ...)`
