# 🧩 Context Layers — System of Separation

> Load this module when the task involves: complex multi-file projects, persistent memory across sessions, or when you need to separate system instructions from user data.
> Load trigger: Large project handoff, multi-session work, or when context seems polluted.

## The 4-Layer Model

Maintain these 4 distinct layers in order. Each layer has a different scope, lifetime, and access pattern.

```
┌──────────────────────────────────────┐
│  L4: TASK LAYER                      │
│  "Current user request"              │
│  Lifetime: This turn                  │
├──────────────────────────────────────┤
│  L3: MEMORY LAYER                    │
│  "What I know about user/project"    │
│  Lifetime: Cross-session             │
├──────────────────────────────────────┤
│  L2: PROJECT LAYER                   │
│  "Current project context"           │
│  Lifetime: Per-project               │
├──────────────────────────────────────┤
│  L1: SYSTEM LAYER                    │
│  "Who I am, how I think"             │
│  Lifetime: Always active             │
└──────────────────────────────────────┘
```

---

## L1: System Layer (Always Active)
**Scope**: Identity, Decision Engine, Rules, Response Template
**Contains**: The SKILL.md content — persona, mode selector, compressed rules, tool mapping
**Access**: Always loaded. Never modified during conversation.
**File**: `SKILL.md` (this is the layer)

## L2: Project Layer (Per-Project)
**Scope**: Current project/repo context
**Contains**: Language, framework, architecture patterns, file structure, conventions
**Load When**: User describes a project or you detect a project context
**Store**: In platform memory or a `project_context.md` note
**Example**:
```
Project: FastAPI microservice
Stack: Python 3.11, FastAPI, PostgreSQL, Docker
Conventions: Pydantic v2, async handlers, repository pattern
Structure: /api, /core, /models, /schemas, /services, /tests
```

## L3: Memory Layer (Cross-Session)
**Scope**: User preferences, past decisions, learned patterns
**Contains**: Preferred tools, coding style, recurring issues, past solutions
**Load When**: Every session start (platform's memory system handles this)
**Store**: Platform-native memory (Hermes memory tool, Claude Projects, ChatGPT memory)
**Example**:
```
User prefers: FastAPI over Flask, PostgreSQL over MySQL, Docker Compose over K8s for small projects
Past feedback: "Use async handlers, not sync"
Last session: Was building auth system with JWT + OAuth2
```

## L4: Task Layer (Per-Turn)
**Scope**: The exact user request
**Contains**: User's latest message, error output, specific constraints, priorities
**Load When**: Every new user message
**Access**: Direct from user's input — this IS the current message
**Example**:
```
"ال API بيدي 403 ومش عارف ليه. الكود:
@app.get('/data')
def get_data():
    return db.query(...)
"
```

## Context Priority Rules

When layers conflict, higher-numbered layers override lower-numbered ones:

1. **Task Layer (L4)** overrides everything — the user's latest instruction is always correct
2. **Memory Layer (L3)** overrides Project and System — user preferences beat defaults
3. **Project Layer (L2)** overrides System — project conventions beat generic best practices
4. **System Layer (L1)** is the fallback — applies when no other layer specifies

### Example: Conflict Resolution
```
User says: "Just give me the code, no explanation"  (L4: Task → Absolute Mode)
But System says: "Always include explanation"        (L1: System)
→ L4 overrides L1 → Code only, no explanation ✓
```

## Context Hygiene Rules

1. **Don't repeat L1 content in responses** — the system layer is always present, don't waste tokens restating it
2. **Summarize L2 at start** — when a user describes their project, summarize it back in 2-3 lines to confirm
3. **Read L3 before acting** — check if the user has established preferences before making decisions
4. **L4 is your ONLY task** — everything else is context. The task layer is what you're actually doing.
