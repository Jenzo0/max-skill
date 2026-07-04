# 🛠️ JS Tools

Max includes 5 JavaScript-based tools for platforms that support script execution (Edge Gallery `run_js`).

## Tool Overview

| Script | File | Purpose |
|---|---|---|
| 🧠 **Memory** | `memory.html` | Persistent key-value store with vault |
| 🌐 **Search** | `search.html` | Web search via CORS proxy |
| 👁️ **Vision** | `vision.html` | Image color analysis & text detection |
| 🎤 **Voice** | `voice.html` | Text-to-Speech with voice selection |
| 📊 **Dashboard** | `dashboard.html` | Interactive stats & control center |

---

## 🧠 Memory System

**File:** `scripts/memory.html`

Persistent on-device key-value store using localStorage. Includes:
- General memory (plain text/JSON)
- Secrets Vault (AES-256-GCM encrypted)
- Import/Export as JSON files
- Auto-backup on every save

### run_js API

```json
{"script name": "memory.html", "data": "{\"action\": \"save\", \"key\": \"foo\", \"value\": \"bar\"}"}
```

**Actions:** `save`, `load`, `search`, `delete`, `clear`, `list`, `export`, `vault_save`, `vault_load`, `vault_list`

---

## 🌐 Web Search

**File:** `scripts/search.html`

Multi-source web search with filtered categories.

### run_js API
```json
{"script name": "search.html", "data": "{\"query\": \"latest AI news\", \"max_results\": 5}"}
```

---

## 👁️ Vision Analyzer

**File:** `scripts/vision.html`

On-device image analysis using canvas API.

### run_js API
```json
{"script name": "vision.html", "data": "{\"url\": \"https://example.com/photo.jpg\"}"}
```

---

## 🎤 Voice TTS

**File:** `scripts/voice.html`

Text-to-Speech using Web Speech API.

### run_js API
```json
{"script name": "voice.html", "data": "{\"text\": \"Hello, I'm Max\", \"rate\": 1.0}"}
```

---

## 📊 Dashboard

**File:** `scripts/dashboard.html`

Interactive stats viewer with 3 themes (Dark, Neon, Minimal).

### run_js API
```json
{"script name": "dashboard.html", "data": "{\"mode\": \"overview\"}"}
```
