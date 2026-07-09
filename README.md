![Max Banner](https://files.catbox.moe/d3ji1i.jpg)

<h1 align="center">🧠 Max — Universal AI Skill Framework</h1>
<h3 align="center">CTO + Senior Dev + Architect + Teacher in One Prompt · 100% Prompt-Only</h3>

<p align="center">
  <a href="https://github.com/Jenzo0/max-skill/releases"><img src="https://img.shields.io/github/v/release/Jenzo0/max-skill?style=flat-square&label=Version&color=FF6B6B" alt="Version"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT License"></a>
  <a href="https://github.com/Jenzo0/max-skill/stargazers"><img src="https://img.shields.io/github/stars/Jenzo0/max-skill?style=flat-square&label=Stars&color=yellow" alt="Stars"></a>
  <a href="https://jenzo0.github.io/max-skill/"><img src="https://img.shields.io/badge/GitHub%20Pages-Deployed-blueviolet?style=flat-square" alt="Pages"></a>
  <br>
  <img src="https://img.shields.io/badge/Model-Agnostic-4299e1?style=flat-square" alt="Model Agnostic">
  <img src="https://img.shields.io/badge/Platform-Universal-success?style=flat-square" alt="Universal">
  <img src="https://img.shields.io/badge/Locale-English%20%7C%20Arabic-orange?style=flat-square" alt="Bilingual">
  <img src="https://img.shields.io/badge/Architecture-Modular-purple?style=flat-square" alt="Modular">
  <img src="https://img.shields.io/badge/Integrations-Claude%20·%20ChatGPT%20·%20Hermes%20·%20Edge%20Gallery-blue?style=flat-square" alt="Integrations">
</p>

<p align="center">
  <em>"Senior Engineer, not just AI."</em>
  <br>
  <strong>Open Source</strong> · <strong>Model Agnostic</strong> · <strong>Platform Agnostic</strong> · <strong>100% Prompt</strong>
</p>

---

## 📋 Sections

| # | Section | File |
|:-:|:--------|:-----|
| 1 | 🤔 Why Max | [WHY.md](WHY.md) |
| 2 | ✨ Features | [FEATURES.md](FEATURES.md) |
| 3 | 🏗️ Architecture | [ARCHITECTURE.md](ARCHITECTURE.md) |
| 4 | 📊 Model Compatibility | [SUPPORTED_MODELS.md](SUPPORTED_MODELS.md) |
| 5 | 💸 Token Cost & Response Quality | [STATS.md](STATS.md) |
| 6 | 📖 FAQ | [FAQ.md](FAQ.md) |
| 7 | 🗺️ Roadmap | [ROADMAP.md](ROADMAP.md) |
| 8 | 🤝 Contributing | [CONTRIBUTING.md](CONTRIBUTING.md) |
| 9 | 📄 Documentation | [Wiki](https://github.com/Jenzo0/max-skill/wiki) |
| 10 | 📜 License | [LICENSE](LICENSE) |
| 11 | 🚀 Why Max Stands Out | [WHY_STANDS_OUT.md](WHY_STANDS_OUT.md) |

---

## 🚀 30-Second Quick Start

> **Try Max in under a minute — zero setup required.**

```bash
# 1️⃣ Load Max into Claude Code / OpenCode / Codex
curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > /tmp/max.md
claude --prompt "$(cat /tmp/max.md)"

# 2️⃣ Or paste as system prompt in ChatGPT/Claude/Gemini:
#    https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md

# 3️⃣ For Edge Gallery / Gemma (Lite version):
#    https://jenzo0.github.io/max-skill/max-super-prompt/lite/
```

### 🌐 Try it Online — Zero Setup

> Test Max instantly on Telegram or WhatsApp — no install needed.

[**▶️ Try max-super-prompt on ClawMama**](https://app.clawmama.run/skills/t40ue3/hermes)

---

## 📦 Installation

### Claude Code / OpenCode / Codex (Full — Recommended)

```bash
curl -s https://jenzo0.github.io/max-skill/max-super-prompt/SKILL.md > /tmp/max.md
claude --prompt "$(cat /tmp/max.md)"
```

### Hermes Agent

```bash
git clone https://github.com/Jenzo0/max-skill.git
cp -r max-skill/max-super-prompt ~/AppData/Local/hermes/skills/persona/
# Then: skill_view(name='max-super-prompt')
```

### ChatGPT / Claude / Gemini / OpenRouter (API)

Paste this URL as **System Prompt**:
```
https://raw.githubusercontent.com/Jenzo0/max-skill/main/max-super-prompt/SKILL.md
```

### Edge Gallery / Gemma (Lite — 700 tokens)

**URL import:**
```
https://jenzo0.github.io/max-skill/max-super-prompt/lite/
```

**Or download:** `max-super-prompt/lite/SKILL.md` → Edge Gallery → (+) → Import local skill.

### Cursor IDE

1. Open Cursor → Settings → Custom Instructions
2. Paste the contents of `max-super-prompt/SKILL.md` into "Custom Instructions"
3. Or include via `.cursorrules` file

---

## 🎯 Examples

### 💻 Building an API (Code Mode)

```
**User**: "Build a FastAPI auth API with JWT"

**Max**: [mode: code | score: 6]

## Solution

```python
from fastapi import FastAPI, Depends, HTTPException, status
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
from pydantic import BaseModel
import jwt, datetime
from passlib.context import CryptContext

app = FastAPI(title="Auth API", version="1.0")
security = HTTPBearer()
pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")
SECRET_KEY = "change-me-in-production"
ALGORITHM = "HS256"

class UserCreate(BaseModel):
    username: str
    password: str

class TokenResponse(BaseModel):
    access_token: str
    token_type: str = "bearer"

fake_users_db: dict[str, dict] = {}

@app.post("/register", response_model=TokenResponse, status_code=201)
def register(user: UserCreate):
    if user.username in fake_users_db:
        raise HTTPException(400, "Username already exists")
    hashed = pwd_context.hash(user.password)
    fake_users_db[user.username] = {"username": user.username, "password": hashed}
    token = jwt.encode({"sub": user.username, "exp": datetime.datetime.utcnow() + datetime.timedelta(hours=1)}, SECRET_KEY, algorithm=ALGORITHM)
    return TokenResponse(access_token=token)

@app.post("/login", response_model=TokenResponse)
def login(user: UserCreate):
    db_user = fake_users_db.get(user.username)
    if not db_user or not pwd_context.verify(user.password, db_user["password"]):
        raise HTTPException(401, "Invalid credentials")
    token = jwt.encode({"sub": user.username, "exp": datetime.datetime.utcnow() + datetime.timedelta(hours=1)}, SECRET_KEY, algorithm=ALGORITHM)
    return TokenResponse(access_token=token)

@app.get("/me")
def get_current_user(credentials: HTTPAuthorizationCredentials = Depends(security)):
    token = credentials.credentials
    try:
        payload = jwt.decode(token, SECRET_KEY, algorithms=[ALGORITHM])
        return {"username": payload["sub"]}
    except jwt.ExpiredSignatureError:
        raise HTTPException(401, "Token expired")
    except jwt.InvalidTokenError:
        raise HTTPException(401, "Invalid token")
```

> 📚 See [examples/](examples/) for more real-world use cases.

---

<p align="center">
  <img src="assets/images/jenzo-avatar.jpg" width="56">
</p>

<h3 align="center">Jenzo Sky</h3>

<p align="center">
Senior Engineer • Building useful AI tools.
</p>

<p align="center">
⭐️ Star • 🍴 Fork • 🤖 Try with your favorite LLM
</p>
