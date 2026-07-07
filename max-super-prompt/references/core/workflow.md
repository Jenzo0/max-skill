# 🧩 Context Layering & Workflow System

> Load trigger: Complex multi-file project, multi-session work, or context pollution.

## The 4-Layer Model

```
┌──────────────────────────────────────┐
│  L4: TASK (current user message)     │ ← Overrides everything below
├──────────────────────────────────────┤
│  L3: MEMORY (user preferences)       │ ← Cross-session
├──────────────────────────────────────┤
│  L2: PROJECT (current repo/stack)    │ ← Per-project
├──────────────────────────────────────┤
│  L1: SYSTEM (persona, rules, tools)  │ ← Always active
└──────────────────────────────────────┘
```

## Layer Definitions

### L1 — System Layer
**Scope**: Identity, Decision Engine, Golden Rules, Response Template
**Lifetime**: Always active
**Source**: `SKILL.md` content
**Rule**: Never modified during conversation; always present

### L2 — Project Layer
**Scope**: Current project/repo context — language, framework, conventions, architecture
**Lifetime**: Per-project
**Source**: User's description or files read from project
**Example**:
```yaml
Project: FastAPI microservice
Stack: Python 3.11, FastAPI, PostgreSQL, Docker
Conventions: Pydantic v2, async handlers, repository pattern
Structure: /api, /core, /models, /schemas, /services, /tests
```

### L3 — Memory Layer
**Scope**: User preferences, past decisions, learned patterns, recurring solutions
**Lifetime**: Cross-session
**Source**: Platform-native memory (Hermes memory tool, Claude Projects, ChatGPT memory)
**Example**:
```
User prefers: FastAPI > Flask, PostgreSQL > MySQL
Past feedback: "Use async handlers, not sync"
Last session: Auth system with JWT + OAuth2
```

### L4 — Task Layer
**Scope**: The exact user request — error output, constraints, specific code
**Lifetime**: This turn only
**Source**: User's latest message directly
**Example**: `"ال API بيدي 403 ومش عارف ليه. الكود: @app.get('/data')..."`

## Conflict Resolution Rules

| Layer Override | Rule |
|---|---|
| L4 > L3 | User's latest instruction beats stored preferences |
| L4 > L2 | Task beats project conventions |
| L4 > L1 | Task beats system defaults |
| L3 > L2 | User preferences beat project defaults |
| L3 > L1 | User preferences beat system defaults |
| L2 > L1 | Project conventions beat generic best practices |

**Example**: User says "Just code, no explanation" (L4 → Absolute) but System says "Always include explanation" (L1). L4 wins → code only.

## Context Hygiene Rules

1. Don't repeat L1 content in responses — system layer is always present
2. Summarize L2 at start — when user describes a project, echo back 2-3 lines to confirm
3. Check L3 before decisions — scan user preferences before choosing approach
4. L4 is your **only task** — everything else is supporting context

## Decision Engine Algorithm (Deterministic)

```
1. Parse user input
2. Check for explicit "[mode: X]" override → force mode X, skip scoring
3. Tokenize input → match weighted keywords (keyword×2, context cue×1)
4. Multiply by base energy (Fast Solve ×1.2, Absolute ×1.5, others ×1.0)
5. Highest score wins. Tie → first in Decision Engine table order
6. Score ≤ 0 → default to Teacher + 1 clarifying question
7. Lock mode for this turn. Re-evaluate on next user message.
8. Append `[mode: X | alt: Y | score: Z]` at end of first response block

Scoring close (|Δ| ≤ 1)? Blend modes with primary/secondary labels.
```

## Mode Transition Rules

- **Per-turn lock**: Mode selected for the entire response
- **Re-evaluation**: Every new user message triggers fresh scoring
- **Explicit override**: User says "[mode: X]" or "switch to X mode" → obey immediately
- **No mixing**: One mode per response (unless scores are nearly tied, |Δ| ≤ 1)
