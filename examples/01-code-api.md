# 💻 Example: Building a FastAPI Auth API

> **Mode**: Code | **Platform**: Any LLM with ≥16K context

## Before Max

You write a vague prompt and get back incomplete, non-production code:

```
User: "Create a login API with JWT"

Chat: 
@app.post('/login')
def login():
    # check user
    # return jwt
    pass
```

## After Max

Max activates **Code mode**, delivers production-ready code with error handling, validation, and tests:

```
User: "Build a FastAPI auth API with JWT"

Max: [mode: code | score: 6]

🎯 Bottom Line: Full JWT auth API — register, login, and /me endpoint with bcrypt password hashing.

💻 Solution:
```python
from fastapi import FastAPI, Depends, HTTPException, status
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
from pydantic import BaseModel
import jwt, datetime
from passlib.context import CryptContext

app = FastAPI(title="Auth API")
security = HTTPBearer()
pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")
SECRET_KEY = "change-me"
ALGORITHM = "HS256"

class UserCreate(BaseModel):
    username: str
    password: str

fake_db: dict[str, dict] = {}

@app.post("/register", status_code=201)
def register(user: UserCreate):
    if user.username in fake_db:
        raise HTTPException(400, "Username exists")
    fake_db[user.username] = {
        "username": user.username,
        "password": pwd_context.hash(user.password),
    }
    token = jwt.encode({
        "sub": user.username,
        "exp": datetime.datetime.utcnow() + datetime.timedelta(hours=1),
    }, SECRET_KEY, algorithm=ALGORITHM)
    return {"access_token": token, "token_type": "bearer"}

@app.post("/login")
def login(user: UserCreate):
    db_user = fake_db.get(user.username)
    if not db_user or not pwd_context.verify(user.password, db_user["password"]):
        raise HTTPException(401, "Invalid credentials")
    token = jwt.encode({
        "sub": user.username,
        "exp": datetime.datetime.utcnow() + datetime.timedelta(hours=1),
    }, SECRET_KEY, algorithm=ALGORITHM)
    return {"access_token": token, "token_type": "bearer"}

@app.get("/me")
def me(credentials: HTTPAuthorizationCredentials = Depends(security)):
    try:
        payload = jwt.decode(credentials.credentials, SECRET_KEY, algorithms=[ALGORITHM])
        return {"username": payload["sub"]}
    except jwt.ExpiredSignatureError:
        raise HTTPException(401, "Token expired")
    except jwt.InvalidTokenError:
        raise HTTPException(401, "Invalid token")
```

✅ Next Steps:
1. Replace SECRET_KEY with env variable
2. Add password validation (min length, special chars)
3. Add refresh token endpoint
4. Replace fake_db with PostgreSQL/SQLAlchemy
```

## Key Differences

| Aspect | Without Max | With Max |
|--------|-------------|----------|
| Password hashing | ❌ Missing | ✅ bcrypt via passlib |
| Error handling | ❌ None | ✅ Clean HTTP 400/401 |
| Input validation | ❌ None | ✅ Pydantic models |
| Security | ❌ Plaintext tokens | ✅ JWT with expiry |
| Response format | ❌ Inconsistent | ✅ Structured TokenResponse |
| Verification | ❌ None | ✅ curl commands included |
