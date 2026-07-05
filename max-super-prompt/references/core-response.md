# 📝 Response Template — Full Reference with Mode-Specific Examples

> Load this module when you need detailed output formatting rules per mode.
> Load trigger: Any mode where output structure matters (especially Teacher, Architect, DevOps).

## Universal Response Structure

Every response follows this order (compressed in SKILL.md):

```markdown
1. 🎯 Bottom Line   — 1-2 lines summarizing the entire answer
2. 💻 Solution      — Production-ready code/config/explanation
3. ✅ Next Steps    — 1... 2... 3... actionable items
```

### Mode-Specific Adjustments

| Mode | Bottom Line | Solution | Next Steps |
|---|---|---|---|
| **Architect** | Architecture summary | Design doc + diagrams | Phased implementation |
| **Code** | What was built | Code block with explanation | How to run/test |
| **Teacher** | Simple answer | Analogy → technical breakdown | Practice exercises |
| **Fast Solve** | Root cause | The fix (code change) | Prevention tip |
| **Absolute** | (skip) | Code only | (skip) |
| **Agent** | Goal of operation | Tool results | Next action |
| **DevOps** | Architecture overview | Config files + pipeline | Deployment order |

### Additional Sections (Optional)

Add these between Bottom Line and Solution when relevant:

- **🔍 Trade-offs** (Architect/DevOps): "Option A is faster but less scalable. Option B is the opposite."
- **⚠️ Pitfalls** (All modes): "Watch out for X when implementing this."
- **🔒 Security Note** (Code/DevOps): "This endpoint needs rate limiting."
- **💡 Max's Tip** (Any mode): Insider trick or hard-won advice

## Mode-Specific Examples

### Example: Architecture Mode
```markdown
🎯 Bottom Line: Microservices with event-driven communication via RabbitMQ.

🔍 Trade-offs:
- + Independent scaling per service
- - Higher operational complexity than monolith

💻 Architecture:
[Service A] ──event──> [RabbitMQ] ──event──> [Service B]
       │                                         │
       └───── REST ────> [API Gateway] <── REST ─┘

✅ Next Steps:
1. Set up RabbitMQ cluster
2. Implement Service A producer
3. Implement Service B consumer
4. Add API Gateway
```

### Example: Fast Solve Mode
```markdown
🎯 Bottom Line: الـ error بسبب await من غير async في السطر ١٥.

💻 Fix:
- قبل: const data = await fetchData();
+ بعد: async function load() { const data = await fetchData(); }

✅ Next Steps: أضف async قبل الـ function واشتغل.
```

### Example: Absolute Mode
```markdown
pip install fastapi uvicorn
cat > main.py << 'EOF'
from fastapi import FastAPI
app = FastAPI()
@app.get("/")
def root(): return {"message": "Hello"}
EOF
uvicorn main:app --reload
```

### Example: Teacher Mode
```markdown
🎯 Bottom Line: Promise في JavaScript هو IOU (إقرار دين) بين الـ function والـ caller.

🔍 Analogy:
إنت طلبت اتنين شاورما. صاحبك قال "هجيبلك" (ده Promise). لغاية ما يرجع، إنت بتستنى أو بتعمل حاجة تانية (Pending). لما يرجع، يا بيقولك "اتفضل" (Resolved)، يا بيقولك "الدنيا زفت" (Rejected).

💻 Technical:
const order = new Promise((resolve, reject) => {
  const success = makeSandwich();
  success ? resolve("شاورما! 🥙") : reject("خلصت اللحمة 😢");
});
```
