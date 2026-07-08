# 💾 Memory Persistence — Storage Backends

> Load trigger: Selecting or configuring a memory storage backend.

## Storage Backend Comparison

| Backend | Persistence | Search | Speed | Cross-Platform | Use When |
|---|---|---|---|---|---|
| **Platform Memory** | Session-to-session | ✅ | Fast | ✅ | The primary channel has a built-in memory system (Hermes, ChatGPT) |
| **JSON File** | Manual save/load | ❌ | Instant | ✅ | Quick local persistence, no dependencies |
| **Markdown File** | Manual | ❌ | Instant | ✅ | Human-readable knowledge base |
| **SQLite** | Persistent | ✅ FTS5 | Fast | ✅ | Structured data, multi-session projects |
| **Redis** | Volatile / persistent | ❌ exact key only | Very fast | ✅ | Caching, sessions, real-time state |
| **ChromaDB / Qdrant** | Persistent | ✅ Vector search | Medium | ✅ | RAG, semantic search, embeddings |
| **Edge Gallery memory.html** | Browser localStorage | ✅ KV search | Fast | ❌ Browser only | Edge Gallery platform |

## Hermes Memory (Primary for Hermes Agent)

| Operation | Code |
|---|---|
| Save | `memory(action="add", target="memory", content="...")` or `memory(operations=[{action:"add",...}])` |
| Load | `memory(action="add"...` doesn't "load" — memory is injected into every turn automatically |
| Search | `session_search(query="...")` |
| Preference | `memory(action="add", target="user", content="...")` |

## JSON File Fallback

```python
import json, os
MEMORY_FILE = "max-memory.json"

def store(key, value):
    mem = {}
    if os.path.exists(MEMORY_FILE):
        with open(MEMORY_FILE) as f:
            mem = json.load(f)
    mem[key] = value
    with open(MEMORY_FILE, "w") as f:
        json.dump(mem, f)

def load(key):
    if not os.path.exists(MEMORY_FILE):
        return None
    with open(MEMORY_FILE) as f:
        mem = json.load(f)
    return mem.get(key)
```

## Edge Gallery — memory.html

Available via `run_js` with `memory.html` script. Supports:
- `save`, `load`, `search`, `delete`, `clear`
- `vault_save`, `vault_load` (AES-256-GCM encrypted)
- `export`, `import` (full JSON export/import)

## Migration Path

To add a new backend:
1. Implement the interface (store, load, search, delete, list)
2. Register it in the provider registry
3. Add connection config (endpoint, credentials, namespace)
4. No changes needed in the core SKILL.md
