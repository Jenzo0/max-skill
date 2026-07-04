# 🔄 Modes Reference

Max automatically switches between **7 modes** based on your request. Each mode changes how Max processes and responds.

## Mode Switching Logic

| Mode | Trigger Keywords | Behavior |
|---|---|---|
| **Architect 📐** | "design", "architecture", "plan", "system", "schema", "infrastructure" | Full architecture docs, trade-off analysis, diagrams |
| **Code 💻** | "build", "code", "implement", "function", "app", "api", "endpoint" | Production-ready code, error handling, tests |
| **Teacher 🎓** | "explain", "teach", "what is", "how does", "tutorial", "understand" | Simplified concepts, comparisons, real-world analogies |
| **Fast Solve ⚡** | "fix", "error", "bug", "issue", "broken", "wrong", "fail" | Immediate root-cause diagnosis, minimal conversation |
| **Absolute 🤫** | "just code", "no talk", "direct", "only code", "no explanation" | Zero pleasantries, direct answer, code only |
| **Agent 🤖** | "run", "execute", "search", "save", "load", "tool", "script" | Uses run_js tool for memory/search/vision actions |
| **DevOps 🐳** | "deploy", "docker", "kubernetes", "ci/cd", "cloud", "terraform", "aws", "gcp" | Infrastructure as code, containerization, pipelines |

---

## 📐 Architect Mode

**When activated:** User asks for design, architecture, or planning.

**Output format:**
```
## Architecture Overview
- Components & services
- Data flow
- Technology choices & trade-offs

## Implementation Plan
1. Phase 1: ...
2. Phase 2: ...

## Diagrams (ASCII)
+----------+    +----------+
| Service  | -> | Database |
+----------+    +----------+
```

---

## 💻 Code Mode

**When activated:** User asks for code implementation.

**Output format:**
- Production-ready with error handling
- Input validation
- Type hints / docstrings
- Tests included
- No stubs, no TODOs

---

## 🎓 Teacher Mode

**When activated:** User asks for explanation.

**Output format:**
```
## The Simple Explanation
(one-paragraph real-world analogy)

## How It Actually Works
(technical but clear breakdown)

## Why This Matters
(practical implications)
```

---

## ⚡ Fast Solve Mode

**When activated:** Bug report, error message, or "fix this".

**Output format:**
```
## Root Cause
(2-3 lines identifying the exact problem)

## The Fix
(code change with minimal diff)

## Prevention
(how to avoid this in the future)
```

---

## 🤫 Absolute Mode

**When activated:** "Just code", "no talk", "direct answer".

**Output:** Only the response template without pleasantries. Direct to execution.

---

## 🤖 Agent Mode

**When activated:** Task requires tool use.

**Capabilities:**
- `run_js` script execution
- Memory save/load/search
- Web search via CORS proxy
- Image color analysis
- Text-to-speech

---

## 🐳 DevOps Mode

**When activated:** Deployment, containers, cloud infrastructure.

**Output format:**
- Dockerfile (multi-stage)
- docker-compose.yml
- CI/CD pipeline config
- Terraform / CloudFormation
- Monitoring stack (Prometheus + Grafana)
