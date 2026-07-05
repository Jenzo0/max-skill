# 🛠️ JS Tools — Edge Gallery Reference

> Load this module ONLY when running inside Google AI Edge Gallery with `run_js` available.
> On other platforms (Claude, ChatGPT, Hermes), use the core-tool-abstraction.md mappings instead.

## Available Scripts

All scripts are self-contained HTML files (CSS + JS inline). Use `run_js` with the following payloads:

### Memory System — `memory.html`
```json
{
  "script name": "memory.html",
  "data": "{\"action\": \"ACTION\", \"key\": \"...\", \"value\": \"...\"}"
}
```

| Action | Description | Required Fields |
|---|---|---|
| `save` | Store a value | `key`, `value` |
| `load` | Retrieve a value | `key` |
| `search` | Find keys by query | `query` |
| `delete` | Remove a key | `key` |
| `clear` | Remove ALL data | (none) |
| `vault_save` | Encrypt + store (AES-256-GCM) | `key`, `value`, `password` |
| `vault_load` | Decrypt + retrieve | `key`, `password` |
| `export` | Export all data as JSON | (none) |
| `import` | Import from JSON export | `data` |

### Web Search — `search.html`
```json
{
  "script name": "search.html",
  "data": "{\"query\": \"your search query\", \"max_results\": 5}"
}
```

Optional filters in `data`: `{region, safe_search, time_range}`.

### Interactive Dashboard — `dashboard.html`
```json
{
  "script name": "dashboard.html",
  "data": "{\"mode\": \"MODE\"}"
}
```

| Mode | What It Shows |
|---|---|
| `memory_tree` | Tree view of all stored keys |
| `stats` | Usage statistics (entries, size, activity) |
| `skills_overview` | Loaded skills and their status |
| `evolution_map` | Memory changes over time |

### Vision Analysis — `vision.html`
```json
{
  "script name": "vision.html",
  "data": "{\"url\": \"https://...image.jpg\"}"
}
```

Analyzes: dominant colors, object detection proxy, text overlay detection, edge density.

### Voice TTS — `voice.html`
```json
{
  "script name": "voice.html",
  "data": "{\"text\": \"Text to speak\"}"
}
```

Uses Web Speech API. Optional: `{voice: "female|male", rate: 0.5..2.0, pitch: 0.5..2.0}`.

## Platform-Specific Notes

| Platform | `run_js` Available? | Alternative |
|---|---|---|
| Edge Gallery | ✅ Yes | — |
| Claude / Claude Code | ❌ No | Use tool abstraction (bash, tool use) |
| ChatGPT | ❌ No | Code Interpreter / GPT Actions |
| Hermes Agent | ❌ No | Terminal, memory tool, web_search |
| Ollama / Local | ❌ No | Terminal commands |
