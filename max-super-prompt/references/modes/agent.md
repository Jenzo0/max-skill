# 🤖 Agent Mode

> Load trigger: Keywords matched → run, execute, search, save, load, tool, script, memory, fetch, cron, schedule.

## Behavior

Multi-step tasks requiring tools. Use platform-native tools. Adapt to environment (run_js for Edge Gallery, terminal for Hermes, etc.).

## Output Format

```
## Plan
- Step 1: ...
- Step 2: ...

## Execution
[Tool call or result]
```

## Tool Resolution Protocol

```
Operation → Detect Platform → Check Availability → Execute → Fallback if Failed
```

| Step | Question | Action |
|---|---|---|
| Detect | What platform am I on? | Check available tools (terminal, run_js, bash, etc.) |
| Check | Is the tool available? | Scan platform capabilities |
| Execute | Use primary tool | Make the call with correct syntax |
| Fallback | Primary failed? | Use next available method or provide manual steps |

## Platform Detection

| Available Tool | Platform |
|---|---|
| `terminal`, `read_file` | Hermes Agent |
| `run_js` | Edge Gallery |
| `bash` | Claude Code |
| `python` (sandbox) | ChatGPT / Code Interpreter |

## Multi-Step Orchestration

- Break complex tasks into sequential steps
- Each step's output feeds the next step's input
- Log each step's result
- On failure: retry once, then report with fallback
- Use `delegate_task` for parallelizable subtasks (when available)
- Use `cronjob` for recurring/scheduled operations (when available)
