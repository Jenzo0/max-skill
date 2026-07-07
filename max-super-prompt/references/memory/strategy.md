# 🧠 Memory Strategy — Abstraction Interface

> Load trigger: Any memory operation (save, load, search, delete preferences).

## Architecture

```
Max
  │
  └─ Memory Interface (abstract)
       │
       ├─ Platform Memory (Hermes memory tool, ChatGPT memory, Claude Projects)
       ├─ File-based (JSON, Markdown files)
       ├─ Database (SQLite, PostgreSQL, Redis)
       ├─ Vector DB (ChromaDB, Qdrant, Pinecone)
       └─ Edge Gallery (memory.html via run_js)
```

## Memory Interface Specification

Every memory provider implements these operations:

| Operation | Signature | Description |
|---|---|---|
| `store` | `(key: str, value: str, namespace?: str) → bool` | Save a value |
| `load` | `(key: str, namespace?: str) → str / None` | Retrieve a value |
| `search` | `(query: str, namespace?: str) → list[dict]` | Find keys by content |
| `delete` | `(key: str, namespace?: str) → bool` | Remove a key |
| `list` | `(namespace?: str) → list[str]` | List all keys |
| `clear` | `(namespace?: str) → bool` | Remove all data in namespace |

## Cross-Session Memory Types

| Type | Lifetime | Storage | Example |
|---|---|---|---|
| User preferences | Persistent | Platform memory | "User prefers FastAPI" |
| Project context | Per-project | File or memory | "Project: FastAPI + PostgreSQL" |
| Session state | Current session | In-context | "Just built auth system" |
| Temporary data | Per-task | In-context or JSON | "API response from step 1" |

## Namespace Convention

Use hierarchical namespaces for multi-project isolation:

```
user/preferences          → User-level settings
project/<name>/context    → Project-specific context
project/<name>/decisions  → Past design decisions
session/<id>/state        → Current session data
skill/<name>/knowledge    → Skill-specific knowledge
```
