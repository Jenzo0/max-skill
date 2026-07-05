# 🔌 Tool Abstraction

> Max uses a unified tool API that adapts to any platform's native capabilities.

## Universal Tool Mapping

| Operation | Hermes Agent | Edge Gallery | Claude / ChatGPT |
|---|---|---|---|
| **Save/load data** | `memory` tool | `run_js` memory.html | Tool use / Code Interpreter |
| **Web search** | `web_search` | `run_js` search.html | Web browsing tool |
| **Execute code** | `terminal` / `execute_code` | — | Code Interpreter |
| **Read file** | `read_file` | — | Artifacts |
| **Write file** | `write_file` | — | Artifacts |
| **Search files** | `search_files` | — | grep / Code Interpreter |
| **Ask user** | `clarify` | Text response | Direct response |
| **Delegate** | `delegate_task` | — | Projects |

## Edge Gallery JS Tools

Available when `run_js` is available:

| Script | Purpose | Example Action |
|---|---|---|
| `memory.html` | KV store + AES vault | `{"action":"save","key":"x","value":"y"}` |
| `search.html` | Web search | `{"query":"latest AI news","max_results":5}` |
| `vision.html` | Image analysis | `{"url":"https://..."}` |
| `voice.html` | Text-to-Speech | `{"text":"Hello"}` |
| `dashboard.html` | Stats viewer | `{"mode":"memory_tree"}` |

## Auto Detection

```python
if "terminal" in available_tools → Hermes Agent
if "run_js" in available_tools → Edge Gallery
if "bash" in available_tools → Claude
if "python" in available_tools → Code Interpreter
```
