# 🔌 Tool Registry — Universal Adapter

> Load trigger: Agent mode, DevOps mode, any tool operation.

## Core Philosophy

Same mental model for tools. Different syntax per platform. Never hardcode a single platform.

## Universal Tool Registry

| Operation | Concept | Hermes | Edge Gallery | Claude/ChatGPT | Fallback |
|---|---|---|---|---|---|
| **Save data** | `store(key, val)` | `memory` tool | `run_js` memory.html | Platform memory / Artifacts | File I/O |
| **Load data** | `load(key)` | `memory` (injected) | `run_js` memory.html | Platform memory | Read file |
| **Search** | `search(query)` | `session_search` | `run_js` memory.html | Projects memory | grep / FTS |
| **Web search** | `search_web(q)` | `web_search` | `run_js` search.html | Web browsing | curl DuckDuckGo |
| **Execute code** | `run(code)` | `terminal` / `execute_code` | Provide script | Code Interpreter | Paste code block |
| **Read file** | `read(path)` | `read_file` | — | Artifacts | `cat` via terminal |
| **Write file** | `write(path, content)` | `write_file` | — | Artifacts | `echo` + redirect |
| **Edit file** | `edit(path, old, new)` | `patch` | — | Artifacts | sed |
| **Ask user** | `ask(question)` | `clarify` | Direct response | Direct response | — |
| **Delegate** | `delegate(task)` | `delegate_task` | — | Projects / GPT Actions | Sequential steps |
| **Capture** | `capture()` | `browser_vision` | — | — | Describe steps |
| **Search files** | `find(pattern)` | `search_files` | — | Code Interpreter | `find`/`grep` |
| **Schedule** | `cron(schedule, task)` | `cronjob` tool | — | — | at/cron via terminal |
| **Notify** | `notify(msg)` | Telegram/WhatsApp send | `console.log` | — | Log to file |

## Platform Compatibility Matrix

| Platform | Terminal | File Ops | Web | Memory | Delegate | Vision | Cron |
|---|---|---|---|---|---|---|---|
| **Hermes Agent** | ✅ Full | ✅ Full | ✅ Full | ✅ Structured | ✅ Background | ✅ | ✅ Native |
| **Claude Code** | ✅ bash | ✅ Tool use | ✅ Via tool | ✅ Via tool | ✅ Projects | ✅ | ❌ |
| **Claude (Chat)** | ❌ | ✅ Artifacts | ✅ Web | ✅ Projects | ❌ | ✅ | ❌ |
| **ChatGPT** | ✅ Code Interpreter | ✅ Interpreter | ✅ Browsing | ✅ Memory | ✅ GPT Actions | ✅ | ❌ |
| **Edge Gallery** | ❌ | ❌ | ✅ search.html | ✅ memory.html | ❌ | ✅ vision.html | ❌ |
| **OpenCode CLI** | ✅ Full | ✅ Full | ❌ | ❌ | ✅ | ❌ | ❌ |
| **Gemini** | ❌ | ❌ | ✅ Google Search | ❌ | ❌ | ✅ | ❌ |

## Platform Detection

```python
if "terminal" in available_tools → Hermes Agent
if "run_js" in available_tools → Edge Gallery
if "bash" in available_tools → Claude Code
if "python" in available_tools → ChatGPT / Code Interpreter
```

## Tool Usage Rules

1. **Check availability** — don't call `run_js` on Hermes or `terminal` on Edge Gallery
2. **Fail gracefully** — preferred tool fails → try fallback → offer manual steps
3. **Show tool calls** — display what tool you're using and what it returned
4. **Don't simulate** — can't actually run the tool? Say so. Don't fabricate output.
5. **Abstract operations, not syntax** — think `store(key, value)` not `memory(action="add", ...)`
